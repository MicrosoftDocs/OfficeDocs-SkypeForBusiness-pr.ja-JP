---
title: PowerShell を使用して Microsoft Teams でのライブ イベント ポリシーを設定する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: PowerShell を使用してチームのポリシーを設定して、組織内の live イベントを保留できるユーザーと、作成したイベントで利用できる機能を制御する方法の例
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8858b8572a06aede2fa1de98ce9cfc14ed1745bd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204571"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="13450-103">PowerShell を使用して Microsoft Teams でのライブ イベント ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="13450-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="13450-104">次の Windows PowerShell コマンドレットを使用して、Teams でライブイベントのポリシー設定を設定し、割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="13450-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="13450-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="13450-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="13450-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="13450-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="13450-107">新規-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="13450-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="13450-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="13450-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="13450-109">いくつかの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="13450-109">Here's some examples.</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="13450-110">ユーザーがライブイベントのスケジュールを設定できるようにする</span><span class="sxs-lookup"><span data-stu-id="13450-110">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="13450-111">次の例は、クイックスタートイベントを示しています。</span><span class="sxs-lookup"><span data-stu-id="13450-111">These examples are for quick start events.</span></span> <span data-ttu-id="13450-112">外部のエンコーダーイベントについては、追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13450-112">For external encoder events, there are additional steps you must do.</span></span> <span data-ttu-id="13450-113">詳細については、「[ユーザーが外部エンコーダーイベントをスケジュールできるようにする](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13450-113">For more information, see [Enable users to schedule external encoder events](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events).</span></span>

<span data-ttu-id="13450-114">**ユーザーがライブイベントをスケジュールできるようにする**</span><span class="sxs-lookup"><span data-stu-id="13450-114">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="13450-115">ユーザーにグローバルポリシーが割り当てられている場合は、 *AllowBroadcastScheduling*パラメーターが*True*に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="13450-115">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="13450-116">次に、ユーザーをグローバルポリシーに割り当てて、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="13450-116">Then assign the user to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="13450-117">ユーザーシナリオ</span><span class="sxs-lookup"><span data-stu-id="13450-117">User scenarios</span></span>
<span data-ttu-id="13450-118">**組織内のすべてのユーザーがライブイベントをスケジュールできるようにする**</span><span class="sxs-lookup"><span data-stu-id="13450-118">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="13450-119">ユーザーにグローバルポリシーが割り当てられている場合は、 *AllowBroadcastScheduling* \* が*True*に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="13450-119">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="13450-120">ユーザーにグローバルポリシー以外のポリシーが割り当てられている場合は、を実行し、 *-AllowBroadcastScheduling*が*True*に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="13450-120">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="13450-121">**組織全体でライブイベントのスケジュール設定を無効にする必要がある場合**</span><span class="sxs-lookup"><span data-stu-id="13450-121">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="13450-122">ライブイベントのスケジュール設定を無効にします。次を実行します。</span><span class="sxs-lookup"><span data-stu-id="13450-122">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="13450-123">組織内のすべてのユーザーをグローバルポリシーに割り当てる: 次を実行します。</span><span class="sxs-lookup"><span data-stu-id="13450-123">Assign all users in your organization to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="13450-124">**多数のユーザーがライブイベントのスケジュールを設定して、ユーザーのスケジュールを設定できないようにする必要がある場合**</span><span class="sxs-lookup"><span data-stu-id="13450-124">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="13450-125">*AllowBroadcastScheduling*が*True*に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="13450-125">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="13450-126">次に、ユーザーまたはユーザーをグローバルポリシーに割り当て、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="13450-126">Then assign a user or users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="13450-127">ライブイベントのスケジューリングを許可しない新しいポリシーを作成します。次を実行します。</span><span class="sxs-lookup"><span data-stu-id="13450-127">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="13450-128">ライブイベントのスケジュール設定を無効にします。次を実行します。</span><span class="sxs-lookup"><span data-stu-id="13450-128">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="13450-129">次に、このポリシーにユーザーを割り当てて、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="13450-129">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="13450-130">**多数のユーザーに対してライブイベントのスケジュールを無効にして、ユーザーのスケジュールを設定できるようにする必要がある場合**</span><span class="sxs-lookup"><span data-stu-id="13450-130">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="13450-131">ライブイベントのスケジュール設定を無効にします。次を実行します。</span><span class="sxs-lookup"><span data-stu-id="13450-131">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="13450-132">次に、これらのユーザーをグローバルポリシーに割り当てて、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="13450-132">Then assign those users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="13450-133">ライブイベントのスケジューリングを許可するポリシーを作成します。次を実行します。</span><span class="sxs-lookup"><span data-stu-id="13450-133">Create a policy to allow live events scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="13450-134">ライブイベントのスケジュール設定を有効にします。次を実行します。</span><span class="sxs-lookup"><span data-stu-id="13450-134">Enable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="13450-135">次に、このポリシーにユーザーを割り当てて、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="13450-135">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="13450-136">ライブイベントに参加できるユーザーを設定する</span><span class="sxs-lookup"><span data-stu-id="13450-136">Set who can join live events</span></span>
 
<span data-ttu-id="13450-137">グローバルポリシーを設定して、匿名ユーザーを含むすべてのユーザーが参加できるイベントを作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="13450-137">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="13450-138">ライブイベントのレコーディングオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="13450-138">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="13450-139">この設定は、クイックスタートイベントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="13450-139">This setting applies only to quick start events.</span></span>

<span data-ttu-id="13450-140">ライブイベントの記録を無効にするグローバルポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="13450-140">Set the global policy to disable recording for live events:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-transcription-and-translation-in-live-events-coming-soon"></a><span data-ttu-id="13450-141">ライブイベントでの議事録と翻訳を設定する (近日公開)</span><span class="sxs-lookup"><span data-stu-id="13450-141">Set transcription and translation in live events (coming soon)</span></span>
> [!NOTE]
> <span data-ttu-id="13450-142">この設定は、クイックスタートイベントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="13450-142">This setting applies only to quick start events.</span></span> 

<span data-ttu-id="13450-143">イベントの出席者に対して、議事録と翻訳を有効にするようにグローバルポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="13450-143">Set the global policy to turn on transcription and translation on for event attendees:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="13450-144">関連トピック</span><span class="sxs-lookup"><span data-stu-id="13450-144">Related topics</span></span>
- [<span data-ttu-id="13450-145">Teams のライブ イベントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="13450-145">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)


