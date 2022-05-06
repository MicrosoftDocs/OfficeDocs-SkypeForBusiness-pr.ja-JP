---
title: Teamsでフロントライン ワーカーのシフトベースのアクセスを管理する
author: SerdarSoysal
ms.author: serdars
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 組織内の Frontline Workers のTeamsでシフトベースのアクセスを管理する方法について説明します。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: d177ac362b7b8c0d1f91be5322fb49696a5cc9b7
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393489"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Teamsでフロントライン ワーカーのシフトベースのアクセスを管理する
## <a name="overview"></a>概要

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft Teamsのプレゼンスは、他のユーザーに対するユーザーの現在の可用性と状態を示します。 フロントラインワーカーの存在は、通常、毎日同じではないため、他のスタッフよりも予測不可能です。 管理者は、組織内のフロントライン ワーカーのシフトベースのプレゼンス状態のセットを表示するようにTeamsを構成して、シフトのオンとオフのタイミングを示すことができます。

これらのシフトベースのプレゼンス状態&mdash;![Solid 緑色のチェック マークは、On shift を示します。](../../media/flw-presence-on-shift.png) **Shift の場合**、 ![灰色の円と x はオフシフトを示します。](../../media/flw-presence-off-shift.png) **オフ シフト** (![赤丸) は、ビジー **状態**&mdash;](../../media/flw-presence-busy.png)を示し、Teams [の既定のプレゼンス状態のセット](../../presence-admins.md)とは別の値を示します。 この 2 つのプレゼンス状態セットを使用すると、組織内のユーザーのロールに基づいてさまざまなエクスペリエンスを構成できます。

シフトベースのアクセスを使用すると、フロントライン ワーカーがシフトオフのときにTeamsへのアクセスを管理できます。 たとえば、Teamsを設定して、フロントライン ワーカーがスケジュールされたシフトに入っていないときにTeamsを使用する前に確認する必要があるメッセージを表示できます。  

## <a name="scenario"></a>シナリオ

組織がシフトベースのアクセスを管理する方法の例を次に示します。

組織内には、上司がスケジュールして承認したシフトで働く時間に対してのみ支払われる必要があるフロントライン ワーカーがいます。 スケジュールされたシフト外での作業に費やされた時間 (Teams アプリの使用を含む) に対して支払われるべきではありません。 "オフシフト時のTeams時間は未払い時間にカウントされません"というカスタム メッセージを設定しました。これは、フロントライン ワーカーがシフトオフ時にTeamsにアクセスしようとしたときに表示されます。 ユーザーがTeamsを使用することを選択した場合、この時点では支払われないことを理解して [**同意** する] をクリックします。

また、組織内には、給与を受け、シフト勤務をしていないインフォメーション ワーカーがいます。 フロントライン ワーカーにシフトベースのプレゼンスを提供しながら、Teamsで既定のプレゼンス状態を使用するようにインフォメーション ワーカーを構成します。

## <a name="shift-based-presence-states"></a>シフトベースのプレゼンス状態

シフトベースのプレゼンス状態を次に示します。

|アプリが設定 |ユーザーが設定  |詳細情報  |
|---------|---------|---------|
|![緑色のチェック マークが点灯し、オンシフトを示します。](../../media/flw-presence-on-shift.png) シフト時     |         |シフトの開始時に自動的に設定する         |
|![灰色の円と x、オフシフトを示します](../../media/flw-presence-off-shift.png) オフシフト     |         |シフトの最後に自動的に設定する         |
|![塗りつぶした赤い丸は、取り込み中を示します。](../../media/flw-presence-busy.png) 取り込み中      | ![塗りつぶした赤い丸は、取り込み中を示す](../../media/flw-presence-busy.png) 取り込み中         |自動的に設定されます。 フロントライン ワーカーがシフト時に手動で設定することもできます。|

## <a name="off-shift-access-to-teams"></a>Teamsへのシフト アクセスをオフにする

この機能を使用すると、フロントライン ワーカーがシフトオフのときにTeamsへのアクセスを管理できます。 シフトオフ時にTeamsにアクセスする場合は、フロントライン ワーカーにメッセージを表示するようにTeamsを設定できます。 フロントライン ワーカーは、Teamsを使用する前に、[**同意** する] をクリックしてメッセージを確認する必要があります。

既定のメッセージを使用したり、定義済みのメッセージのセットから選択したり、必要なテキストを表示するようにメッセージをカスタマイズしたりできます。 既定のメッセージは次のとおりです。

![既定のメッセージのスクリーンショット。](../../media/shifts-presence-message.png)

メッセージが表示される頻度を設定し、最初のシフトが開始されたときから最後のシフトが終了するまでの猶予期間と、Teamsへのアクセスが制限されるまでの猶予期間を設定することもできます。

## <a name="manage-shift-based-access"></a>シフトベースのアクセスを管理する

管理者は、ポリシーを使用して、組織内のフロントライン ワーカーのシフトベースのプレゼンスを制御します。 これらのポリシーは、次の PowerShell コマンドレットを使用して管理します。

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

New-CsTeamsShiftsPolicy コマンドレットを使用して新しいポリシーを作成し、必要なポリシー設定を設定してから、Grant-CsTeamsShiftsPolicy コマンドレットを使用してポリシーをユーザーに割り当てます。

次に例を示します。 選択できる定義済みのオフ シフト メッセージの一覧など、各ポリシー設定とパラメーターの詳細については、「 [New-CsTeamsShiftsPolicy」を](/powershell/module/teams/new-csteamsshiftspolicy)参照してください。

### <a name="example-1"></a>例 1

この例では、Off Shift Teams Access Default Message という名前の新しいポリシーを作成します。 このポリシーでは、シフトベースのプレゼンスがオンになり、このポリシーが割り当てられているユーザーがシフトオフ時にTeamsにアクセスするたびに既定のメッセージが表示されます。 ユーザーは、メッセージを受け入れる場合はオフシフト時にTeamsを使用できます。また、最初のシフトが開始されたときから最後のシフトが終了するまでの猶予期間とアクセスが制限されたときの猶予期間は 10 分です。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> **ShiftNoticeMessageType** パラメーターを使用して、表示するメッセージを設定します。 このパラメーターに対して選択できる定義済みのメッセージの一覧については、「 [New-CsTeamsShiftsPolicy」を](/powershell/module/teams/new-csteamsshiftspolicy)参照してください。

### <a name="example-2"></a>例 2 

この例では、Off Shift Teams Access Custom Message という名前の新しいポリシーを作成します。 このポリシーでは、シフトベースのプレゼンスがオンになり、このポリシーが割り当てられているユーザーがシフトオフ時にTeamsにアクセスするたびにカスタム メッセージが表示されます。 ユーザーは、メッセージを受け入れる場合はオフシフト時にTeamsを使用でき、最初のシフトが開始されたときから最後のシフトが終了するまでの猶予期間と、アクセスが制限されたときは 15 分です。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> **ShiftNoticeMessageType** パラメーターを使用して、表示するメッセージを設定します。 詳細については、「 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)」を参照してください。

### <a name="example-3"></a>例 3

この例では、Off Shift Teams Access Message1 という名前の新しいポリシーを作成します。 このポリシーでは、シフトベースのプレゼンスがオンになり、このポリシーが割り当てられているユーザーがシフトオフ時にTeamsにアクセスするたびに、次の定義済みメッセージが表示されます。

  "あなたの雇用主は、非勤務時間中に非免除または時間単位の従業員によるネットワーク、アプリケーション、システム、またはツールの使用を承認または承認しません。 受け入れることで、オフシフト中のTeamsの使用が承認されておらず、補正されないことを認めます。 

ユーザーは、メッセージを受け入れる場合はオフシフト時にTeamsを使用でき、最初のシフトが開始されたときから最後のシフトが終了するまでの猶予期間は 3 分です。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> **ShiftNoticeMessageType** パラメーターを使用して、表示するメッセージを設定します。 このパラメーターに対して選択できる定義済みのメッセージの一覧については、「 [New-CsTeamsShiftsPolicy」を](/powershell/module/teams/new-csteamsshiftspolicy)参照してください。

### <a name="example-4"></a>例 4

この例では、Off Shift Teams Access Custom Message という名前のポリシーを、remy@contoso.com という名前のユーザーに割り当てます。

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>関連項目

- [Teams で組織のシフト アプリを管理する](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams での PowerShell の概要](../../teams-powershell-overview.md)