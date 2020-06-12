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
ms.openlocfilehash: 1c1131790e36fe451444a8c8a3fb25259d5741da
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691573"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="a1ab4-103">PowerShell を使用して Microsoft Teams でのライブ イベント ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="a1ab4-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="a1ab4-104">次の Windows PowerShell コマンドレットを使用して、Teams のライブ イベントのポリシー設定を設定および割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="a1ab4-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="a1ab4-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="a1ab4-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="a1ab4-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="a1ab4-107">New-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="a1ab4-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="a1ab4-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="a1ab4-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="a1ab4-109">以下にいくつかの例を示します。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-109">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="a1ab4-110">これらのコマンドレットを実行するには、Skype for Business Online PowerShell に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-110">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="a1ab4-111">詳細については、「 [Microsoft 365 または Office 365 PowerShell で Skype For Business Online を管理](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-111">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="a1ab4-112">ユーザーがライブ イベントをスケジュールできるようにする</span><span class="sxs-lookup"><span data-stu-id="a1ab4-112">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="a1ab4-113">これらの例は、Teams で生成されたイベント用です。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-113">These examples are for events produced in Teams.</span></span> <span data-ttu-id="a1ab4-114">外部アプリまたはデバイスで生成されたイベントの場合、追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-114">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="a1ab4-115">詳細については、「[ユーザーが外部アプリまたはデバイスで生成されたイベントをスケジュールできるようにする](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-115">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="a1ab4-116">**ユーザーがライブ イベントをスケジュールできるようにする**</span><span class="sxs-lookup"><span data-stu-id="a1ab4-116">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="a1ab4-117">ユーザーにグローバル ポリシーが割り当てられている場合、*AllowBroadcastScheduling* パラメーターが *True* に設定されていることを実行して確認します。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-117">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="a1ab4-118">次に、ユーザーをグローバル ポリシーに割り当て、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-118">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="a1ab4-119">ユーザーのシナリオ</span><span class="sxs-lookup"><span data-stu-id="a1ab4-119">User scenarios</span></span>
<span data-ttu-id="a1ab4-120">**組織内のすべてのユーザーがライブ イベントをスケジュールできるようにする**</span><span class="sxs-lookup"><span data-stu-id="a1ab4-120">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="a1ab4-121">ユーザーにグローバル ポリシーが割り当てられている場合、*AllowBroadcastScheduling*\* が *True* に設定されていることを実行して確認します。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-121">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="a1ab4-122">ユーザーにグローバル ポリシー以外のポリシーが割り当てられている場合、*AllowBroadcastScheduling*\* が *True* に設定されていることを実行して確認します。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-122">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="a1ab4-123">**組織全体でライブ イベントのスケジュール設定を無効にする場合**</span><span class="sxs-lookup"><span data-stu-id="a1ab4-123">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="a1ab4-124">ライブ イベントのスケジュール設定を無効にし、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-124">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="a1ab4-125">組織内のすべてのユーザーをグローバル ポリシーに割り当て、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-125">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="a1ab4-126">**多数のユーザーがライブ イベントをスケジュール設定し、一連のユーザーがそれらをスケジュールできないようにする必要がある**</span><span class="sxs-lookup"><span data-stu-id="a1ab4-126">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="a1ab4-127">*AllowBroadcastScheduling* が *True* に設定されていることを実行して確認します。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-127">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="a1ab4-128">次に、1 人または複数のユーザーをグローバル ポリシーに割り当て、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-128">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="a1ab4-129">ライブ イベントのスケジュール設定を許可しない新しいポリシーを作成し、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-129">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="a1ab4-130">ライブ イベントのスケジュール設定を無効にし、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-130">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="a1ab4-131">次に、このポリシーにユーザーを割り当て、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-131">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="a1ab4-132">**多数のユーザーのライブ イベント スケジュール設定を無効にし、一連のユーザーがそれらをスケジュール設定できるようにする場合**</span><span class="sxs-lookup"><span data-stu-id="a1ab4-132">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="a1ab4-133">ライブ イベントのスケジュール設定を無効にし、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-133">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="a1ab4-134">次に、これらのユーザーをグローバル ポリシーに割り当て、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-134">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="a1ab4-135">ライブ イベントのスケジュール設定を許可するポリシーを作成し、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-135">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="a1ab4-136">ライブ イベントのスケジュール設定を有効にし、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-136">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="a1ab4-137">次に、このポリシーにユーザーを割り当て、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-137">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="a1ab4-138">ライブ イベントに参加できるユーザーを設定する</span><span class="sxs-lookup"><span data-stu-id="a1ab4-138">Set who can join live events</span></span>
 
<span data-ttu-id="a1ab4-139">グローバル ポリシーを設定して、ユーザーが匿名ユーザーを含む全員が参加および実行できるイベントを作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-139">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="a1ab4-140">ライブ イベントの記録オプションを設定する</span><span class="sxs-lookup"><span data-stu-id="a1ab4-140">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="a1ab4-141">この設定は、Teams で作成されたイベントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-141">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="a1ab4-142">ライブ イベントの記録を無効にするグローバル ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-142">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="a1ab4-143">ライブ イベントでライブ キャプションと字幕を設定する</span><span class="sxs-lookup"><span data-stu-id="a1ab4-143">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="a1ab4-144">この設定は、Teams で作成されたイベントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-144">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="a1ab4-145">イベント参加者のライブ キャプションと字幕 (文字起こし) をオンにするグローバル ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="a1ab4-145">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="a1ab4-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1ab4-146">Related topics</span></span>
- [<span data-ttu-id="a1ab4-147">Teams のライブ イベントをセットアップする</span><span class="sxs-lookup"><span data-stu-id="a1ab4-147">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="a1ab4-148">Teams での PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="a1ab4-148">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)

