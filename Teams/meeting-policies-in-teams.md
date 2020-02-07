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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836477"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="b11fb-103">Teams での会議ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="b11fb-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="b11fb-104">会議ポリシーは、組織内のユーザーによってスケジュールされている会議の参加者が使用できる機能を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="b11fb-105">ポリシーを作成して変更を行うと、そのポリシーにユーザーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-105">After you create a policy and make your changes, you can then assign users to the policy.</span></span> <span data-ttu-id="b11fb-106">会議ポリシーは、Microsoft Teams 管理センターまたは[PowerShell](teams-powershell-overview.md)を使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-106">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

<span data-ttu-id="b11fb-107">ポリシーを実装するには、次のような方法があります。これは、会議の開始前、会議中、または会議中にユーザーの会議の操作に影響します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-107">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="b11fb-108">実装の種類</span><span class="sxs-lookup"><span data-stu-id="b11fb-108">Implementation type</span></span>  |<span data-ttu-id="b11fb-109">説明</span><span class="sxs-lookup"><span data-stu-id="b11fb-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="b11fb-110">開催者ごと</span><span class="sxs-lookup"><span data-stu-id="b11fb-110">Per-organizer</span></span>    |<span data-ttu-id="b11fb-111">開催者ごとのポリシーを実装すると、すべての会議参加者が開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-111">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="b11fb-112">たとえば、ユーザーが開催者ごと**に自動的に**参加するポリシーを設定し、そのポリシーが割り当てられているユーザーによってスケジュールされた会議のロビーでユーザーが会議に参加するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-112">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="b11fb-113">ユーザーごと</span><span class="sxs-lookup"><span data-stu-id="b11fb-113">Per-user</span></span>    |<span data-ttu-id="b11fb-114">ユーザーごとのポリシーを実装する場合、開催者や会議の参加者の特定の機能を制限するために、ユーザーごとのポリシーのみが適用されます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-114">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="b11fb-115">たとえば、 **[チャネルでの今すぐ会議を許可する**] は、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="b11fb-115">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="b11fb-116">開催者ごととユーザーごと</span><span class="sxs-lookup"><span data-stu-id="b11fb-116">Per-organizer and per-user</span></span>     |<span data-ttu-id="b11fb-117">開催者ごととユーザーごとのポリシーの組み合わせを実装する場合、特定の機能は、そのポリシーと開催者のポリシーに基づいて会議の参加者に制限されます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-117">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="b11fb-118">たとえば、**クラウドの記録を許可する**のは、開催者ごととユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="b11fb-118">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="b11fb-119">会議の開催者と参加者がレコーディングを開始および停止できるようにするには、この設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="b11fb-119">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="b11fb-120">既定では、Global (Org wide default) という名前のポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-120">By default, a policy named Global (Org-wide default) is created.</span></span> <span data-ttu-id="b11fb-121">組織内のすべてのユーザーには、既定でグローバル会議ポリシーが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-121">All users in your organization are assigned the Global meeting policy by default.</span></span> <span data-ttu-id="b11fb-122">それに変更を加えるか、1つ以上のカスタムポリシーを作成してユーザーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-122">You can either make changes to it or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="b11fb-123">カスタムポリシーを作成して割り当てる場合を除き、ユーザーはグローバルポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-123">Users will get the Global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="b11fb-124">ユーザー設定のポリシーを作成するときに、特定の機能をユーザーが利用できるようにするか、または設定を適用する1人以上のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-124">When you create a custom policy, you can allow or prevent certain features from being available to your users, and then assign it to one or more users who will have the settings applied to them.</span></span>

## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="b11fb-125">会議のポリシーを変更または作成する</span><span class="sxs-lookup"><span data-stu-id="b11fb-125">Change or create a meeting policy</span></span>

<span data-ttu-id="b11fb-126">会議のポリシーを変更または作成するには、Microsoft Teams 管理センターの >**会議** > の**会議のポリシー**を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b11fb-126">To change or create a meeting policy, go to the Microsoft Teams admin center > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="b11fb-127">リストからポリシーを選ぶか、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-127">Select a policy from the list or select **Add**.</span></span> <span data-ttu-id="b11fb-128">新しいポリシーを作成する場合は、名前と説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-128">If you're creating a new policy, add a name and description.</span></span> <span data-ttu-id="b11fb-129">名前には特殊文字を含めたり、64文字より長い名前を指定したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b11fb-129">The name can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="b11fb-130">設定を選び、[**保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-130">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="b11fb-131">たとえば、多数のユーザーがいて、会議で必要な帯域幅の量を制限するとします。</span><span class="sxs-lookup"><span data-stu-id="b11fb-131">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="b11fb-132">"制限された帯域幅" という名前の新しいカスタムポリシーを作成して、次の設定を無効にします。</span><span class="sxs-lookup"><span data-stu-id="b11fb-132">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="b11fb-133">[**オーディオ & ビデオ**:</span><span class="sxs-lookup"><span data-stu-id="b11fb-133">Under **Audio & video**:</span></span>
- <span data-ttu-id="b11fb-134">クラウドの記録を許可する機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="b11fb-134">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="b11fb-135">「IP ビデオを許可」をオフにします。</span><span class="sxs-lookup"><span data-stu-id="b11fb-135">Turn off Allow IP video.</span></span>

<span data-ttu-id="b11fb-136">[**コンテンツ共有**] の下:</span><span class="sxs-lookup"><span data-stu-id="b11fb-136">Under **Content sharing**:</span></span>
- <span data-ttu-id="b11fb-137">画面共有モードを無効にします。</span><span class="sxs-lookup"><span data-stu-id="b11fb-137">Disable screen sharing mode.</span></span>
- <span data-ttu-id="b11fb-138">ホワイトボードを許可する機能をオフにします。</span><span class="sxs-lookup"><span data-stu-id="b11fb-138">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="b11fb-139">共有のノートを許可する機能をオフにします。</span><span class="sxs-lookup"><span data-stu-id="b11fb-139">Turn off Allow shared notes.</span></span>

<span data-ttu-id="b11fb-140">次に、ポリシーをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-140">Then assign the policy to the users.</span></span>

> [!NOTE]
> <span data-ttu-id="b11fb-141">ユーザーには、一度に1つの会議ポリシーのみを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-141">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="b11fb-142">ユーザーに会議ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b11fb-142">Assign a meeting policy to users</span></span>

1. <span data-ttu-id="b11fb-143">Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b11fb-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="b11fb-144">ユーザー名の左側をクリックしてユーザーを選び、[**設定の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b11fb-144">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="b11fb-145">[**会議ポリシー**] で、割り当てるポリシーを選び、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b11fb-145">Under **Meeting policy**, select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="b11fb-146">一度に複数のユーザーにポリシーを割り当てるには、「[チームのユーザー設定を一括](edit-user-settings-in-bulk.md)して編集する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b11fb-146">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="b11fb-147">または、次の操作も行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-147">Or, you can also do the following:</span></span>

1. <span data-ttu-id="b11fb-148">Microsoft Teams 管理センターの左のナビゲーションで、[**会議** > の**ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-148">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="b11fb-149">ポリシー名の左側をクリックして、ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-149">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="b11fb-150">[**ユーザーの管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-150">Select **Manage users**.</span></span>
4. <span data-ttu-id="b11fb-151">[**ユーザーの管理**] ウィンドウで、[表示名] または [ユーザー名] でユーザーを検索し、名前を選択して [**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-151">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="b11fb-152">追加するユーザーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-152">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="b11fb-153">ユーザーの追加が完了したら、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-153">After you finish adding users, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="b11fb-154">ポリシーは、ユーザーに割り当てられている場合は削除できません。</span><span class="sxs-lookup"><span data-stu-id="b11fb-154">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="b11fb-155">最初に、影響を受けるすべてのユーザーに別のポリシーを割り当てる必要があります。その後、元のポリシーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-155">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="b11fb-156">会議のポリシー設定</span><span class="sxs-lookup"><span data-stu-id="b11fb-156">Meeting policy settings</span></span>

<span data-ttu-id="b11fb-157">[**会議ポリシー** ] ページで既存のポリシーを選ぶか、[**追加**] を選んで新しいポリシーを追加するときに、次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-157">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- <span data-ttu-id="b11fb-158">[[全般]](#meeting-policy-settings---general)</span><span class="sxs-lookup"><span data-stu-id="b11fb-158">[General](#meeting-policy-settings---general)</span></span>
- [<span data-ttu-id="b11fb-159">オーディオ & ビデオ</span><span class="sxs-lookup"><span data-stu-id="b11fb-159">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="b11fb-160">コンテンツ共有</span><span class="sxs-lookup"><span data-stu-id="b11fb-160">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="b11fb-161">ゲスト & 参加者</span><span class="sxs-lookup"><span data-stu-id="b11fb-161">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end 

<span data-ttu-id="b11fb-162"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="b11fb-162"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="b11fb-163">会議のポリシー設定-全般</span><span class="sxs-lookup"><span data-stu-id="b11fb-163">Meeting policy settings - General</span></span>

- <span data-ttu-id="b11fb-164">[チャネルの [会議の開始] を許可する](#allow-meet-now-in-channels)</span><span class="sxs-lookup"><span data-stu-id="b11fb-164">[Allow Meet now in channels](#allow-meet-now-in-channels)</span></span>
- [<span data-ttu-id="b11fb-165">Outlook アドインの使用を許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-165">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="b11fb-166">チャネル会議のスケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-166">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="b11fb-167">プライベート会議のスケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-167">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="b11fb-168">チャネルの [会議の開始] を許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-168">Allow Meet now in channels</span></span>

<span data-ttu-id="b11fb-169">これはユーザーごとのポリシーであり、会議が開始される前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-169">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="b11fb-170">この設定は、ユーザーが Teams のチャネルで臨時の会議を開始できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-170">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="b11fb-171">この設定を有効にした場合、ユーザーが Teams チャネルでメッセージを投稿したときに、[作成] ボックスの下にある [**今すぐ**ミーティング] をクリックして、チャネル内で臨時の会議を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-171">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** under the compose box to start an ad hoc meeting in the channel.</span></span>

![メッセージの下に [今すぐ会議] アイコンが表示されたスクリーンショット](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="b11fb-173">Outlook アドインの使用を許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-173">Allow the Outlook add-in</span></span>

<span data-ttu-id="b11fb-174">これはユーザーごとのポリシーであり、会議が開始される前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-174">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="b11fb-175">この設定は、Teams 会議を Outlook 内でスケジュールできるかどうかを制御します (Windows、Mac、web、およびモバイル)。</span><span class="sxs-lookup"><span data-stu-id="b11fb-175">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![新しい会議をスケジュールする機能を示すスクリーンショット](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="b11fb-177">この設定を無効にした場合、ユーザーが Outlook で新しい会議を作成するときに、チームの会議をスケジュールできなくなります。</span><span class="sxs-lookup"><span data-stu-id="b11fb-177">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="b11fb-178">たとえば、Windows の Outlook では、[**新しいチーム会議**] オプションがリボンに表示されません。</span><span class="sxs-lookup"><span data-stu-id="b11fb-178">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="b11fb-179">チャネル会議のスケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-179">Allow channel meeting scheduling</span></span>

<span data-ttu-id="b11fb-180">これはユーザーごとのポリシーであり、会議が開始される前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-180">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="b11fb-181">この設定は、ユーザーが Teams のチャネルで会議をスケジュールできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-181">This setting controls whether users can schedule a meeting in a Teams channel.</span></span>  <span data-ttu-id="b11fb-182">この設定を無効にした場合、チームのチャネルで会議を開始したときに [**会議のスケジュール**] オプションがユーザーに表示されず、チームのユーザーに対して [**チャネルの追加**] オプションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="b11fb-182">If you turn this off, the **Schedule a meeting** option won't be available to the user when they start a meeting in a Teams channel and the **Add channel** option is disabled for users in Teams.</span></span>

![Teams の [会議のスケジュール] オプションを示すスクリーンショット](media/meeting-policies-schedule-a-meeting.png)

![[会議のためのチャネルの選択] オプションを示すスクリーンショット](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="b11fb-185">プライベート会議のスケジュールを許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-185">Allow scheduling private meetings</span></span>

<span data-ttu-id="b11fb-186">これはユーザーごとのポリシーであり、会議が開始される前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-186">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="b11fb-187">この設定は、ユーザーが Teams でプライベート会議をスケジュールできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-187">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="b11fb-188">チーム内のチャネルに発行されていない場合、会議は非公開になります。</span><span class="sxs-lookup"><span data-stu-id="b11fb-188">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="b11fb-189">[**プライベート会議のスケジュール設定を許可**し、**チャネル会議のスケジュールを許可**する] をオフにすると、Teams のユーザーに対して [**必須出席者の追加**] オプションと [チャネルの**追加**] オプションが無効になることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b11fb-189">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span>

<span data-ttu-id="b11fb-190"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="b11fb-190"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="b11fb-191">会議のポリシー設定-オーディオ & ビデオ</span><span class="sxs-lookup"><span data-stu-id="b11fb-191">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="b11fb-192">議事録を許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-192">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="b11fb-193">クラウドの記録を許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-193">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="b11fb-194">IP ビデオを許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-194">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="b11fb-195">メディアのビットレート (KBs)</span><span class="sxs-lookup"><span data-stu-id="b11fb-195">Media bit rate (KBs)</span></span>](#media-bit-rate-kbs)

### <a name="allow-transcription"></a><span data-ttu-id="b11fb-196">議事録を許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-196">Allow transcription</span></span>

<span data-ttu-id="b11fb-197">これは、1つの開催者とユーザーごとのポリシーを組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="b11fb-197">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="b11fb-198">この設定では、会議のレコーディングの再生中にキャプションと議事録機能を使用できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-198">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="b11fb-199">この設定を無効にした場合、会議のレコーディングの再生中は、[**検索**] と [ **CC** ] オプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="b11fb-199">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="b11fb-200">レコーディングを開始したユーザーは、この設定をオンにして、レコーディングにも議事録を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-200">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span> 

<span data-ttu-id="b11fb-201">記録された会議の議事録は、現時点では、Teams の言語が英語に設定されているユーザー、および英語が会議で話されている場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-201">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![会議の [議事録] オプションを示すスクリーンショット](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="b11fb-203">クラウドの記録を許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-203">Allow cloud recording</span></span>

<span data-ttu-id="b11fb-204">これは、1つの開催者とユーザーごとのポリシーを組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="b11fb-204">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="b11fb-205">この設定は、このユーザーの会議を記録できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-205">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="b11fb-206">参加者のポリシー設定が有効になっている場合、または同じ組織から認証されたユーザーである場合は、レコーディングを会議の開催者または別の会議参加者が開始することができます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-206">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="b11fb-207">フェデレーションユーザーや匿名ユーザーなどの組織外のユーザーは、レコーディングを開始できません。</span><span class="sxs-lookup"><span data-stu-id="b11fb-207">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="b11fb-208">ゲストユーザーがレコーディングを開始または停止することはできません。</span><span class="sxs-lookup"><span data-stu-id="b11fb-208">Guest users can't start or stop the recording.</span></span> 

![レコーディングオプションが表示されたスクリーンショット](media/meeting-policies-recording.png)

<span data-ttu-id="b11fb-210">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="b11fb-210">Let's look at the following example.</span></span>

|<span data-ttu-id="b11fb-211">ユーザー</span><span class="sxs-lookup"><span data-stu-id="b11fb-211">User</span></span> |<span data-ttu-id="b11fb-212">会議のポリシー</span><span class="sxs-lookup"><span data-stu-id="b11fb-212">Meeting policy</span></span>  |<span data-ttu-id="b11fb-213">クラウドの記録を許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-213">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b11fb-214">Daniela</span><span class="sxs-lookup"><span data-stu-id="b11fb-214">Daniela</span></span> | <span data-ttu-id="b11fb-215">Global</span><span class="sxs-lookup"><span data-stu-id="b11fb-215">Global</span></span>   | <span data-ttu-id="b11fb-216">False</span><span class="sxs-lookup"><span data-stu-id="b11fb-216">False</span></span> |
|<span data-ttu-id="b11fb-217">Amanda</span><span class="sxs-lookup"><span data-stu-id="b11fb-217">Amanda</span></span> | <span data-ttu-id="b11fb-218">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="b11fb-218">Location1MeetingPolicy</span></span> | <span data-ttu-id="b11fb-219">True</span><span class="sxs-lookup"><span data-stu-id="b11fb-219">True</span></span>|
|<span data-ttu-id="b11fb-220">John (外部ユーザー)</span><span class="sxs-lookup"><span data-stu-id="b11fb-220">John (external user)</span></span> | <span data-ttu-id="b11fb-221">該当しない</span><span class="sxs-lookup"><span data-stu-id="b11fb-221">Not applicable</span></span> | <span data-ttu-id="b11fb-222">該当しない</span><span class="sxs-lookup"><span data-stu-id="b11fb-222">Not applicable</span></span>|

<span data-ttu-id="b11fb-223">Daniela によって開催された会議を記録することはできません。ポリシー設定が有効になっている場合は、Daniela で開催された会議を記録することはできません。</span><span class="sxs-lookup"><span data-stu-id="b11fb-223">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="b11fb-224">Amanda によって開催された会議を記録することはできますが、ポリシー設定が無効になっている、または外部ユーザーである John が、Amanda によって開催された会議を記録することはできません。 Daniela。</span><span class="sxs-lookup"><span data-stu-id="b11fb-224">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="b11fb-225">クラウド会議のレコーディングの詳細については、「 [Teams クラウド会議のレコーディング](cloud-recording.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b11fb-225">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="b11fb-226">IP ビデオを許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-226">Allow IP video</span></span>

<span data-ttu-id="b11fb-227">これは、1つの開催者とユーザーごとのポリシーを組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="b11fb-227">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="b11fb-228">ビデオは、会議の主要なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="b11fb-228">Video is a key component to meetings.</span></span> <span data-ttu-id="b11fb-229">一部の組織では、管理者がビデオを使用するユーザーの会議をさらに制御する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b11fb-229">In some organizations, admins might want more control over which users’ meetings have video.</span></span> <span data-ttu-id="b11fb-230">この設定では、ユーザーによってホストされている会議でビデオをオンにするかどうかを制御します。また、ユーザーが開始した1:1 通話とグループ通話にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-230">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="b11fb-231">このポリシーが有効になっているユーザーによって開催された会議は、会議参加者がポリシーを有効にしている場合は、会議参加者の会議でのビデオ共有を許可します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-231">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="b11fb-232">(匿名およびフェデレーション参加者などの) ポリシーが割り当てられていない会議の参加者は、会議の開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-232">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![音声とビデオの設定での会議を示すスクリーンショット](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="b11fb-234">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="b11fb-234">Let's look at the following example.</span></span>

|<span data-ttu-id="b11fb-235">ユーザー</span><span class="sxs-lookup"><span data-stu-id="b11fb-235">User</span></span> |<span data-ttu-id="b11fb-236">会議のポリシー</span><span class="sxs-lookup"><span data-stu-id="b11fb-236">Meeting policy</span></span>  |<span data-ttu-id="b11fb-237">IP ビデオを許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-237">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b11fb-238">Daniela</span><span class="sxs-lookup"><span data-stu-id="b11fb-238">Daniela</span></span>   | <span data-ttu-id="b11fb-239">Global</span><span class="sxs-lookup"><span data-stu-id="b11fb-239">Global</span></span>   | <span data-ttu-id="b11fb-240">True</span><span class="sxs-lookup"><span data-stu-id="b11fb-240">True</span></span>        |
|<span data-ttu-id="b11fb-241">Amanda</span><span class="sxs-lookup"><span data-stu-id="b11fb-241">Amanda</span></span>    | <span data-ttu-id="b11fb-242">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="b11fb-242">Location1MeetingPolicy</span></span>        | <span data-ttu-id="b11fb-243">False</span><span class="sxs-lookup"><span data-stu-id="b11fb-243">False</span></span>      |

<span data-ttu-id="b11fb-244">Daniela でホストされている会議では、ビデオをオンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-244">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="b11fb-245">Daniela は会議に参加して、ビデオをオンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-245">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="b11fb-246">Amanda のポリシーが [ビデオを許可しない] に設定されているため、Amanda は Daniela の会議でビデオを有効にできません。</span><span class="sxs-lookup"><span data-stu-id="b11fb-246">Amanda can't turn on video in Daniela's meeting because Amanda’s policy is set to not allow video.</span></span> <span data-ttu-id="b11fb-247">Amanda は、会議で他の参加者と共有されているビデオを表示できます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-247">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="b11fb-248">Amanda によってホストされている会議では、ユーザーに割り当てられているビデオポリシーに関係なく、誰もビデオをオンにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b11fb-248">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="b11fb-249">これは、Daniela Amanda の会議でビデオを有効にできないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-249">This means Daniela can't turn on video in Amanda’s meetings.</span></span>  

<span data-ttu-id="b11fb-250">Daniela がビデオで Amanda 通話を発信した場合、Amanda は音声のみで通話に応答できます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-250">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="b11fb-251">通話が接続されている場合、Amanda は Daniela のビデオを見ることはできますが、ビデオを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b11fb-251">When the call is connected, Amanda can see Daniela’s video, but can't turn on video.</span></span> <span data-ttu-id="b11fb-252">Amanda が Daniela 通話を発信すると、Daniela はビデオと音声で通話に応答できます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-252">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="b11fb-253">通話が接続されると、Daniela は、必要に応じて彼女のビデオをオンまたはオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-253">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="b11fb-254">メディアのビットレート (KBs)</span><span class="sxs-lookup"><span data-stu-id="b11fb-254">Media bit rate (KBs)</span></span>

<span data-ttu-id="b11fb-255">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="b11fb-255">This is a per-user policy.</span></span> <span data-ttu-id="b11fb-256">この設定は、ユーザーの通話と会議でのオーディオ、ビデオ、およびビデオベースのアプリ共有転送のメディアのビットレートを決定します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-256">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="b11fb-257">これは、通話または会議のユーザーに対して、アップリンクとダウンリンクメディアトラバーサルの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-257">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="b11fb-258">この設定により、組織内の帯域幅の管理をきめ細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-258">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="b11fb-259">ユーザーが必要とする会議シナリオによっては、優れた品質を実現するために十分な帯域幅を用意することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b11fb-259">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="b11fb-260">最小値は 30 Kbps で、最大値は会議シナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b11fb-260">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="b11fb-261">Teams での品質の高い会議、通話、ライブイベントに関する最低限の推奨帯域幅の詳細については、「[帯域幅要件](prepare-network.md#bandwidth-requirements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b11fb-261">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="b11fb-262">会議に十分な帯域幅がない場合、参加者には、ネットワークの品質低下を示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-262">If there isn’t enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="b11fb-263">最高品質のビデオエクスペリエンス (CEO ボード会議や Teams live イベントなど) が必要な会議の場合は、帯域幅を 10 Mbps に設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b11fb-263">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="b11fb-264">最大のエクスペリエンスが設定されている場合でも、シナリオによっては、特定のネットワーク条件が検出されると、Teams メディアスタックが低帯域幅の条件に合わせて調整されます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-264">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span> 

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="b11fb-265">会議のポリシー設定-コンテンツ共有</span><span class="sxs-lookup"><span data-stu-id="b11fb-265">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="b11fb-266">画面共有モード</span><span class="sxs-lookup"><span data-stu-id="b11fb-266">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="b11fb-267">参加者による制御を許可または要求する</span><span class="sxs-lookup"><span data-stu-id="b11fb-267">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="b11fb-268">外部参加者による制御の付与または要求を許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-268">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="b11fb-269">PowerPoint の共有を許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-269">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="b11fb-270">ホワイトボードを許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-270">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="b11fb-271">共有のノートを許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-271">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="b11fb-272">画面共有モード</span><span class="sxs-lookup"><span data-stu-id="b11fb-272">Screen sharing mode</span></span>

<span data-ttu-id="b11fb-273">これは、1つの開催者とユーザーごとのポリシーを組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="b11fb-273">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="b11fb-274">この設定は、ユーザーの会議でデスクトップとウィンドウの共有を許可するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-274">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="b11fb-275">(匿名、ゲスト、B2B、フェデレーション参加者などの) ポリシーが割り当てられていない会議の参加者は、会議の開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-275">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="b11fb-276">値の設定</span><span class="sxs-lookup"><span data-stu-id="b11fb-276">Setting value</span></span> |<span data-ttu-id="b11fb-277">動作</span><span class="sxs-lookup"><span data-stu-id="b11fb-277">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="b11fb-278">**画面全体**</span><span class="sxs-lookup"><span data-stu-id="b11fb-278">**Entire screen**</span></span>    | <span data-ttu-id="b11fb-279">完全なデスクトップ共有とアプリケーション共有が会議で許可されている</span><span class="sxs-lookup"><span data-stu-id="b11fb-279">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="b11fb-280">**1つのアプリケーション**</span><span class="sxs-lookup"><span data-stu-id="b11fb-280">**Single application**</span></span>   | <span data-ttu-id="b11fb-281">会議ではアプリケーション共有が許可されている</span><span class="sxs-lookup"><span data-stu-id="b11fb-281">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="b11fb-282">**無効**</span><span class="sxs-lookup"><span data-stu-id="b11fb-282">**Disabled**</span></span>     |<span data-ttu-id="b11fb-283">会議中に画面共有とアプリケーション共有が無効になりました。</span><span class="sxs-lookup"><span data-stu-id="b11fb-283">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="b11fb-284">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="b11fb-284">Let's look at the following example.</span></span>

|<span data-ttu-id="b11fb-285">ユーザー</span><span class="sxs-lookup"><span data-stu-id="b11fb-285">User</span></span> |<span data-ttu-id="b11fb-286">会議のポリシー</span><span class="sxs-lookup"><span data-stu-id="b11fb-286">Meeting policy</span></span> |<span data-ttu-id="b11fb-287">画面共有モード</span><span class="sxs-lookup"><span data-stu-id="b11fb-287">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b11fb-288">Daniela</span><span class="sxs-lookup"><span data-stu-id="b11fb-288">Daniela</span></span>  | <span data-ttu-id="b11fb-289">Global</span><span class="sxs-lookup"><span data-stu-id="b11fb-289">Global</span></span>   | <span data-ttu-id="b11fb-290">画面全体</span><span class="sxs-lookup"><span data-stu-id="b11fb-290">Entire screen</span></span> |
|<span data-ttu-id="b11fb-291">Amanda</span><span class="sxs-lookup"><span data-stu-id="b11fb-291">Amanda</span></span>   | <span data-ttu-id="b11fb-292">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="b11fb-292">Location1MeetingPolicy</span></span>  | <span data-ttu-id="b11fb-293">無効</span><span class="sxs-lookup"><span data-stu-id="b11fb-293">Disabled</span></span> |

<span data-ttu-id="b11fb-294">Daniela によってホストされている会議により、会議の参加者は画面全体または特定のアプリケーションを共有できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b11fb-294">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="b11fb-295">Amanda が Daniela の会議に参加している場合は、そのポリシー設定が無効になっているために、Amanda が自分の画面や特定のアプリケーションを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="b11fb-295">If Amanda joins Daniela’s meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="b11fb-296">Amanda によってホストされている会議では、画面共有モードポリシーが割り当てられているかどうかに関係なく、1つのアプリを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="b11fb-296">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="b11fb-297">これは、Daniela が Amanda の会議で、画面や単一のアプリケーションを共有できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-297">This means that Daniela can't share her screen or a single application in Amanda’s meetings.</span></span>  

<span data-ttu-id="b11fb-298">現時点では、ユーザーが Google Chrome を使用している場合は、Teams 会議でビデオを再生したり、画面を共有したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b11fb-298">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="b11fb-299">参加者による制御を許可または要求する</span><span class="sxs-lookup"><span data-stu-id="b11fb-299">Allow a participant to give or request control</span></span>

<span data-ttu-id="b11fb-300">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="b11fb-300">This is a per-user policy.</span></span> <span data-ttu-id="b11fb-301">この設定は、ユーザーが共有デスクトップまたはウィンドウの制御を他の会議参加者に対して許可できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-301">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="b11fb-302">コントロールを指定するには、画面の上部にマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-302">To give control, hover over the top of the screen.</span></span> 

<span data-ttu-id="b11fb-303">ユーザーに対してこの設定をオンにすると、共有セッションのトップバーに [**制御を渡す**] オプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-303">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span> 

![[制御を渡す] オプションが表示されたスクリーンショット](media/meeting-policies-give-control.png)

<span data-ttu-id="b11fb-305">ユーザーに対して設定を無効にした場合は、[**制御を渡す**] オプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="b11fb-305">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![[制御を渡す] オプションが使用できないことを示すスクリーンショット](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="b11fb-307">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="b11fb-307">Let's look at the following example.</span></span>

|<span data-ttu-id="b11fb-308">ユーザー</span><span class="sxs-lookup"><span data-stu-id="b11fb-308">User</span></span> |<span data-ttu-id="b11fb-309">会議のポリシー</span><span class="sxs-lookup"><span data-stu-id="b11fb-309">Meeting policy</span></span>  |<span data-ttu-id="b11fb-310">参加者にコントロールの譲渡または要求を許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-310">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b11fb-311">Daniela</span><span class="sxs-lookup"><span data-stu-id="b11fb-311">Daniela</span></span>   | <span data-ttu-id="b11fb-312">Global</span><span class="sxs-lookup"><span data-stu-id="b11fb-312">Global</span></span>   | <span data-ttu-id="b11fb-313">True</span><span class="sxs-lookup"><span data-stu-id="b11fb-313">True</span></span>       |
|<span data-ttu-id="b11fb-314">Babek</span><span class="sxs-lookup"><span data-stu-id="b11fb-314">Babek</span></span>    | <span data-ttu-id="b11fb-315">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="b11fb-315">Location1MeetingPolicy</span></span>        | <span data-ttu-id="b11fb-316">False</span><span class="sxs-lookup"><span data-stu-id="b11fb-316">False</span></span>   |

<span data-ttu-id="b11fb-317">Daniela は、Babek によって開催された会議の他の参加者と共有しているデスクトップまたはウィンドウを制御できますが、Babek は他の参加者に制御を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="b11fb-317">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="b11fb-318">PowerShell を使用して、制御を提供できるユーザーと制御要求を受け入れるユーザーを制御するには、AllowParticipantGiveRequestControl コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-318">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="b11fb-319">共有中に共有コンテンツの制御を行うには、両方の当事者が Teams デスクトップクライアントを使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b11fb-319">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="b11fb-320">いずれかの当事者がブラウザーで Teams を実行している場合、制御はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="b11fb-320">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="b11fb-321">これは、修正する予定の技術的制限によるものです。</span><span class="sxs-lookup"><span data-stu-id="b11fb-321">This is due to a technical limitation that we're planning to fix.</span></span> 

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="b11fb-322">外部参加者による制御の付与または要求を許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-322">Allow an external participant to give or request control</span></span>

<span data-ttu-id="b11fb-323">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="b11fb-323">This is a per-user policy.</span></span> <span data-ttu-id="b11fb-324">この設定では、会議の外部参加者が、共有しているデスクトップまたはウィンドウを会議の他の参加者に対して管理できるようにするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-324">This setting controls whether external participants in a meeting can give control of their shared desktop or window to other participants in the meeting.</span></span> <span data-ttu-id="b11fb-325">Teams 会議の外部参加者は、次のように分類されます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-325">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="b11fb-326">匿名ユーザー</span><span class="sxs-lookup"><span data-stu-id="b11fb-326">Anonymous user</span></span>
- <span data-ttu-id="b11fb-327">ゲスト ユーザー</span><span class="sxs-lookup"><span data-stu-id="b11fb-327">Guest users</span></span>  
- <span data-ttu-id="b11fb-328">B2B ユーザー</span><span class="sxs-lookup"><span data-stu-id="b11fb-328">B2B user</span></span>
- <span data-ttu-id="b11fb-329">フェデレーションされたユーザー</span><span class="sxs-lookup"><span data-stu-id="b11fb-329">Federated user</span></span>  

<span data-ttu-id="b11fb-330">フェデレーションされたユーザーが外部ユーザーに制御を渡すことができるかどうかは、「外部参加者による組織の制御設定の**付与または要求**」によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-330">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="b11fb-331">PowerShell を使用して外部の参加者が制御要求を許可するか制御要求を受け入れるかを制御するには、AllowExternalParticipantGiveRequestControl コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-331">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="b11fb-332">PowerPoint の共有を許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-332">Allow PowerPoint sharing</span></span>

<span data-ttu-id="b11fb-333">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="b11fb-333">This is a per-user policy.</span></span> <span data-ttu-id="b11fb-334">この設定は、ユーザーが PowerPoint スライドデッキを会議で共有できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-334">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="b11fb-335">匿名、ゲスト、フェデレーションユーザーなどの外部ユーザーは、会議の開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-335">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="b11fb-336">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="b11fb-336">Let's look at the following example.</span></span>

|<span data-ttu-id="b11fb-337">ユーザー</span><span class="sxs-lookup"><span data-stu-id="b11fb-337">User</span></span> |<span data-ttu-id="b11fb-338">会議のポリシー</span><span class="sxs-lookup"><span data-stu-id="b11fb-338">Meeting policy</span></span>  |<span data-ttu-id="b11fb-339">PowerPoint の共有を許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-339">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b11fb-340">Daniela</span><span class="sxs-lookup"><span data-stu-id="b11fb-340">Daniela</span></span>   | <span data-ttu-id="b11fb-341">Global</span><span class="sxs-lookup"><span data-stu-id="b11fb-341">Global</span></span>   | <span data-ttu-id="b11fb-342">True</span><span class="sxs-lookup"><span data-stu-id="b11fb-342">True</span></span>       |
|<span data-ttu-id="b11fb-343">Amanda</span><span class="sxs-lookup"><span data-stu-id="b11fb-343">Amanda</span></span>   | <span data-ttu-id="b11fb-344">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="b11fb-344">Location1MeetingPolicy</span></span>        | <span data-ttu-id="b11fb-345">False</span><span class="sxs-lookup"><span data-stu-id="b11fb-345">False</span></span>   |

<span data-ttu-id="b11fb-346">Amanda が会議の開催者であっても、会議で PowerPoint スライドデッキを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="b11fb-346">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="b11fb-347">Daniela は、Amanda によって会議が開催されている場合でも、PowerPoint スライドデッキを共有できます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-347">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="b11fb-348">Amanda は、PowerPoint スライドデッキを共有できない場合でも、会議中に他のユーザーと共有している PowerPoint スライドデッキを表示できます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-348">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="b11fb-349">ホワイトボードを許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-349">Allow whiteboard</span></span>

<span data-ttu-id="b11fb-350">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="b11fb-350">This is a per-user policy.</span></span> <span data-ttu-id="b11fb-351">この設定は、ユーザーが会議でホワイトボードを共有できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-351">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="b11fb-352">匿名、B2B、フェデレーションユーザーなどの外部ユーザーは、会議の開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-352">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> 

<span data-ttu-id="b11fb-353">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="b11fb-353">Let's look at the following example.</span></span>

|<span data-ttu-id="b11fb-354">ユーザー</span><span class="sxs-lookup"><span data-stu-id="b11fb-354">User</span></span> |<span data-ttu-id="b11fb-355">会議のポリシー</span><span class="sxs-lookup"><span data-stu-id="b11fb-355">Meeting policy</span></span>  |<span data-ttu-id="b11fb-356">ホワイトボードを許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-356">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="b11fb-357">Daniela</span><span class="sxs-lookup"><span data-stu-id="b11fb-357">Daniela</span></span>   | <span data-ttu-id="b11fb-358">Global</span><span class="sxs-lookup"><span data-stu-id="b11fb-358">Global</span></span>   | <span data-ttu-id="b11fb-359">True</span><span class="sxs-lookup"><span data-stu-id="b11fb-359">True</span></span>       |
|<span data-ttu-id="b11fb-360">Amanda</span><span class="sxs-lookup"><span data-stu-id="b11fb-360">Amanda</span></span>   | <span data-ttu-id="b11fb-361">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="b11fb-361">Location1MeetingPolicy</span></span>        | <span data-ttu-id="b11fb-362">False</span><span class="sxs-lookup"><span data-stu-id="b11fb-362">False</span></span>   |

<span data-ttu-id="b11fb-363">Amanda が会議の開催者である場合でも、会議でホワイトボードを共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="b11fb-363">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="b11fb-364">Daniela は、会議が Amanda によって開催されている場合でも、ホワイトボードを共有できます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-364">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="b11fb-365">共有のノートを許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-365">Allow shared notes</span></span>

<span data-ttu-id="b11fb-366">これは、ユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="b11fb-366">This is a per-user policy.</span></span> <span data-ttu-id="b11fb-367">この設定では、ユーザーが会議でノートを作成して共有できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-367">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="b11fb-368">匿名、B2B、フェデレーションユーザーなどの外部ユーザーは、会議の開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-368">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="b11fb-369">現在、[**会議メモ**] タブは、参加者が20人未満の会議でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b11fb-369">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span>

<span data-ttu-id="b11fb-370">次の例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="b11fb-370">Let's look at the following example.</span></span>

|<span data-ttu-id="b11fb-371">ユーザー</span><span class="sxs-lookup"><span data-stu-id="b11fb-371">User</span></span> |<span data-ttu-id="b11fb-372">会議のポリシー</span><span class="sxs-lookup"><span data-stu-id="b11fb-372">Meeting policy</span></span>  |<span data-ttu-id="b11fb-373">共有のノートを許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-373">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b11fb-374">Daniela</span><span class="sxs-lookup"><span data-stu-id="b11fb-374">Daniela</span></span>   | <span data-ttu-id="b11fb-375">Global</span><span class="sxs-lookup"><span data-stu-id="b11fb-375">Global</span></span>   | <span data-ttu-id="b11fb-376">True</span><span class="sxs-lookup"><span data-stu-id="b11fb-376">True</span></span>       |
|<span data-ttu-id="b11fb-377">Amanda</span><span class="sxs-lookup"><span data-stu-id="b11fb-377">Amanda</span></span>   | <span data-ttu-id="b11fb-378">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="b11fb-378">Location1MeetingPolicy</span></span> | <span data-ttu-id="b11fb-379">False</span><span class="sxs-lookup"><span data-stu-id="b11fb-379">False</span></span> |

<span data-ttu-id="b11fb-380">Daniela は Amanda の会議でノートを取ることができ、Amanda はどの会議でもノートを取ることができません。</span><span class="sxs-lookup"><span data-stu-id="b11fb-380">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="b11fb-381">会議のポリシー設定-ゲスト & 参加者</span><span class="sxs-lookup"><span data-stu-id="b11fb-381">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="b11fb-382">これらの設定では、参加者が会議に参加する前に、ロビーで待機する会議の参加者と、会議で許可されている参加のレベルを制御します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-382">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="b11fb-383">匿名ユーザーが会議を開始できるようにする</span><span class="sxs-lookup"><span data-stu-id="b11fb-383">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="b11fb-384">ユーザーを自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-384">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="b11fb-385">ダイヤルインユーザーがロビーをバイパスすることを許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-385">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="b11fb-386">プライベート会議で今すぐ会議を許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-386">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)
- [<span data-ttu-id="b11fb-387">ライブキャプションを有効にする</span><span class="sxs-lookup"><span data-stu-id="b11fb-387">Enable live captions </span></span>](#enable-live-captions)
- [<span data-ttu-id="b11fb-388">会議でチャットを許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-388">Allow chat in meetings </span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="b11fb-389">会議に参加するためのオプションは、各 Teams グループの設定と接続方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="b11fb-389">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="b11fb-390">グループに電話会議があり、それを使用して接続する場合は、「 [Office 365 の電話会議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b11fb-390">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="b11fb-391">Teams グループに電話会議がない場合は、「 [teams で会議に参加する」](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b11fb-391">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="b11fb-392">匿名ユーザーが会議を開始できるようにする</span><span class="sxs-lookup"><span data-stu-id="b11fb-392">Let anonymous people start a meeting</span></span>

<span data-ttu-id="b11fb-393">これは開催者ごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="b11fb-393">This is a per-organizer policy.</span></span> <span data-ttu-id="b11fb-394">この設定では、組織の承認されたユーザーが参加していない場合に、そのユーザーの会議に参加できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-394">This setting controls whether anonymous people, including B2B, and federated users, can join the user's meeting without an authenticated user from the organization in attendance.</span></span> 

![待機中のユーザーへのメッセージを示すスクリーンショット](media/meeting-policies-anonymous-user-lobby.png)

<span data-ttu-id="b11fb-396">認証されたユーザーが会議に存在する場合の、匿名ユーザーの結合動作を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-396">Here's the join behavior of anonymous people when authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="b11fb-397">匿名ユーザーが会議を開始できるようにする</span><span class="sxs-lookup"><span data-stu-id="b11fb-397">Let anonymous people start a meeting</span></span>  |<span data-ttu-id="b11fb-398">ユーザーを自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-398">Automatically admit people</span></span> |<span data-ttu-id="b11fb-399">匿名ユーザーの参加動作</span><span class="sxs-lookup"><span data-stu-id="b11fb-399">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b11fb-400">True</span><span class="sxs-lookup"><span data-stu-id="b11fb-400">True</span></span>    | <span data-ttu-id="b11fb-401">すべて</span><span class="sxs-lookup"><span data-stu-id="b11fb-401">Everyone</span></span>      | <span data-ttu-id="b11fb-402">直接参加</span><span class="sxs-lookup"><span data-stu-id="b11fb-402">Join directly</span></span>         |
|   | <span data-ttu-id="b11fb-403">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="b11fb-403">Everyone in your organization</span></span>       | <span data-ttu-id="b11fb-404">ロビーで待機する</span><span class="sxs-lookup"><span data-stu-id="b11fb-404">Wait in lobby</span></span>        |
|   | <span data-ttu-id="b11fb-405">組織内のすべてのユーザーとフェデレーション組織</span><span class="sxs-lookup"><span data-stu-id="b11fb-405">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="b11fb-406">ロビーで待機する</span><span class="sxs-lookup"><span data-stu-id="b11fb-406">Wait in lobby</span></span>         |
|<span data-ttu-id="b11fb-407">False</span><span class="sxs-lookup"><span data-stu-id="b11fb-407">False</span></span>    | <span data-ttu-id="b11fb-408">すべて</span><span class="sxs-lookup"><span data-stu-id="b11fb-408">Everyone</span></span>        | <span data-ttu-id="b11fb-409">直接参加</span><span class="sxs-lookup"><span data-stu-id="b11fb-409">Join directly</span></span>        |
|   | <span data-ttu-id="b11fb-410">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="b11fb-410">Everyone in your organization</span></span>     | <span data-ttu-id="b11fb-411">ロビーで待機する</span><span class="sxs-lookup"><span data-stu-id="b11fb-411">Wait in lobby</span></span>        |
|   | <span data-ttu-id="b11fb-412">組織内のすべてのユーザーとフェデレーション組織</span><span class="sxs-lookup"><span data-stu-id="b11fb-412">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="b11fb-413">ロビーで待機する</span><span class="sxs-lookup"><span data-stu-id="b11fb-413">Wait in lobby</span></span>         |

<span data-ttu-id="b11fb-414">認証されたユーザーが会議に存在しない場合の、匿名ユーザーの結合動作を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-414">Here's the join behavior of anonymous people when no authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="b11fb-415">匿名ユーザーが会議を開始できるようにする</span><span class="sxs-lookup"><span data-stu-id="b11fb-415">Let anonymous people start a meeting</span></span> |<span data-ttu-id="b11fb-416">ユーザーを自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-416">Automatically admit people</span></span>  |<span data-ttu-id="b11fb-417">匿名ユーザーの参加動作</span><span class="sxs-lookup"><span data-stu-id="b11fb-417">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b11fb-418">True</span><span class="sxs-lookup"><span data-stu-id="b11fb-418">True</span></span>    | <span data-ttu-id="b11fb-419">すべて</span><span class="sxs-lookup"><span data-stu-id="b11fb-419">Everyone</span></span>      | <span data-ttu-id="b11fb-420">直接参加</span><span class="sxs-lookup"><span data-stu-id="b11fb-420">Join directly</span></span>         |
|   | <span data-ttu-id="b11fb-421">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="b11fb-421">Everyone in your organization</span></span>       | <span data-ttu-id="b11fb-422">ロビーで待機する</span><span class="sxs-lookup"><span data-stu-id="b11fb-422">Wait in lobby</span></span>        |
|   | <span data-ttu-id="b11fb-423">組織内のすべてのユーザーとフェデレーション組織</span><span class="sxs-lookup"><span data-stu-id="b11fb-423">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="b11fb-424">ロビーで待機する</span><span class="sxs-lookup"><span data-stu-id="b11fb-424">Wait in lobby</span></span>         |
|<span data-ttu-id="b11fb-425">False</span><span class="sxs-lookup"><span data-stu-id="b11fb-425">False</span></span>    | <span data-ttu-id="b11fb-426">すべて</span><span class="sxs-lookup"><span data-stu-id="b11fb-426">Everyone</span></span>        | <span data-ttu-id="b11fb-427">ロビーで待機します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-427">Wait in lobby.</span></span> <span data-ttu-id="b11fb-428">最初の認証済みのユーザーが会議に参加すると、ユーザーは自動的に許可されます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-428">Users are automatically admitted when the first authenticated user joins the meeting.</span></span>        |
|   | <span data-ttu-id="b11fb-429">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="b11fb-429">Everyone in your organization</span></span>     |<span data-ttu-id="b11fb-430">ロビーで待機する</span><span class="sxs-lookup"><span data-stu-id="b11fb-430">Wait in lobby</span></span>         |
|   | <span data-ttu-id="b11fb-431">組織内のすべてのユーザーとフェデレーション組織</span><span class="sxs-lookup"><span data-stu-id="b11fb-431">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="b11fb-432">ロビーで待機する</span><span class="sxs-lookup"><span data-stu-id="b11fb-432">Wait in lobby</span></span>         |

### <a name="automatically-admit-people"></a><span data-ttu-id="b11fb-433">ユーザーを自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-433">Automatically admit people</span></span>

<span data-ttu-id="b11fb-434">これは開催者ごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="b11fb-434">This is a per-organizer policy.</span></span> <span data-ttu-id="b11fb-435">この設定では、ユーザーが会議に直接参加するか、認証されたユーザーに許可されるまでロビーで待機するかを制御します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-435">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span>

![ロビー内のユーザーとの会議を示すスクリーンショット](media/meeting-policies-lobby.png)

 <span data-ttu-id="b11fb-437">会議の開催者は、会議出席依頼の [**会議オプション**] をクリックして、スケジュールする会議ごとにこの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-437">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span> <span data-ttu-id="b11fb-438">**(近日公開)**</span><span class="sxs-lookup"><span data-stu-id="b11fb-438">**(coming soon)**</span></span>
  
|<span data-ttu-id="b11fb-439">値の設定</span><span class="sxs-lookup"><span data-stu-id="b11fb-439">Setting value</span></span>  |<span data-ttu-id="b11fb-440">結合動作</span><span class="sxs-lookup"><span data-stu-id="b11fb-440">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="b11fb-441">**すべて**</span><span class="sxs-lookup"><span data-stu-id="b11fb-441">**Everyone**</span></span>   |<span data-ttu-id="b11fb-442">すべての会議参加者が、ロビーで待たずに会議に直接参加します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-442">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="b11fb-443">これには、認証済みユーザー、フェデレーションされたユーザー、ゲスト、匿名ユーザー、電話でダイヤルインするユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-443">This includes authenticated users, federated users, guests, anonymous users, and people who dial in by phone.</span></span>       |
|<span data-ttu-id="b11fb-444">**組織内のすべてのユーザーとフェデレーション組織**</span><span class="sxs-lookup"><span data-stu-id="b11fb-444">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="b11fb-445">組織内で認証されたユーザー (ゲストユーザーやフェデレーションされた組織のユーザーを含む) は、ロビーで待機することなく直接会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-445">Authenticated users within the organization, including guest users and the users from federated organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="b11fb-446">ロビーで電話で通話を発信する匿名ユーザーとユーザー。</span><span class="sxs-lookup"><span data-stu-id="b11fb-446">Anonymous users and users who dial in by phone wait in the lobby.</span></span>   |
|<span data-ttu-id="b11fb-447">**組織内のすべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="b11fb-447">**Everyone in your organization**</span></span>    |<span data-ttu-id="b11fb-448">ゲストユーザーを含む、組織内から認証されたユーザーは、ロビーで待たずに会議に直接参加できます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-448">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="b11fb-449">フェデレーションされたユーザー、匿名ユーザー、およびロビーで電話で通話を発信するユーザー。</span><span class="sxs-lookup"><span data-stu-id="b11fb-449">Federated users, anonymous users, and users who dial in by phone wait in the lobby.</span></span>           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="b11fb-450">ダイヤルインユーザーがロビーをバイパスすることを許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-450">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="b11fb-451">これは開催者ごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="b11fb-451">This is a per-organizer policy.</span></span> <span data-ttu-id="b11fb-452">この設定では、電話でダイヤルインするユーザーが会議に直接参加するか、[ユーザーの**自動**許可] 設定に関係なくロビーで待機するかを制御します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-452">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span>

<span data-ttu-id="b11fb-453">電話でダイヤルインするユーザーの結合動作を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-453">Here's the join behavior of people who dial in by phone.</span></span>

|<span data-ttu-id="b11fb-454">ダイヤルインユーザーがロビーをバイパスすることを許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-454">Allow dial-in users to bypass the lobby</span></span>  |<span data-ttu-id="b11fb-455">ユーザーを自動的に許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-455">Automatically admit people</span></span>  |<span data-ttu-id="b11fb-456">ダイヤルインするユーザーの参加動作</span><span class="sxs-lookup"><span data-stu-id="b11fb-456">Join behavior of people who dial in</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b11fb-457">True</span><span class="sxs-lookup"><span data-stu-id="b11fb-457">True</span></span>    | <span data-ttu-id="b11fb-458">すべて</span><span class="sxs-lookup"><span data-stu-id="b11fb-458">Everyone</span></span>      | <span data-ttu-id="b11fb-459">直接参加</span><span class="sxs-lookup"><span data-stu-id="b11fb-459">Join directly</span></span>         |
|   | <span data-ttu-id="b11fb-460">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="b11fb-460">Everyone in your organization</span></span>       | <span data-ttu-id="b11fb-461">直接参加</span><span class="sxs-lookup"><span data-stu-id="b11fb-461">Join directly</span></span>        |
|   | <span data-ttu-id="b11fb-462">組織内のすべてのユーザーとフェデレーション組織</span><span class="sxs-lookup"><span data-stu-id="b11fb-462">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="b11fb-463">直接参加</span><span class="sxs-lookup"><span data-stu-id="b11fb-463">Join directly</span></span>         |
|<span data-ttu-id="b11fb-464">False</span><span class="sxs-lookup"><span data-stu-id="b11fb-464">False</span></span>    | <span data-ttu-id="b11fb-465">すべて</span><span class="sxs-lookup"><span data-stu-id="b11fb-465">Everyone</span></span>        | <span data-ttu-id="b11fb-466">直接参加</span><span class="sxs-lookup"><span data-stu-id="b11fb-466">Join directly</span></span>        |
|   | <span data-ttu-id="b11fb-467">組織内のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="b11fb-467">Everyone in your organization</span></span>     |<span data-ttu-id="b11fb-468">ロビーで待機する</span><span class="sxs-lookup"><span data-stu-id="b11fb-468">Wait in lobby</span></span>         |
|   | <span data-ttu-id="b11fb-469">組織内のすべてのユーザーとフェデレーション組織</span><span class="sxs-lookup"><span data-stu-id="b11fb-469">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="b11fb-470">ロビーで待機する</span><span class="sxs-lookup"><span data-stu-id="b11fb-470">Wait in lobby</span></span>         |

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="b11fb-471">プライベート会議で今すぐ会議を許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-471">Allow Meet now in private meetings</span></span>

<span data-ttu-id="b11fb-472">これはユーザーごとのポリシーであり、会議が開始される前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-472">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="b11fb-473">この設定は、ユーザーが臨時のプライベート会議を開始できるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-473">This setting controls whether a user can start an ad hoc private meeting.</span></span> 

### <a name="enable-live-captions"></a><span data-ttu-id="b11fb-474">ライブキャプションを有効にする</span><span class="sxs-lookup"><span data-stu-id="b11fb-474">Enable live captions</span></span>

<span data-ttu-id="b11fb-475">これはユーザーごとのポリシーであり、会議中に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b11fb-475">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="b11fb-476">この設定では、ユーザーが会議のライブキャプションを有効**または無効**にするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-476">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![[ライブキャプションを有効にする] オプションを示すスクリーンショット](media/meeting-policies-live-captions.png)

|<span data-ttu-id="b11fb-478">値の設定</span><span class="sxs-lookup"><span data-stu-id="b11fb-478">Setting value</span></span> |<span data-ttu-id="b11fb-479">動作</span><span class="sxs-lookup"><span data-stu-id="b11fb-479">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="b11fb-480">**無効 (開催者は上書き可能)**</span><span class="sxs-lookup"><span data-stu-id="b11fb-480">**Disabled but the organizer can override**</span></span>     | <span data-ttu-id="b11fb-481">会議中は、ユーザーに対してライブキャプションが自動的に有効になりません。</span><span class="sxs-lookup"><span data-stu-id="b11fb-481">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="b11fb-482">ユーザーには、オーバーフロー (**...**) メニューの [**ライブキャプションを有効**にする] オプションが表示され、有効にします。</span><span class="sxs-lookup"><span data-stu-id="b11fb-482">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="b11fb-483">これは、既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="b11fb-483">This is the default setting.</span></span> |
|<span data-ttu-id="b11fb-484">**無効**</span><span class="sxs-lookup"><span data-stu-id="b11fb-484">**Disabled**</span></span>     | <span data-ttu-id="b11fb-485">会議中にユーザーに対してライブキャプションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="b11fb-485">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="b11fb-486">ユーザーには、有効にするオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="b11fb-486">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="b11fb-487"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="b11fb-487"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="b11fb-488">会議でチャットを許可する</span><span class="sxs-lookup"><span data-stu-id="b11fb-488">Allow chat in meetings</span></span>

<span data-ttu-id="b11fb-489">これは開催者ごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="b11fb-489">This is a per-organizer policy.</span></span> <span data-ttu-id="b11fb-490">この設定は、ユーザーの会議で会議チャットを許可するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="b11fb-490">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="b11fb-491"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="b11fb-491"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="related-topics"></a><span data-ttu-id="b11fb-492">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b11fb-492">Related topics</span></span>

[<span data-ttu-id="b11fb-493">Teams のメッセージポリシー</span><span class="sxs-lookup"><span data-stu-id="b11fb-493">Messaging policies in Teams</span></span>](messaging-policies-in-teams.md)
