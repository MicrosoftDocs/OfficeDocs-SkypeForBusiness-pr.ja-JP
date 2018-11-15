---
title: PowerShell を使用して、マイクロソフトのチームでのライブ イベントのポリシーを設定するのには
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
description: PowerShell を使用して、チーム、組織と機能でのライブ イベントを押しながらユーザーを制御するためにポリシーを設定する方法の例では、自分で作成したイベントで使用できます。
appliesto:
- Microsoft Teams
ms.openlocfilehash: f802c2b67c0a4cd4b0838dd9aeec9c4bbf884968
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "26535940"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>PowerShell を使用して、マイクロソフトのチームでのライブ イベントのポリシーを設定するのには
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

設定し、チームでのライブ イベントのポリシー設定を割り当てるには、次の Windows PowerShell コマンドレットを使用できます。 
- [Get CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [セット CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [新しい-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [許可 CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

いくつかの例を次に示します。

## <a name="allow-users-to-schedule-live-events"></a>ライブ イベントのスケジュールを設定するユーザーを許可します。 

> [!NOTE]
> クイック スタートのイベントのこれらの例を示します。 外部エンコーダーのイベントは、追加の手順を行う必要がありますがあります。 詳細については、[外部のエンコーダーのイベントをスケジュールするのにはユーザーを有効にする](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events)を参照してください。

**ライブ イベントのスケジュールを設定するユーザーを許可します。**

ユーザーには、グローバル ポリシーが割り当てられているが場合、は、実行し、 *AllowBroadcastScheduling*パラメーターが*True*に設定されていることを確認します。
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
グローバル ポリシーの実行にユーザーを割り当てます。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>ユーザー シナリオ
**ライブ イベントのスケジュールを設定することができる、組織内のすべてのユーザーをします。**

実行し、確認の場合はユーザーには、グローバル ポリシーが割り当てられているが、その*AllowBroadcastScheduling* * が*True*に設定します。
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
以外のグローバル ポリシーのポリシーを割り当てると、ユーザー場合は、実行し、 *-AllowBroadcastScheduling*が*True*に設定されていることを確認します。
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**ライブ イベントを組織全体で無効にするスケジュールを設定します。**

ライブ イベントのスケジュールを無効にするには、実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
グローバル ポリシーの実行には、組織内のすべてのユーザーを割り当てます。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**スケジュールを設定できるユーザーの数が多いライブ イベントと、一連のユーザーがそれらのスケジュールを設定するを防止します。**

実行し、 *AllowBroadcastScheduling*を*True*に設定されていることを確認します。
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
グローバル ポリシーの実行にユーザーまたはユーザーを割り当てます。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

ライブ イベントの実行をスケジュール設定は、新しいポリシーを作成します。
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingpolicy
```
ライブ イベントのスケジュールを無効にするには、実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
このポリシーの実行にユーザーを割り当てます。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
**ライブ イベントを多数のユーザーのスケジュールを無効にしてそれらをスケジュールするのにはユーザーのセットを許可します。**

ライブ イベントのスケジュールを無効にするには、実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
グローバル ポリシーの実行にこれらのユーザーを割り当てます。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
ライブ イベントのスケジュールを許可する、実行するポリシーを作成します。
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
ライブ イベントのスケジュール設定を有効にするを実行します。
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
このポリシーの実行にユーザーを割り当てます。
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>ライブ イベントに参加できるユーザーを設定します
 
ユーザーがそのすべてのユーザー、匿名ユーザーを含むイベントを作成することができますへの参加、実行できるようにするグローバル ポリシーを設定します。
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>ライブ イベントの記録] オプションを設定します。
> [!NOTE]
> この設定は、クイック スタートのイベントにのみ適用されます。

ライブ イベントの記録を無効にするグローバル ポリシーを設定します。
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-transcription-and-translation-in-live-events-coming-soon"></a>(準備中) のライブ イベントでの議事録作成と翻訳を設定します。
> [!NOTE]
> この設定は、クイック スタートのイベントにのみ適用されます。 

イベントの参加者議事録作成と翻訳を有効にするグローバル ポリシーを設定します。
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>関連トピック
- [チームのライブ イベントを設定します。](set-up-for-teams-live-events.md)


