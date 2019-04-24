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
description: PowerShell を使用して、チーム、組織と機能でのライブ イベントを押しながらユーザーを制御するためにポリシーを設定する方法の例では、自分で作成したイベントで使用できます。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8858b8572a06aede2fa1de98ce9cfc14ed1745bd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204571"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="f0ca3-103">PowerShell を使用して Microsoft Teams でのライブ イベント ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="f0ca3-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="f0ca3-104">設定し、チームでのライブ イベントのポリシー設定を割り当てるには、次の Windows PowerShell コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="f0ca3-105">Get CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="f0ca3-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="f0ca3-106">セット CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="f0ca3-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="f0ca3-107">新しい-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="f0ca3-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="f0ca3-108">許可 CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="f0ca3-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="f0ca3-109">いくつかの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-109">Here's some examples.</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="f0ca3-110">ライブ イベントのスケジュールを設定するユーザーを許可します。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-110">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="f0ca3-111">クイック スタートのイベントのこれらの例を示します。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-111">These examples are for quick start events.</span></span> <span data-ttu-id="f0ca3-112">外部エンコーダーのイベントは、追加の手順を行う必要がありますがあります。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-112">For external encoder events, there are additional steps you must do.</span></span> <span data-ttu-id="f0ca3-113">詳細については、[外部のエンコーダーのイベントをスケジュールするのにはユーザーを有効にする](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-113">For more information, see [Enable users to schedule external encoder events](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events).</span></span>

<span data-ttu-id="f0ca3-114">**ライブ イベントのスケジュールを設定するユーザーを許可します。**</span><span class="sxs-lookup"><span data-stu-id="f0ca3-114">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="f0ca3-115">ユーザーには、グローバル ポリシーが割り当てられているが場合、は、実行し、 *AllowBroadcastScheduling*パラメーターが*True*に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-115">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="f0ca3-116">グローバル ポリシーの実行にユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-116">Then assign the user to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="f0ca3-117">ユーザー シナリオ</span><span class="sxs-lookup"><span data-stu-id="f0ca3-117">User scenarios</span></span>
<span data-ttu-id="f0ca3-118">**ライブ イベントのスケジュールを設定することができる、組織内のすべてのユーザーをします。**</span><span class="sxs-lookup"><span data-stu-id="f0ca3-118">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="f0ca3-119">実行し、確認の場合はユーザーには、グローバル ポリシーが割り当てられているが、その*AllowBroadcastScheduling* \* が*True*に設定します。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-119">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="f0ca3-120">以外のグローバル ポリシーのポリシーを割り当てると、ユーザー場合は、実行し、 *-AllowBroadcastScheduling*が*True*に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-120">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="f0ca3-121">**ライブ イベントを組織全体で無効にするスケジュールを設定します。**</span><span class="sxs-lookup"><span data-stu-id="f0ca3-121">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="f0ca3-122">ライブ イベントのスケジュールを無効にするには、実行します。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-122">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="f0ca3-123">グローバル ポリシーの実行には、組織内のすべてのユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-123">Assign all users in your organization to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="f0ca3-124">**スケジュールを設定できるユーザーの数が多いライブ イベントと、一連のユーザーがそれらのスケジュールを設定するを防止します。**</span><span class="sxs-lookup"><span data-stu-id="f0ca3-124">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="f0ca3-125">実行し、 *AllowBroadcastScheduling*を*True*に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-125">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="f0ca3-126">グローバル ポリシーの実行にユーザーまたはユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-126">Then assign a user or users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="f0ca3-127">ライブ イベントの実行をスケジュール設定は、新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-127">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="f0ca3-128">ライブ イベントのスケジュールを無効にするには、実行します。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-128">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="f0ca3-129">このポリシーの実行にユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-129">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="f0ca3-130">**ライブ イベントを多数のユーザーのスケジュールを無効にしてそれらをスケジュールするのにはユーザーのセットを許可します。**</span><span class="sxs-lookup"><span data-stu-id="f0ca3-130">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="f0ca3-131">ライブ イベントのスケジュールを無効にするには、実行します。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-131">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="f0ca3-132">グローバル ポリシーの実行にこれらのユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-132">Then assign those users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="f0ca3-133">ライブ イベントのスケジュールを許可する、実行するポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-133">Create a policy to allow live events scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="f0ca3-134">ライブ イベントのスケジュール設定を有効にするを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-134">Enable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="f0ca3-135">このポリシーの実行にユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-135">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="f0ca3-136">ライブ イベントに参加できるユーザーを設定します</span><span class="sxs-lookup"><span data-stu-id="f0ca3-136">Set who can join live events</span></span>
 
<span data-ttu-id="f0ca3-137">ユーザーがそのすべてのユーザー、匿名ユーザーを含むイベントを作成することができますへの参加、実行できるようにするグローバル ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-137">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="f0ca3-138">ライブ イベントの記録] オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-138">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="f0ca3-139">この設定は、クイック スタートのイベントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-139">This setting applies only to quick start events.</span></span>

<span data-ttu-id="f0ca3-140">ライブ イベントの記録を無効にするグローバル ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-140">Set the global policy to disable recording for live events:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-transcription-and-translation-in-live-events-coming-soon"></a><span data-ttu-id="f0ca3-141">(準備中) のライブ イベントでの議事録作成と翻訳を設定します。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-141">Set transcription and translation in live events (coming soon)</span></span>
> [!NOTE]
> <span data-ttu-id="f0ca3-142">この設定は、クイック スタートのイベントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-142">This setting applies only to quick start events.</span></span> 

<span data-ttu-id="f0ca3-143">イベントの参加者議事録作成と翻訳を有効にするグローバル ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="f0ca3-143">Set the global policy to turn on transcription and translation on for event attendees:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="f0ca3-144">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f0ca3-144">Related topics</span></span>
- [<span data-ttu-id="f0ca3-145">Teams のライブ イベントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="f0ca3-145">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)


