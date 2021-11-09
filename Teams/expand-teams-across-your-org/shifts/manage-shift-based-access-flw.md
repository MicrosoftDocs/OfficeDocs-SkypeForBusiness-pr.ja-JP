---
title: フロントライン ワーカーのシフトベースのアクセスを管理Teams
author: HowlinWolf-92
ms.author: v-mahoffman
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 組織内の Frontline Worker の Teamsにシフトベースのアクセスを管理する方法について学習します。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 708ce6158cd799bed506751006d94679eedcd950
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60842599"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>フロントライン ワーカーのシフトベースのアクセスを管理Teams

> [!IMPORTANT]
> 2020 年 6 月 30 日をもって、Microsoft Staffhub は廃止されました。 Microsoft では、StaffHub の機能を Microsoft Teams に組み込む作業に取り組んでいます。 現在、Teams にはシフト アプリのスケジュール管理機能が含まれています。今後、他の機能もロールアウトされる予定です。 StaffHub は 2020 年 6 月 30 日をもって、すべてのユーザーがご利用できなくなりました。 ユーザーが StaffHub を開くと、Teams をダウンロードするように求めるメッセージが表示されます。 詳細については、「[Microsoft StaffHub は廃止されました](microsoft-staffhub-to-be-retired.md)」を参照してください。  

## <a name="overview"></a>概要

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

[プレゼンス] Microsoft Teamsユーザーの現在の可用性と他のユーザーの状態を示します。 フロントライン ワーカーの存在は、通常は毎日同じではならず、他のスタッフよりも予測が難しい場合があります。 管理者は、Teams を構成して、組織内のフロントライン ワーカーがシフトのオンとオフを示す一連のシフトベースのプレゼンス状態を表示できます。

これらのシフトベースのプレゼンス状態は緑色 &mdash; ![ の単色のチェック マークで、シフト時を示します。](../../media/flw-presence-on-shift.png) **Shift の場合**、 ![ 灰色の円と x はオフ シフトを示します。](../../media/flw-presence-off-shift.png) **Shift をオフ** にし、赤色の丸で囲み、ビジー状態が、既定のプレゼンス状態セットと異な ![ ](../../media/flw-presence-busy.png)  &mdash; Teams。 [](../../presence-admins.md) これら 2 つのプレゼンス状態のセットでは、その役割に基づいて組織内のユーザーに対して異なるエクスペリエンスを構成できます。

シフトベースのアクセスを使用すると、フロントラインワーカーがシフトTeamsのアクセスを管理できます。 たとえば、Teams を設定して、スケジュールされたシフトに移動していない場合に、フロントラインワーカーが Teams を使用する前に確認する必要があるメッセージを表示できます。  

## <a name="scenario"></a>シナリオ

組織でシフトベースのアクセスを管理する方法の例を次に示します。

組織内のフロントライン ワーカーは、マネージャーがスケジュールおよび承認したシフトで作業する時間に対してのみ支払う必要があります。 スケジュールされたシフトの外で作業に費やされた時間に対して支払いを行う必要があります。これには、スケジュールされたアプリの使用Teamsがあります。 「シフトをオフにした場合の Teams の時間は未払い時間にカウントされません」というカスタム メッセージを設定します。これは、フロントラインワーカーがシフト外の場合に Teams にアクセスしようとするときに表示されます。 ユーザーがアプリを使用Teams、この時間の支払いを受け取らないという理解を得て [同意する] をクリックします。

また、組織内に、サラリーマンであり、シフトを使用しない情報ワーカーもいます。 フロント ライン ワーカーにシフト ベースのプレゼンスを提供しながら、Teams の既定のプレゼンス状態を使用する情報ワーカーを構成します。

## <a name="shift-based-presence-states"></a>シフトベースのプレゼンス状態

シフトベースのプレゼンス状態を次に示します。

|アプリが設定 |ユーザーが設定  |詳細情報  |
|---------|---------|---------|
|![緑色の単色のチェック マークは、[シフト時] を示します。](../../media/flw-presence-on-shift.png) シフト時     |         |シフトの開始時に自動的に設定する         |
|![x を含む灰色の円、オフ シフトを示します。](../../media/flw-presence-off-shift.png) シフトをオフにする     |         |シフトの最後に自動的に設定する         |
|![塗りつぶした赤い丸は、取り込み中を示します。](../../media/flw-presence-busy.png) 取り込み中      | ![塗りつぶした赤い丸は、取り込み中を示す](../../media/flw-presence-busy.png) 取り込み中         |自動的に設定されます。 フロントライン ワーカーがシフト中のときに手動で設定することもできます。|

## <a name="off-shift-access-to-teams"></a>シフトをオフにし、Teams

この機能を使用すると、フロントライン ワーカーがシフトTeamsにアクセスするユーザーを管理できます。 シフトをオフにTeamsにアクセスする場合は、フロントライン worker にメッセージを表示Teamsを設定できます。 フロントライン ワーカーは、メッセージを **使用する前** に [同意する] をクリックしてメッセージをTeams。

既定のメッセージを使用したり、一連の定義済みメッセージから選択したり、メッセージをカスタマイズして必要なテキストを表示することができます。 既定のメッセージを次に示します。

![既定のメッセージのスクリーンショット。](../../media/shifts-presence-message.png)

また、メッセージが表示される頻度を設定し、最初のシフトの開始または最後のシフトの終了と、メッセージへのアクセスが制限されているTeams設定できます。

## <a name="manage-shift-based-access"></a>シフトベースのアクセスを管理する

管理者は、ポリシーを使用して、組織内のフロントライン ワーカーのシフトベースのプレゼンスを制御します。 これらのポリシーは、次の PowerShell コマンドレットを使用して管理します。

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

New-CsTeamsShiftsPolicy コマンドレットを使用して新しいポリシーを作成し、必要なポリシー設定を設定した後、Grant-CsTeamsShiftsPolicy コマンドレットを使用してポリシーをユーザーに割り当てします。

次に例を示します。 選択できる定義済みのオフ シフト メッセージの一覧など、各ポリシー設定とパラメーターの詳細については [、「New-CsTeamsShiftsPolicy」](/powershell/module/teams/new-csteamsshiftspolicy)を参照してください。

### <a name="example-1"></a>例 1

この例では、既定のメッセージにアクセスするために、Shift キーを使用Teams新しいポリシーを作成します。 このポリシーでは、シフトベースのプレゼンスが有効になっていて、このポリシーが割り当てられているユーザーがシフトをオフにするときに、そのポリシーにアクセスTeamsメッセージが表示されます。 ユーザーは、メッセージを受け入れる場合はシフトをオフにするときに Teams を使用できます。最初のシフトが開始または最後のシフトが終了し、アクセスが制限されている場合の猶予期間は 10 分です。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> **ShiftNoticeMessageType パラメーターを使用** して、表示するメッセージを設定します。 このパラメーターに対して選択できる定義済みのメッセージの一覧を表示するには [、New-CsTeamsShiftsPolicy を参照してください](/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-2"></a>例 2 

この例では、"Shift オフ" という名前の新しいポリシーを作成し、Teams メッセージにアクセスします。 このポリシーでは、シフトベースのプレゼンスが有効になっていて、このポリシーが割り当てられているユーザーがシフトをオフにするときにユーザーがアクセスするTeamsメッセージが表示されます。 ユーザーは、メッセージを受け入れる場合はシフトをオフにするときに Teams を使用できます。最初のシフトが開始または最後のシフトが終了し、アクセスが制限されている場合の猶予期間は 15 分です。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> **ShiftNoticeMessageType パラメーターを使用** して、表示するメッセージを設定します。 詳細については [、New-CsTeamsShiftsPolicy に関するページを参照してください](/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-3"></a>例 3

この例では、Off Shift という名前の新しいポリシーを作成し、Access Message1 Teams作成します。 このポリシーでは、シフトベースのプレゼンスが有効になっていて、このポリシーが割り当てられているユーザーがシフトをオフにすると、そのポリシーにアクセスするユーザーがTeamsメッセージが表示されます。

  "雇用主は、非勤務時間中に、非免除または時間給の従業員によるネットワーク、アプリケーション、システム、またはツールの使用を承認または承認していません。 これを受け入れて、シフト外のTeamsの使用が承認されていないこと、および補正されていないことを確認します。" 

ユーザーは、メッセージを受け入れる場合はシフトをオフにするときに Teams を使用できます。また、最初のシフトが開始または最後のシフトが終了し、アクセスが制限されている場合の猶予期間は 3 分です。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> **ShiftNoticeMessageType パラメーターを使用** して、表示するメッセージを設定します。 このパラメーターに対して選択できる定義済みのメッセージの一覧を表示するには [、New-CsTeamsShiftsPolicy を参照してください](/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-4"></a>例 4

この例では、Off Shift という名前のポリシーを割り当Teams Access カスタム メッセージ] という名前のユーザーに remy@contoso.com。

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>関連項目

- [Teams で組織のシフト アプリを管理する](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams での PowerShell の概要](../../teams-powershell-overview.md)