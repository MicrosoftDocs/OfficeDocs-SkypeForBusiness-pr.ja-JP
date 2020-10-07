---
title: PowerShell を使用してライブイベントのポリシーを設定する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: PowerShell を使用してチームのポリシーを設定する方法の例。組織内のライブイベントを保持できるユーザーと、イベントで利用可能な機能を制御します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e49c2dca91dca56366dd6b8a8ce460547043c120
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369152"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="c5384-103">PowerShell を使用して Microsoft Teams でのライブ イベント ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="c5384-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="c5384-104">次の Windows PowerShell コマンドレットを使用して、Teams のライブ イベントのポリシー設定を設定および割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c5384-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="c5384-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="c5384-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="c5384-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="c5384-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="c5384-107">New-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="c5384-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="c5384-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="c5384-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="c5384-109">新しい CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="c5384-109">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

<span data-ttu-id="c5384-110">以下にいくつかの例を示します。</span><span class="sxs-lookup"><span data-stu-id="c5384-110">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="c5384-111">これらのコマンドレットを実行するには、Skype for Business Online PowerShell に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5384-111">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="c5384-112">詳細については、「 [Microsoft 365 または Office 365 PowerShell で Skype For Business Online を管理](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5384-112">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="c5384-113">ユーザーがライブ イベントをスケジュールできるようにする</span><span class="sxs-lookup"><span data-stu-id="c5384-113">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="c5384-114">これらの例は、Teams で生成されたイベント用です。</span><span class="sxs-lookup"><span data-stu-id="c5384-114">These examples are for events produced in Teams.</span></span> <span data-ttu-id="c5384-115">外部アプリまたはデバイスで生成されたイベントの場合、追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5384-115">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="c5384-116">詳細については、「[ユーザーが外部アプリまたはデバイスで生成されたイベントをスケジュールできるようにする](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5384-116">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="c5384-117">**ユーザーがライブ イベントをスケジュールできるようにする**</span><span class="sxs-lookup"><span data-stu-id="c5384-117">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="c5384-118">ユーザーにグローバル ポリシーが割り当てられている場合、*AllowBroadcastScheduling* パラメーターが *True* に設定されていることを実行して確認します。</span><span class="sxs-lookup"><span data-stu-id="c5384-118">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="c5384-119">次に、ユーザーをグローバル ポリシーに割り当て、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c5384-119">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="c5384-120">ユーザーのシナリオ</span><span class="sxs-lookup"><span data-stu-id="c5384-120">User scenarios</span></span>
<span data-ttu-id="c5384-121">**組織内のすべてのユーザーがライブ イベントをスケジュールできるようにする**</span><span class="sxs-lookup"><span data-stu-id="c5384-121">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="c5384-122">ユーザーにグローバル ポリシーが割り当てられている場合、*AllowBroadcastScheduling*\* が *True* に設定されていることを実行して確認します。</span><span class="sxs-lookup"><span data-stu-id="c5384-122">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="c5384-123">ユーザーにグローバル ポリシー以外のポリシーが割り当てられている場合、*AllowBroadcastScheduling*\* が *True* に設定されていることを実行して確認します。</span><span class="sxs-lookup"><span data-stu-id="c5384-123">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="c5384-124">**組織全体でライブ イベントのスケジュール設定を無効にする場合**</span><span class="sxs-lookup"><span data-stu-id="c5384-124">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="c5384-125">ライブ イベントのスケジュール設定を無効にし、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c5384-125">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="c5384-126">組織内のすべてのユーザーをグローバル ポリシーに割り当て、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c5384-126">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="c5384-127">**多数のユーザーがライブ イベントをスケジュール設定し、一連のユーザーがそれらをスケジュールできないようにする必要がある**</span><span class="sxs-lookup"><span data-stu-id="c5384-127">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="c5384-128">*AllowBroadcastScheduling* が *True* に設定されていることを実行して確認します。</span><span class="sxs-lookup"><span data-stu-id="c5384-128">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="c5384-129">次に、1 人または複数のユーザーをグローバル ポリシーに割り当て、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c5384-129">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="c5384-130">ライブ イベントのスケジュール設定を許可しない新しいポリシーを作成し、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c5384-130">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="c5384-131">ライブ イベントのスケジュール設定を無効にし、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c5384-131">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="c5384-132">次に、このポリシーにユーザーを割り当て、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c5384-132">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="c5384-133">**多数のユーザーのライブ イベント スケジュール設定を無効にし、一連のユーザーがそれらをスケジュール設定できるようにする場合**</span><span class="sxs-lookup"><span data-stu-id="c5384-133">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="c5384-134">ライブ イベントのスケジュール設定を無効にし、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c5384-134">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="c5384-135">次に、これらのユーザーをグローバル ポリシーに割り当て、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c5384-135">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="c5384-136">ライブ イベントのスケジュール設定を許可するポリシーを作成し、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c5384-136">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="c5384-137">ライブ イベントのスケジュール設定を有効にし、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c5384-137">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="c5384-138">次に、このポリシーにユーザーを割り当て、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c5384-138">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="c5384-139">ライブ イベントに参加できるユーザーを設定する</span><span class="sxs-lookup"><span data-stu-id="c5384-139">Set who can join live events</span></span>
 
<span data-ttu-id="c5384-140">グローバル ポリシーを設定して、ユーザーが匿名ユーザーを含む全員が参加および実行できるイベントを作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c5384-140">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="c5384-141">ライブ イベントの記録オプションを設定する</span><span class="sxs-lookup"><span data-stu-id="c5384-141">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="c5384-142">この設定は、Teams で作成されたイベントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c5384-142">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="c5384-143">ライブ イベントの記録を無効にするグローバル ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="c5384-143">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="c5384-144">ライブ イベントでライブ キャプションと字幕を設定する</span><span class="sxs-lookup"><span data-stu-id="c5384-144">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="c5384-145">この設定は、Teams で作成されたイベントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c5384-145">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="c5384-146">イベント参加者のライブ キャプションと字幕 (文字起こし) をオンにするグローバル ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="c5384-146">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="c5384-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5384-147">Related topics</span></span>
- [<span data-ttu-id="c5384-148">Teams のライブ イベントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="c5384-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="c5384-149">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="c5384-149">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)

