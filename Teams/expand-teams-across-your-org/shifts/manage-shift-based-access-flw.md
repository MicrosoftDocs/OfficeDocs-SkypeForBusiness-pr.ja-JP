---
title: Teams で Firstline Worker のシフトベースのアクセスを管理する
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 組織内の Firstline Worker 用 Teams でシフトベースのアクセスを管理する方法について学習します。
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b73fe9b3c4b39e7d3fa7b31427f563c47e5a737
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823017"
---
# <a name="manage-shift-based-access-for-firstline-workers-in-teams"></a>Teams で Firstline Worker のシフトベースのアクセスを管理する

> [!IMPORTANT]
> Microsoft StaffHub は 2020 年 6 月 30 日に廃止されました。 Microsoft では、StaffHub の機能を Microsoft Teams に組み込む作業に取り組んでいます。 現在、Teams にはシフト アプリのスケジュール管理機能が含まれています。今後、他の機能もロールアウトされる予定です。 StaffHub は、2020 年 6 月 30 日にすべてのユーザーの作業を停止しました。 StaffHub を開しようとすると、Teams のダウンロードを指示するメッセージが表示されます。 詳細については [、Microsoft StaffHub の廃止に関するページを参照してください](microsoft-staffhub-to-be-retired.md)。  

## <a name="overview"></a>概要

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft Teams のプレゼンスは、他のユーザーに対するユーザーの現在の状態を示します。 通常、ファーストライン ワーカーのプレゼンスは他のスタッフよりも予測が難しく、通常は毎日同じではありません。 管理者は、組織内の Firstline Worker のシフトベースのプレゼンス状態のセットを表示して、シフトのオンとオフを示す一連のプレゼンス状態を表示する Teams を構成できます。

これらのシフトベースのプレゼンス状態は、緑色の単色のチェック マーク、シフト時のオンシフト &mdash; ![ ](../../media/flw-presence-on-shift.png)  ![ 、x ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; [](../../presence-admins.md)を含む灰色の円、オフシフトオフシフト、単色の赤い円、取り込み中が Teams の既定のプレゼンス状態のセットから分離された状態を示します。 これら 2 セットのプレゼンス状態では、その役割に基づいて組織内のユーザーに異なるエクスペリエンスを構成できます。

シフトベースのアクセスでは、Firstline Worker がシフトオフのときに Teams へのアクセスを管理できます。 たとえば、スケジュールされたシフトに移動していない場合に、Firstline Worker が Teams を使用する前に認識する必要があるメッセージを表示する Teams を設定できます。  

## <a name="scenario"></a>シナリオ

組織でシフトベースのアクセスを管理する方法の例を次に示します。

組織内に Firstline Worker がいて、マネージャーがスケジュールして承認したシフトで作業する時間に対する支払いのみを行う必要があります。 Teams アプリの使用を含む、スケジュールされたシフト外での作業に費やされた時間に対する支払いを行う必要があります。 "オフ シフト時の Teams の時間は支払い時間にカウントされません" というカスタム メッセージを設定すると、Firstline Worker がシフト外のときに Teams にアクセスしようとするときに表示されます。 Teams の使用を選択した場合、この時間の支払いは行えなという理解を得て [同意する] をクリックします。

また、組織内に、サラリーマンやシフトを働かしない情報提供者もいます。 ファーストライン ワーカーにシフトベースのプレゼンスを提供しながら、Teams で既定のプレゼンス状態を使用する情報ワーカーを構成します。

## <a name="shift-based-presence-states"></a>シフトベースのプレゼンス状態

シフトベースのプレゼンス状態は次のとおりです。

|アプリが設定 |ユーザーが設定  |詳細情報  |
|---------|---------|---------|
|![緑色の単色のチェック マーク、シフト時を示す](../../media/flw-presence-on-shift.png) シフト時     |         |シフトの最初に自動的に設定する         |
|![x が付く灰色の円はオフ シフトを示す](../../media/flw-presence-off-shift.png) オフ シフト     |         |シフトの最後に自動的に設定する         |
|![塗りつぶした赤い丸は、取り込み中を示す](../../media/flw-presence-busy.png) 取り込み中      | ![塗りつぶした赤い丸は、取り込み中を示す](../../media/flw-presence-busy.png) 取り込み中         |自動的に設定されます。 また、Firstline Worker がシフト中に手動で設定することもできます。|

## <a name="off-shift-access-to-teams"></a>Teams へのシフトアクセスをオフにする

この機能を使用すると、Firstline Worker がシフトオフのときに Teams へのアクセスを管理できます。 シフトをオフに Teams にアクセスする場合は、メッセージを Firstline Worker に表示する Teams を設定できます。 Firstline Worker は、Teams を **使用する前** に、[承諾] をクリックしてメッセージを確認する必要があります。

既定のメッセージを使用したり、事前に定義されたメッセージのセットから選択したり、メッセージをカスタマイズして必要なテキストを表示することができます。 既定のメッセージを次に示します。

![既定のメッセージのスクリーンショット](../../media/shifts-presence-message.png)

また、メッセージが表示される頻度を設定し、最初のシフトの開始または最後のシフトの終了から Teams へのアクセスが制限される期間の猶予期間を設定できます。

## <a name="manage-shift-based-access"></a>シフトベースのアクセスを管理する

管理者は、ポリシーを使用して、組織内の Firstline Worker のシフトベースのプレゼンスを制御します。 これらのポリシーを管理するには、次の PowerShell コマンドレットを使用します。

- [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

New-CsTeamsShiftsPolicyコマンドレットを使用して新しいポリシーを作成し、必要なポリシー設定を設定し、Grant-CsTeamsShiftsPolicy コマンドレットを使用してユーザーにポリシーを割り当てる。

次に例を示します。 選択できる定義済みのオフシフト メッセージの一覧など、各ポリシー設定とパラメーターの詳細については [、「New-CsTeamsShiftsPolicy」](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)を参照してください。

### <a name="example-1"></a>例 1

この例では、"オフ Shift Teams Access の既定のメッセージ" という名前の新しいポリシーを作成します。 このポリシーでは、シフトベースのプレゼンスが有効になっていて、このポリシーが割り当てられているユーザーがシフト外のときに Teams にアクセスすると、既定のメッセージが毎回表示されます。 ユーザーは、メッセージを受け入れる場合に Teams をオフシフトで使用し、最初のシフトの開始または最後のシフトの終了からアクセスが制限された時間が 10 分の猶予期間を使用できます。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> **ShiftNoticeMessageType パラメーター** を使用して、表示するメッセージを設定します。 このパラメーターから選択できる定義済みメッセージの一覧を表示するには [、「New-CsTeamsShiftsPolicy」を参照してください](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-2"></a>例 2 

この例では、"オフ Shift Teams Access カスタム メッセージ" という名前の新しいポリシーを作成します。 このポリシーでは、シフトベースのプレゼンスが有効になっていて、このポリシーが割り当てられているユーザーがシフトをオフにするときに Teams にアクセスするごとに、カスタム メッセージが表示されます。 ユーザーは、メッセージを受け入れる場合に Teams をオフシフトで使用し、最初のシフトの開始または最後のシフトの終了からアクセスが制限される時間が 15 分の猶予期間を使用できます。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> **ShiftNoticeMessageType パラメーター** を使用して、表示するメッセージを設定します。 詳細については [、New-CsTeamsShiftsPolicy を参照してください](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-3"></a>例 3

この例では、Off Shift Teams Access Message1 という名前の新しいポリシーを作成します。 このポリシーでは、シフトベースのプレゼンスが有効になっていて、このポリシーが割り当てられているユーザーがシフト外のときに Teams にアクセスすると、次の定義済みメッセージが毎回表示されます。

  "雇用主は、非適用従業員または非勤務時間の従業員によるネットワーク、アプリケーション、システム、またはツールの使用を承認または承認していません。 受け入れにより、オフシフト中の Teams の使用が承認されていないことと、ユーザーが補償を受け取らなされていないことに同意したと見なされます。" 

ユーザーは、メッセージを受け入れる場合に Teams をオフシフトで使用し、最初のシフトの開始または最後のシフトの終了からアクセスが制限される時間が 3 分の猶予期間を使用できます。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> **ShiftNoticeMessageType パラメーター** を使用して、表示するメッセージを設定します。 このパラメーターから選択できる定義済みメッセージの一覧を表示するには [、「New-CsTeamsShiftsPolicy」を参照してください](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-4"></a>例 4

この例では、"オフ Shift Teams Access カスタム メッセージ" という名前のポリシーを remy@contoso.com という名前のユーザーに割り当remy@contoso.com。

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>関連項目

- [Teams で組織の Shifts アプリを管理する](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams での PowerShell の概要](../../teams-powershell-overview.md)
