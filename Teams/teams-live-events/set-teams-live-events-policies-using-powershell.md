---
title: PowerShell を使用して Microsoft Teams でのライブ イベント ポリシーを設定する
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: PowerShell を使用してチームのポリシーを設定して、組織内の live イベントを保留できるユーザーと、作成したイベントで利用できる機能を制御する方法の例
appliesto:
- Microsoft Teams
ms.openlocfilehash: b92d52178f7b57b453eaaec010ded4731d166caf
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243650"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="04dcc-103">PowerShell を使用して Microsoft Teams でのライブ イベント ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="04dcc-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="04dcc-104">次の Windows PowerShell コマンドレットを使用して、Teams でライブイベントのポリシー設定を設定し、割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="04dcc-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="04dcc-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="04dcc-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="04dcc-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="04dcc-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="04dcc-107">新規-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="04dcc-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="04dcc-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="04dcc-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="04dcc-109">いくつかの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="04dcc-109">Here are some examples.</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="04dcc-110">ユーザーがライブイベントのスケジュールを設定できるようにする</span><span class="sxs-lookup"><span data-stu-id="04dcc-110">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="04dcc-111">次の例は、Teams で作成されたイベントを対象としています。</span><span class="sxs-lookup"><span data-stu-id="04dcc-111">These examples are for events produced in Teams.</span></span> <span data-ttu-id="04dcc-112">外部のアプリやデバイスで生成されたイベントの場合は、追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04dcc-112">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="04dcc-113">詳細については、「[外部アプリまたはデバイスで生成されたイベントをユーザーがスケジュールできるよう](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04dcc-113">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="04dcc-114">**ユーザーがライブイベントをスケジュールできるようにする**</span><span class="sxs-lookup"><span data-stu-id="04dcc-114">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="04dcc-115">ユーザーにグローバルポリシーが割り当てられている場合は、 *AllowBroadcastScheduling*パラメーターが*True*に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="04dcc-115">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="04dcc-116">次に、ユーザーをグローバルポリシーに割り当てて、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="04dcc-116">Then assign the user to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="04dcc-117">ユーザーシナリオ</span><span class="sxs-lookup"><span data-stu-id="04dcc-117">User scenarios</span></span>
<span data-ttu-id="04dcc-118">**組織内のすべてのユーザーがライブイベントをスケジュールできるようにする**</span><span class="sxs-lookup"><span data-stu-id="04dcc-118">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="04dcc-119">ユーザーにグローバルポリシーが割り当てられている場合は、 *AllowBroadcastScheduling* \* が*True*に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="04dcc-119">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="04dcc-120">ユーザーにグローバルポリシー以外のポリシーが割り当てられている場合は、を実行し、 *-AllowBroadcastScheduling*が*True*に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="04dcc-120">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="04dcc-121">**組織全体でライブイベントのスケジュール設定を無効にする必要がある場合**</span><span class="sxs-lookup"><span data-stu-id="04dcc-121">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="04dcc-122">ライブイベントのスケジュール設定を無効にします。次を実行します。</span><span class="sxs-lookup"><span data-stu-id="04dcc-122">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="04dcc-123">組織内のすべてのユーザーをグローバルポリシーに割り当てる: 次を実行します。</span><span class="sxs-lookup"><span data-stu-id="04dcc-123">Assign all users in your organization to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="04dcc-124">**多数のユーザーがライブイベントのスケジュールを設定して、ユーザーのスケジュールを設定できないようにする必要がある場合**</span><span class="sxs-lookup"><span data-stu-id="04dcc-124">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="04dcc-125">*AllowBroadcastScheduling*が*True*に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="04dcc-125">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="04dcc-126">次に、ユーザーまたはユーザーをグローバルポリシーに割り当て、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="04dcc-126">Then assign a user or users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="04dcc-127">ライブイベントのスケジューリングを許可しない新しいポリシーを作成します。次を実行します。</span><span class="sxs-lookup"><span data-stu-id="04dcc-127">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="04dcc-128">ライブイベントのスケジュール設定を無効にします。次を実行します。</span><span class="sxs-lookup"><span data-stu-id="04dcc-128">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="04dcc-129">次に、このポリシーにユーザーを割り当てて、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="04dcc-129">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="04dcc-130">**多数のユーザーに対してライブイベントのスケジュールを無効にして、ユーザーのスケジュールを設定できるようにする必要がある場合**</span><span class="sxs-lookup"><span data-stu-id="04dcc-130">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="04dcc-131">ライブイベントのスケジュール設定を無効にします。次を実行します。</span><span class="sxs-lookup"><span data-stu-id="04dcc-131">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="04dcc-132">次に、これらのユーザーをグローバルポリシーに割り当てて、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="04dcc-132">Then assign those users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="04dcc-133">ライブイベントのスケジューリングを許可するポリシーを作成します。次を実行します。</span><span class="sxs-lookup"><span data-stu-id="04dcc-133">Create a policy to allow live events scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="04dcc-134">ライブイベントのスケジュール設定を有効にします。次を実行します。</span><span class="sxs-lookup"><span data-stu-id="04dcc-134">Enable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="04dcc-135">次に、このポリシーにユーザーを割り当てて、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="04dcc-135">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="04dcc-136">ライブイベントに参加できるユーザーを設定する</span><span class="sxs-lookup"><span data-stu-id="04dcc-136">Set who can join live events</span></span>
 
<span data-ttu-id="04dcc-137">グローバルポリシーを設定して、匿名ユーザーを含むすべてのユーザーが参加できるイベントを作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="04dcc-137">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="04dcc-138">ライブイベントのレコーディングオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="04dcc-138">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="04dcc-139">この設定は Teams で作成されたイベントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04dcc-139">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="04dcc-140">ライブイベントの記録を無効にするグローバルポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="04dcc-140">Set the global policy to disable recording for live events:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="04dcc-141">ライブイベントでライブキャプションと字幕を設定する</span><span class="sxs-lookup"><span data-stu-id="04dcc-141">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="04dcc-142">この設定は Teams で作成されたイベントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="04dcc-142">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="04dcc-143">イベントの出席者に対して、ライブキャプションと字幕 (書き起こし) を有効にするグローバルポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="04dcc-143">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="04dcc-144">関連トピック</span><span class="sxs-lookup"><span data-stu-id="04dcc-144">Related topics</span></span>
- [<span data-ttu-id="04dcc-145">Teams のライブ イベントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="04dcc-145">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)


