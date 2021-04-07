---
title: 会議ポリシーを管理する
author: CarolynRowe
ms.author: crowe
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
- seo-marvel-apr2020
description: Teams で会議ポリシーの設定を管理する方法について説明します。また、会議ポリシーの設定を使用して、ユーザーがスケジュールした会議の参加者に対して利用できる機能を制御します。
ms.openlocfilehash: d9f403625225711cb21245ca01262d3c0140063f
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598761"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="76b3d-103">Teams での会議ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="76b3d-103">Manage meeting policies in Teams</span></span>

<span data-ttu-id="76b3d-104"><a name="bkautomatically-admit-people"> </a></span><span class="sxs-lookup"><span data-stu-id="76b3d-104"><a name="bkautomatically-admit-people"> </a></span></span>

<span data-ttu-id="76b3d-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span><span class="sxs-lookup"><span data-stu-id="76b3d-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span></span>

<span data-ttu-id="76b3d-106"><a name="bkallow-transcription"> </a></span><span class="sxs-lookup"><span data-stu-id="76b3d-106"><a name="bkallow-transcription"> </a></span></span>

<span data-ttu-id="76b3d-107">会議ポリシーは、組織内のユーザーによってスケジュールされた会議への参加者が利用できる機能を制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="76b3d-107">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="76b3d-108">自動的に作成されるグローバル (組織全体の既定) ポリシーを使用することも、カスタム ポリシーを作成して割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="76b3d-108">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="76b3d-109">会議ポリシーは、Microsoft Teams 管理センターで管理するか、[PowerShell](teams-powershell-overview.md) を使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="76b3d-109">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="76b3d-110">ロールを使用して、会議の発表者や出席者の権限を管理する方法の詳細については、「[Teams会議の役割](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76b3d-110">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="76b3d-111">次の方法でポリシーを実装できます。これらの方法は、会議の開始前、会議中、または会議後のユーザーの会議エクスペリエンスに影響します。</span><span class="sxs-lookup"><span data-stu-id="76b3d-111">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="76b3d-112">実装の種類</span><span class="sxs-lookup"><span data-stu-id="76b3d-112">Implementation type</span></span>  |<span data-ttu-id="76b3d-113">説明</span><span class="sxs-lookup"><span data-stu-id="76b3d-113">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="76b3d-114">開催者単位</span><span class="sxs-lookup"><span data-stu-id="76b3d-114">Per-organizer</span></span>    |<span data-ttu-id="76b3d-115">開催者単位のポリシーを実装すると、すべての参加者は開催者のポリシーを継承します。</span><span class="sxs-lookup"><span data-stu-id="76b3d-115">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="76b3d-116">たとえば、[**ユーザーの参加を自動的に許可する**] は、開催者単位のポリシーであり、ユーザーが会議に直接参加するか、ポリシーが割り当てられたユーザーがスケジュールした会議をロビーで待機するかを制御します。</span><span class="sxs-lookup"><span data-stu-id="76b3d-116">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="76b3d-117">ユーザーごと</span><span class="sxs-lookup"><span data-stu-id="76b3d-117">Per-user</span></span>    |<span data-ttu-id="76b3d-118">ユーザーごとのポリシーを実装すると、ユーザーごとのポリシーのみが適用され、開催者や会議参加者に対する特定の機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="76b3d-118">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="76b3d-119">たとえば、[**チャネルで "今すぐ会議" を許可する**] は、ユーザー単位のポリシーです。</span><span class="sxs-lookup"><span data-stu-id="76b3d-119">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="76b3d-120">開催者単位およびユーザーごと</span><span class="sxs-lookup"><span data-stu-id="76b3d-120">Per-organizer and per-user</span></span>     |<span data-ttu-id="76b3d-121">開催者単位とユーザー単位のポリシーを組み合わせて実装すると、会議の参加者はユーザーのポリシーと開催者のポリシーに基づいて特定の機能が制限されます。</span><span class="sxs-lookup"><span data-stu-id="76b3d-121">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="76b3d-122">たとえば、[**クラウド記録を許可する**] は、開催者単位およびユーザーごとのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="76b3d-122">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="76b3d-123">この設定をオンにすると、会議の開催者と参加者は記録の開始と停止が可能になります。</span><span class="sxs-lookup"><span data-stu-id="76b3d-123">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="76b3d-124">グローバル ポリシーの設定を編集したり、1 つまたは複数のカスタム ポリシーを作成して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="76b3d-124">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="76b3d-125">カスタム ポリシーを作成して割り当てていない場合、ユーザーにはグローバル ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="76b3d-125">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="76b3d-126">[会議の詳細] ボタンは、ユーザーがオーディオ会議ライセンスを有効にしているか、ユーザーがオーディオ会議に許可されている場合に使用できます。それ以外の場合、会議の詳細は利用できません。</span><span class="sxs-lookup"><span data-stu-id="76b3d-126">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="76b3d-127">カスタムのチーム ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="76b3d-127">Create a custom meeting policy</span></span>

1. <span data-ttu-id="76b3d-128">Microsoft Teams 管理センターの左側のナビゲーションで、[**会議**]  >  [**会議ポリシー**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="76b3d-128">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="76b3d-129">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76b3d-129">Click **Add**.</span></span>
3. <span data-ttu-id="76b3d-130">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="76b3d-130">Enter a name and description for the policy.</span></span> <span data-ttu-id="76b3d-131">名前に特殊文字を含めたり、64 文字より長くすることはできません。</span><span class="sxs-lookup"><span data-stu-id="76b3d-131">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="76b3d-132">希望する設定を選びます。</span><span class="sxs-lookup"><span data-stu-id="76b3d-132">Choose the settings that you want.</span></span>
5. <span data-ttu-id="76b3d-133">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76b3d-133">Click **Save**.</span></span>

<span data-ttu-id="76b3d-134">たとえば、多数のユーザーがいて、会議に必要な帯域幅を制限するとします。</span><span class="sxs-lookup"><span data-stu-id="76b3d-134">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="76b3d-135">「制限された帯域幅」という名前の新しいカスタム ポリシーを作成し、次の設定を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="76b3d-135">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="76b3d-136">[**オーディオとビデオ**] で、</span><span class="sxs-lookup"><span data-stu-id="76b3d-136">Under **Audio & video**:</span></span>

- <span data-ttu-id="76b3d-137">[クラウド記録を許可する] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="76b3d-137">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="76b3d-138">[IP のビデオを許可する] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="76b3d-138">Turn off Allow IP video.</span></span>

<span data-ttu-id="76b3d-139">[**コンテンツの共有**] で、</span><span class="sxs-lookup"><span data-stu-id="76b3d-139">Under **Content sharing**:</span></span>

- <span data-ttu-id="76b3d-140">画面共有モードを無効にします。</span><span class="sxs-lookup"><span data-stu-id="76b3d-140">Disable screen sharing mode.</span></span>
- <span data-ttu-id="76b3d-141">[ホワイトボードを許可] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="76b3d-141">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="76b3d-142">[メモの共有を許可する] を無効にします。</span><span class="sxs-lookup"><span data-stu-id="76b3d-142">Turn off Allow shared notes.</span></span>

<span data-ttu-id="76b3d-143">その後、ポリシーをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="76b3d-143">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="76b3d-144">会議 ポリシーの編集</span><span class="sxs-lookup"><span data-stu-id="76b3d-144">Edit a meeting policy</span></span>

<span data-ttu-id="76b3d-145">グローバル ポリシーおよび作成したカスタム ポリシーを編集できます。</span><span class="sxs-lookup"><span data-stu-id="76b3d-145">You can edit the global policy and any custom policies that you create.</span></span>

1. <span data-ttu-id="76b3d-146">Microsoft Teams 管理センターの左側のナビゲーションで、[**会議**]  >  [**会議ポリシー**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="76b3d-146">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="76b3d-147">ポリシー名の左側をクリックしてポリシーを選び、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76b3d-147">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="76b3d-148">ここで、希望する変更を行います。</span><span class="sxs-lookup"><span data-stu-id="76b3d-148">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="76b3d-149">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76b3d-149">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="76b3d-150">ユーザーに割り当てることができる会議ポリシーは一度に 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="76b3d-150">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="76b3d-151">ユーザーに会議ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="76b3d-151">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="76b3d-152">ユーザーが割り当てられているポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="76b3d-152">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="76b3d-153">影響を受けるすべてのユーザーにまず異なるポリシーを割り当ててから、元のポリシーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="76b3d-153">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="76b3d-154">会議ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="76b3d-154">Meeting policy settings</span></span>

<span data-ttu-id="76b3d-155">[**会議ポリシー**] ページで既存のポリシーを選択するか、新しいポリシーを追加するための [**追加**] を選択すると、次の設定内容を構成できます。</span><span class="sxs-lookup"><span data-stu-id="76b3d-155">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="76b3d-156">全般</span><span class="sxs-lookup"><span data-stu-id="76b3d-156">General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="76b3d-157">オーディオとビデオ</span><span class="sxs-lookup"><span data-stu-id="76b3d-157">Audio & video</span></span>](meeting-policies-audio-and-video.md)
- [<span data-ttu-id="76b3d-158">コンテンツの共有</span><span class="sxs-lookup"><span data-stu-id="76b3d-158">Content sharing</span></span>](meeting-policies-content-sharing.md)
- [<span data-ttu-id="76b3d-159">参加者とゲスト</span><span class="sxs-lookup"><span data-stu-id="76b3d-159">Participants & guests</span></span>](meeting-policies-participants-and-guests.md)


## <a name="related-topics"></a><span data-ttu-id="76b3d-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="76b3d-160">Related topics</span></span>

- [<span data-ttu-id="76b3d-161">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="76b3d-161">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="76b3d-162"> Teams でユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="76b3d-162">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="76b3d-163">ユーザーから RestrictedAnonymousAccess Teams 会議ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="76b3d-163">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)