---
title: PowerShell を使用してライブ イベント ポリシーを設定する
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: PowerShell を使用して Teams でポリシーを設定し、組織内のライブ イベントを保持できるユーザーとイベントで使用できる機能を制御する方法の例。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ef243860ea1450dcd5539d3d5b01025e7eac55cd
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767577"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>PowerShell を使用して Microsoft Teams でのライブ イベント ポリシーを設定する

次の Windows PowerShell コマンドレットを使用して、Teams のライブ イベントのポリシー設定を設定および割り当てることができます。

- [Get-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy)
- [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy)
- [New-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy)
- [Grant-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy)
- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment)

以下にいくつかの例を示します。

> [!NOTE]
> これらのコマンドレットを実行する前に、Skype for Business Online PowerShell に接続する必要があります。 詳細については、「[Microsoft 365 で Skype for Business Online を管理する」または「Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)」を参照してください。

## <a name="allow-users-to-schedule-live-events"></a>ユーザーがライブ イベントをスケジュールできるようにする

> [!NOTE]
> これらの例は、Teams で生成されたイベント用です。

### <a name="allow-a-user-to-schedule-live-events"></a>ユーザーがライブ イベントをスケジュールできるようにする

ユーザーにグローバル ポリシーが割り当てられている場合、*AllowBroadcastScheduling* パラメーターが *True* に設定されていることを実行して確認します。

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```

次に、ユーザーをグローバル ポリシーに割り当て、次を実行します。

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>ユーザーのシナリオ

#### <a name="you-want-all-users-in-your-organization-to-be-able-to-schedule-live-events"></a>組織内のすべてのユーザーがライブ イベントをスケジュールできるようにする

ユーザーにグローバル ポリシーが割り当てられている場合は、 *AllowBroadcastScheduling* が True に設定されていることを実行して確認 *します*。

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```

ユーザーにグローバル ポリシー以外のポリシーが割り当てられている場合、*AllowBroadcastScheduling** が *True* に設定されていることを実行して確認します。

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

#### <a name="you-want-live-events-scheduling-to-be-disabled-across-your-organization"></a>組織全体でライブ イベントのスケジュール設定を無効にする場合

ライブ イベントのスケジュール設定を無効にし、次を実行します。

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```

組織内のすべてのユーザーをグローバル ポリシーに割り当て、次を実行します。

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

#### <a name="you-want-a-large-number-of-users-to-be-able-to-schedule-live-events-and-prevent-a-set-of-users-from-scheduling-them"></a>多数のユーザーがライブ イベントをスケジュール設定し、一連のユーザーがそれらをスケジュールできないようにする必要がある

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

#### <a name="you-want-to-disable-live-event-scheduling-for-a-large-number-of-the-users-and-allow-a-set-of-users-to-schedule-them"></a>多数のユーザーのライブ イベント スケジュール設定を無効にし、一連のユーザーがそれらをスケジュール設定できるようにする場合

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
