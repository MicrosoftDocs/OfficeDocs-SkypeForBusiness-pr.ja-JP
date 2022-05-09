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
- Microsoft Cloud for Retail
description: スケジュール管理のためにシフト所有者を管理する方法について説明します。 チーム メンバーのアクセス許可をスケジュール所有者に昇格するポリシーを設定できます。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
- microsoftcloud-retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 12cf33f193e7f1d1a976e5cde8612df19108cb69
ms.sourcegitcommit: 159399f2325af644c20551925c1fa34bf76aad43
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2022
ms.locfileid: "62288635"
---
# <a name="schedule-owner-for-shift-management"></a>シフト管理のスケジュール所有者

## <a name="overview"></a>概要

スケジュール所有者機能を使用すると、チーム メンバーのアクセス許可を昇格して、従業員をチームの所有者にすることなくスケジュールを管理できます。 スケジュール所有者のアクセス許可を持つ従業員は、チーム チャネルの更新、編集、削除などの他のチーム プロパティを変更することなく、チームのスケジュールを管理できます。

スケジュール所有者のアクセス許可を持つユーザーは何を行うことができますか?

- スケジュールを作成、編集、発行して、チームのシフト割り当てを管理します。
- シフトをスワップし、オープン シフトを受け取る要求を含むシフト要求を表示および承認します。
- Shifts で設定を管理し、チームの特定の機能を有効にします。
- 従業員の給与を処理するために、チームのタイムシートを表示および変更します。

## <a name="why-schedule-owner"></a>所有者のスケジュールを設定する理由

スケジュール所有者機能を使用しないと、日常のビジネス機能が中断される可能性があります。 チームの所有者はチームの実行に役立ちますが、必ずしも日常的なスケジュール設定の担当者であるとは限りません。 この場合、スケジュール管理の責任のみを別のチーム メンバーに転送すると、チーム内の日常業務が効率化され、同じアクセス特権を持つ 2 人のチーム メンバーの混乱が解消されます。

## <a name="scenario"></a>シナリオ

組織で所有者のスケジュール機能を使用する方法の例を次に示します。

あなたは、部署マネージャーがストア マネージャーに直接報告する大規模な組織で働いています。 ストア マネージャーは、社内でより多くの権限を持ち、Shifts のチーム所有者です。 一方、部門マネージャーは、チーム メンバーとして Shifts にのみ追加されます。 店長は部署のマネージャーよりも年功序列が高い一方で、部署マネージャーがチームの従業員の日常的なスケジュールを処理する方が理にかなっています。

*スケジュール所有者が存在しない場合*、部門マネージャーには、チームの所有者とまったく同じ特権が与えられている必要があります。 最近、部署のマネージャーが情報を移動し、チャネルの名前を変更し、店長の仕事に問題を引き起こしています。 店長は、部署のマネージャーがスケジュールを整理できることを望んでいますが、シフトの外部でチームの他の何かを変更できないようにしたいと考えています。

*スケジュール所有者を使用すると*、他のチーム所有者特権なしで、部門マネージャーにスケジュール設定特権を付与できます。

## <a name="manage-schedule-ownership"></a>スケジュールの所有権を管理する

管理者は、ポリシーを使用して、組織の管理所有権のスケジュールを制御します。 これらのポリシーは、次の PowerShell コマンドレットを使用して管理します。

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy?view=teams-ps)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy?view=teams-ps)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy?view=teams-ps)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy?view=teams-ps)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy?view=teams-ps)

### <a name="example-1"></a>例 1

ここでは、ScheduleOwnerPolicy という名前の新しいポリシーを作成し、スケジュール所有者機能を有効にします。

```powershell
New-CsTeamsShiftsPolicy –Identity ScheduleOwnerPolicy  -EnableScheduleOwnerPermissions $true -AccessType UnrestrictedAccess_TeamsApp
```

### <a name="example-2"></a>例 2

この例では、ScheduleOwnerPolicy という名前のポリシーを remy@contoso.com という名前のユーザーに割り当てます。

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName ScheduleOwnerPolicy
```

## <a name="related-articles"></a>関連記事

- [Teams で組織のシフト アプリを管理する](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teamsでフロントライン ワーカーのシフトベースのアクセスを管理する](manage-shift-based-access-flw.md) 
