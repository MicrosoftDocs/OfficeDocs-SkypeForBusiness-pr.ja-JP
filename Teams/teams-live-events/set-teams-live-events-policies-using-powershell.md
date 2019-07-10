---
title: PowerShell を使用して Microsoft Teams でのライブ イベント ポリシーを設定する
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 07/10/2019
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
ms.openlocfilehash: 825fe7e7e80b2653d35c8b0752124b50386395d6
ms.sourcegitcommit: 5faa89ea686448d5b339178f1330edc63e21a52f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35602264"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>PowerShell を使用して Microsoft Teams でのライブ イベント ポリシーを設定する

次の Windows PowerShell コマンドレットを使用して、Teams でライブイベントのポリシー設定を設定し、割り当てることができます。 
- [Get-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [新規-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

いくつかの例を次に示します。

## <a name="allow-users-to-schedule-live-events"></a>ユーザーがライブイベントのスケジュールを設定できるようにする 

> [!NOTE]
> 次の例は、Teams で作成されたイベントを対象としています。 外部のアプリやデバイスで生成されたイベントの場合は、追加の手順を実行する必要があります。 詳細については、「[外部アプリまたはデバイスで生成されたイベントをユーザーがスケジュールできるよう](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)にする」を参照してください。

**ユーザーがライブイベントをスケジュールできるようにする**

ユーザーにグローバルポリシーが割り当てられている場合は、 *AllowBroadcastScheduling*パラメーターが*True*に設定されていることを確認します。
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
次に、ユーザーをグローバルポリシーに割り当てて、次を実行します。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>ユーザーシナリオ
**組織内のすべてのユーザーがライブイベントをスケジュールできるようにする**

ユーザーにグローバルポリシーが割り当てられている場合は、 *AllowBroadcastScheduling* * が*True*に設定されていることを確認します。
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
ユーザーにグローバルポリシー以外のポリシーが割り当てられている場合は、を実行し、 *-AllowBroadcastScheduling*が*True*に設定されていることを確認します。
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**組織全体でライブイベントのスケジュール設定を無効にする必要がある場合**

ライブイベントのスケジュール設定を無効にします。次を実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
組織内のすべてのユーザーをグローバルポリシーに割り当てる: 次を実行します。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**多数のユーザーがライブイベントのスケジュールを設定して、ユーザーのスケジュールを設定できないようにする必要がある場合**

*AllowBroadcastScheduling*が*True*に設定されていることを確認します。
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
次に、ユーザーまたはユーザーをグローバルポリシーに割り当て、次を実行します。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

ライブイベントのスケジューリングを許可しない新しいポリシーを作成します。次を実行します。
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
ライブイベントのスケジュール設定を無効にします。次を実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
次に、このポリシーにユーザーを割り当てて、次を実行します。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**多数のユーザーに対してライブイベントのスケジュールを無効にして、ユーザーのスケジュールを設定できるようにする必要がある場合**

ライブイベントのスケジュール設定を無効にします。次を実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
次に、これらのユーザーをグローバルポリシーに割り当てて、次を実行します。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
ライブイベントのスケジューリングを許可するポリシーを作成します。次を実行します。
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
ライブイベントのスケジュール設定を有効にします。次を実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
次に、このポリシーにユーザーを割り当てて、次を実行します。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>ライブイベントに参加できるユーザーを設定する
 
グローバルポリシーを設定して、匿名ユーザーを含むすべてのユーザーが参加できるイベントを作成できるようにします。
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>ライブイベントのレコーディングオプションを設定する
> [!NOTE]
> この設定は Teams で作成されたイベントにのみ適用されます。

ライブイベントの記録を無効にするグローバルポリシーを設定します。
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>ライブイベントでライブキャプションと字幕を設定する
> [!NOTE]
> この設定は Teams で作成されたイベントにのみ適用されます。 

イベントの出席者に対して、ライブキャプションと字幕 (書き起こし) を有効にするグローバルポリシーを設定します。
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>関連トピック
- [Teams のライブ イベントをセットアップする](set-up-for-teams-live-events.md)


