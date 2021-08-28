---
title: シフト管理のスケジュール所有者を管理する
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: スケジュール管理のためにシフト所有者を管理する方法について説明します。 チーム メンバーのアクセス許可をスケジュール所有者に昇格するポリシーを設定できます。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 702ca0fd5b392755b1966d16024d5ecf10cdacab
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627539"
---
# <a name="schedule-owner-for-shift-management"></a>シフト管理の所有者をスケジュールする

## <a name="overview"></a>概要

スケジュール所有者は、従業員をチーム所有者にすることなく、チーム メンバーのアクセス許可をスケジュール所有者に昇格できる機能です。 つまり、従業員は、チーム チャネルの更新、編集、削除などの他のチーム プロパティを変更することなく、チームのスケジュールを管理する権限を持っています。

所有者アクセス許可のスケジュールを持つユーザーは何ができますか?

- スケジュールを作成、編集、発行して、チームのシフト割り当てを管理します。
- シフトを交換し、オープン シフトを取る要求を含むシフト要求を表示および承認します。
- チームの特定の機能を有効にするには、Shifts で設定を管理します。
- 従業員の給与を処理するために、チームのタイムシートを表示および変更します。

## <a name="why-schedule-owner"></a>所有者のスケジュールを設定する理由

所有者のスケジュール機能がない場合、毎日のビジネス機能が中断される可能性があります。 チーム所有者はチームの実行をサポートしますが、必ずしも毎日のスケジュールの担当者であるとは限りません。 この場合、スケジュール管理の責任のみを別のチーム メンバーに転送すると、チーム内での毎日の操作が合理化され、同じアクセス権限を持つ 2 人のチーム メンバーの混乱が解消されます。

## <a name="scenario"></a>シナリオ

組織で所有者のスケジュール機能を使用する方法の例を次に示します。

大規模な組織で働き、部門マネージャーがストア マネージャーに直接報告します。 ストア マネージャーは、会社内の権限が高く、Shifts のチーム所有者です。 一方、部署のマネージャーは、チーム メンバーとして Shifts にのみ追加されます。 ストア マネージャーは部門マネージャーよりも年長ですが、部門マネージャーはチームの従業員の毎日のスケジュール設定を処理する方が理にかなっています。

*スケジュール所有者を指定しない* 場合、部門管理者には、チーム所有者とまったく同じ権限を付与する必要があります。 最近、部門管理者は情報を移動し、チャネルの名前を変更し、ストア マネージャーの作業に複雑な問題を引き起こしています。 ストア マネージャーは、部門マネージャーがスケジュールを整理できる必要がありますが、シフト以外のチームで他の変更を行うのを望んでいません。

*[所有者のスケジュール*] を使用すると、他のチーム所有者特権を持たなくても、部門マネージャーにスケジュール権限を付与できます。

## <a name="manage-schedule-ownership"></a>スケジュールの所有権を管理する

管理者は、ポリシーを使用して、組織のスケジュール管理所有権を制御します。 これらのポリシーは、次の PowerShell コマンドレットを使用して管理します。

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy?view=teams-ps)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy?view=teams-ps)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy?view=teams-ps)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy?view=teams-ps)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy?view=teams-ps)

### <a name="example-1"></a>例 1

ここでは、ScheduleOwnerPolicy という名前の新しいポリシーを作成し、[所有者のスケジュール] 機能を有効にします。

```powershell
New-CsTeamsShiftsPolicy –Identity ScheduleOwnerPolicy  -EnableScheduleOwnerPermissions $true -AccessType UnrestrictedAccess_TeamsApp
```

### <a name="example-2"></a>例 2

この例では、ScheduleOwnerPolicy という名前のポリシーを、remy@contoso.com という名前のユーザーに割り当 remy@contoso.com。

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName ScheduleOwnerPolicy
```

## <a name="related-articles"></a>関連記事

- [Teams で組織のシフト アプリを管理する](manage-the-shifts-app-for-your-organization-in-teams.md)
- [フロントライン ワーカーのシフトベースのアクセスを管理Teams](manage-shift-based-access-flw.md) 
