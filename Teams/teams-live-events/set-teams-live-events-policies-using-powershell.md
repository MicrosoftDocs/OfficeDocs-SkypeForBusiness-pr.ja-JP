---
title: PowerShell を使用してライブ イベント ポリシーを設定する
author: cichur
ms.author: v-cichur
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
description: PowerShell を使用して Teams でポリシーを設定し、組織内でライブ イベントを開催できるユーザーとイベントで使用できる機能を制御する方法の例。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 95b78b520b6978c85715e6dc1c1314ed279a305b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119146"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>PowerShell を使用して Microsoft Teams でのライブ イベント ポリシーを設定する

次の Windows PowerShell コマンドレットを使用して、Teams のライブ イベントのポリシー設定を設定および割り当てることができます。 
- [Get-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

以下にいくつかの例を示します。

> [!NOTE]
> これらのコマンドレットを実行する前に、オンライン PowerShell Skype for Business接続する必要があります。 詳細については、「Manage Skype for Business Online with Microsoft 365 または Office 365 [PowerShell 」を参照してください](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

## <a name="allow-users-to-schedule-live-events"></a>ユーザーがライブ イベントをスケジュールできるようにする 

> [!NOTE]
> これらの例は、Teams で生成されたイベント用です。 外部アプリまたはデバイスで生成されたイベントの場合、追加の手順を実行する必要があります。 詳細については、「[ユーザーが外部アプリまたはデバイスで生成されたイベントをスケジュールできるようにする](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)」を参照してください。

**ユーザーがライブ イベントをスケジュールできるようにする**

ユーザーにグローバル ポリシーが割り当てられている場合、*AllowBroadcastScheduling* パラメーターが *True* に設定されていることを実行して確認します。
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
次に、ユーザーをグローバル ポリシーに割り当て、次を実行します。
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>ユーザーのシナリオ
**組織内のすべてのユーザーがライブ イベントをスケジュールできるようにする**

ユーザーにグローバル ポリシーが割り当てられている場合、*AllowBroadcastScheduling** が *True* に設定されていることを実行して確認します。
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
ユーザーにグローバル ポリシー以外のポリシーが割り当てられている場合、*AllowBroadcastScheduling** が *True* に設定されていることを実行して確認します。
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**組織全体でライブ イベントのスケジュール設定を無効にする場合**

ライブ イベントのスケジュール設定を無効にし、次を実行します。
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
組織内のすべてのユーザーをグローバル ポリシーに割り当て、次を実行します。
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**多数のユーザーがライブ イベントをスケジュール設定し、一連のユーザーがそれらをスケジュールできないようにする必要がある**

*AllowBroadcastScheduling* が *True* に設定されていることを実行して確認します。
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
次に、1 人または複数のユーザーをグローバル ポリシーに割り当て、次を実行します。
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

ライブ イベントのスケジュール設定を許可しない新しいポリシーを作成し、次を実行します。
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
ライブ イベントのスケジュール設定を無効にし、次を実行します。
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
次に、このポリシーにユーザーを割り当て、次を実行します。
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**多数のユーザーのライブ イベント スケジュール設定を無効にし、一連のユーザーがそれらをスケジュール設定できるようにする場合**

ライブ イベントのスケジュール設定を無効にし、次を実行します。
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
次に、これらのユーザーをグローバル ポリシーに割り当て、次を実行します。
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
ライブ イベントのスケジュール設定を許可するポリシーを作成し、次を実行します。
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
ライブ イベントのスケジュール設定を有効にし、次を実行します。
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
次に、このポリシーにユーザーを割り当て、次を実行します。
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>ライブ イベントに参加できるユーザーを設定する
 
グローバル ポリシーを設定して、ユーザーが匿名ユーザーを含む全員が参加および実行できるイベントを作成できるようにします。
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>ライブ イベントの記録オプションを設定する
> [!NOTE]
> この設定は、Teams で作成されたイベントにのみ適用されます。

ライブ イベントの記録を無効にするグローバル ポリシーを設定します。
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>ライブ イベントでライブ キャプションと字幕を設定する
> [!NOTE]
> この設定は、Teams で作成されたイベントにのみ適用されます。 

イベント参加者のライブ キャプションと字幕 (文字起こし) をオンにするグローバル ポリシーを設定します。
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>関連項目
- [Teams のライブ イベントをセットアップする](set-up-for-teams-live-events.md)
- [Teams での PowerShell の概要](../teams-powershell-overview.md)