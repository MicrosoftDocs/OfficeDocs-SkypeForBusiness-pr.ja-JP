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
- M365-collaboration
description: PowerShell を使用して Teams でポリシーを設定し、組織内のライブ イベントを保持できるユーザーと、作成するイベントで使用可能な機能を制御する方法の例
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0d734cd4a92f3ebd32e2d0e6a24292ae50b456e7
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952880"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="3a1b5-103">PowerShell を使用して Microsoft Teams でのライブ イベント ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="3a1b5-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="3a1b5-104">次の Windows PowerShell コマンドレットを使用して、Teams のライブ イベントのポリシー設定を設定および割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="3a1b5-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="3a1b5-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="3a1b5-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="3a1b5-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="3a1b5-107">New-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="3a1b5-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="3a1b5-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="3a1b5-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="3a1b5-109">以下にいくつかの例を示します。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-109">Here are some examples.</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="3a1b5-110">ユーザーがライブ イベントをスケジュールできるようにする</span><span class="sxs-lookup"><span data-stu-id="3a1b5-110">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="3a1b5-111">これらの例は、Teams で生成されたイベント用です。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-111">These examples are for events produced in Teams.</span></span> <span data-ttu-id="3a1b5-112">外部アプリまたはデバイスで生成されたイベントの場合、追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-112">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="3a1b5-113">詳細については、「[ユーザーが外部アプリまたはデバイスで生成されたイベントをスケジュールできるようにする](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-113">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="3a1b5-114">**ユーザーがライブ イベントをスケジュールできるようにする**</span><span class="sxs-lookup"><span data-stu-id="3a1b5-114">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="3a1b5-115">ユーザーにグローバル ポリシーが割り当てられている場合、*AllowBroadcastScheduling* パラメーターが *True* に設定されていることを実行して確認します。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-115">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="3a1b5-116">次に、ユーザーをグローバル ポリシーに割り当て、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-116">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="3a1b5-117">ユーザーのシナリオ</span><span class="sxs-lookup"><span data-stu-id="3a1b5-117">User scenarios</span></span>
<span data-ttu-id="3a1b5-118">**組織内のすべてのユーザーがライブ イベントをスケジュールできるようにする**</span><span class="sxs-lookup"><span data-stu-id="3a1b5-118">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="3a1b5-119">ユーザーにグローバル ポリシーが割り当てられている場合、*AllowBroadcastScheduling*\* が *True* に設定されていることを実行して確認します。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-119">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="3a1b5-120">ユーザーにグローバル ポリシー以外のポリシーが割り当てられている場合、*AllowBroadcastScheduling*\* が *True* に設定されていることを実行して確認します。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-120">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="3a1b5-121">**組織全体でライブ イベントのスケジュール設定を無効にする場合**</span><span class="sxs-lookup"><span data-stu-id="3a1b5-121">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="3a1b5-122">ライブ イベントのスケジュール設定を無効にし、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-122">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="3a1b5-123">組織内のすべてのユーザーをグローバル ポリシーに割り当て、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-123">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="3a1b5-124">**多数のユーザーがライブ イベントをスケジュール設定し、一連のユーザーがそれらをスケジュールできないようにする必要がある**</span><span class="sxs-lookup"><span data-stu-id="3a1b5-124">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="3a1b5-125">*AllowBroadcastScheduling* が *True* に設定されていることを実行して確認します。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-125">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="3a1b5-126">次に、1 人または複数のユーザーをグローバル ポリシーに割り当て、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-126">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="3a1b5-127">ライブ イベントのスケジュール設定を許可しない新しいポリシーを作成し、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-127">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="3a1b5-128">ライブ イベントのスケジュール設定を無効にし、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-128">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="3a1b5-129">次に、このポリシーにユーザーを割り当て、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-129">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="3a1b5-130">**多数のユーザーのライブ イベント スケジュール設定を無効にし、一連のユーザーがそれらをスケジュール設定できるようにする場合**</span><span class="sxs-lookup"><span data-stu-id="3a1b5-130">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="3a1b5-131">ライブ イベントのスケジュール設定を無効にし、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-131">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="3a1b5-132">次に、これらのユーザーをグローバル ポリシーに割り当て、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-132">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="3a1b5-133">ライブ イベントのスケジュール設定を許可するポリシーを作成し、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-133">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="3a1b5-134">ライブ イベントのスケジュール設定を有効にし、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-134">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="3a1b5-135">次に、このポリシーにユーザーを割り当て、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-135">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="3a1b5-136">ライブ イベントに参加できるユーザーを設定する</span><span class="sxs-lookup"><span data-stu-id="3a1b5-136">Set who can join live events</span></span>
 
<span data-ttu-id="3a1b5-137">グローバル ポリシーを設定して、ユーザーが匿名ユーザーを含む全員が参加および実行できるイベントを作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-137">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="3a1b5-138">ライブ イベントの記録オプションを設定する</span><span class="sxs-lookup"><span data-stu-id="3a1b5-138">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="3a1b5-139">この設定は、Teams で作成されたイベントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-139">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="3a1b5-140">ライブ イベントの記録を無効にするグローバル ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-140">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="3a1b5-141">ライブ イベントでライブ キャプションと字幕を設定する</span><span class="sxs-lookup"><span data-stu-id="3a1b5-141">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="3a1b5-142">この設定は、Teams で作成されたイベントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-142">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="3a1b5-143">イベント参加者のライブ キャプションと字幕 (文字起こし) をオンにするグローバル ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="3a1b5-143">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="3a1b5-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a1b5-144">Related topics</span></span>
- [<span data-ttu-id="3a1b5-145">Teams のライブ イベントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="3a1b5-145">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)


