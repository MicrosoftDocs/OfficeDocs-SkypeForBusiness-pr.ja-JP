---
title: Microsoft Teams でユーザーにポリシーを割り当てる
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams でユーザーにポリシーを割り当てる方法について説明します。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 5d213c53de22994d46e7d7faf54a8dfd687806d7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821307"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a>Microsoft Teams でユーザーにポリシーを割り当てる

管理者は、ポリシーを使用して、組織のユーザーが利用できる Teams 機能を制御できます。 たとえば、ほんの一例を挙げると、通話ポリシー、会議ポリシー、メッセージ ポリシーなどがあります。

組織には、独自のニーズを持つさまざまなタイプのユーザーがあり、カスタム ポリシーを作成して割り当てることで、それらのニーズに応じて、さまざまなユーザーのセットにポリシー設定を調整できます。

組織でのポリシーの管理を容易にするために、Teams はユーザーにポリシーを割り当てるいくつかの方法を提供しています。 個別に、一括割り当てで、またはユーザーがメンバーになっているグループを介して、ポリシーをユーザーに直接割り当てることができます。 ポリシー パッケージを使用して、ポリシーの既定のコレクションを、同様の役割を持つ組織内のユーザーに割り当てることもできます。 選択するオプションは、管理しているポリシーの数と、割り当てているユーザーの数によって異なります。 グローバルな （組織全体の既定の） ポリシーを設定して、それらが組織内の最大数のユーザーに適用されるようにすることで、特殊なポリシーを必要とするユーザーにポリシーを割り当てるだけで済みます。

この記事では、ユーザーにポリシーを割り当てるさまざまな方法と、何をいつ使用するかについての推奨シナリオについて説明します。

## <a name="which-policy-takes-precedence"></a>どのポリシーが優先されますか?

ユーザーには、ポリシーの種類ごとに 1 つの有効なポリシーがあります。 ユーザーに直接ポリシーが割り当てられていてもかまいません。同じ種類のポリシーが割り当てられている 1 つ以上のグループのメンバーでもある可能性があります。 このようなシナリオでは、どのポリシーが優先されますか?  ユーザーの有効なポリシーは、次の優先規則に従って決定されます。

ユーザーに直接ポリシーが割り当てられている場合 （個別に、またはバッチ割り当てによって）、そのポリシーが優先されます。 次の例では、ユーザーの有効なポリシーは、ユーザーに直接割り当てられている Lincoln Square の会議ポリシーです。

![直接割り当てられたポリシーの優先順位を示す図](media/assign-policies-example-directly-assigned.png)

ユーザーに特定の種類のポリシーが直接割り当てられていない場合は、そのユーザーがメンバーになっているグループに割り当てられているポリシーが優先されます。 ユーザーが複数のグループのメンバーである場合、特定のポリシーの種類に対して、[グループ割り当てのランク付け](#group-assignment-ranking) が最も高いポリシーが優先されます。

この例では、ユーザーの有効なポリシーは、Exec Teams および HD ポリシーです。このポリシーは、ユーザーがメンバーであり、同じポリシー タイプのポリシーが割り当てられている他のグループと比べて、割り当てのランクが最も高くなっています。  

![グループから継承されたポリシーの優先順位を示す図](media/assign-policies-example-group.png)

ユーザーが直接ポリシーを割り当てられていない場合や、ポリシーが割り当てられているグループのメンバーではない場合、ユーザーはそのポリシーの種類に対してグローバルな (組織全体の既定の) ポリシーを取得します。 次に例を示します。

![グローバル ポリシーの優先順位を示す図](media/assign-policies-example-global.png)

詳細については、「[優先規則](#precedence-rules)」を参照してください。

## <a name="ways-to-assign-policies"></a>ポリシーを割り当てる方法

これは、ユーザーにポリシーを割り当てる方法と、それぞれに推奨されるシナリオの概要です。 リンクをクリックして詳細を確認してください。

個々のユーザーまたはグループにポリシーを割り当てる前に、[グローバルな （組織全体の既定の） ポリシーを設定して](#set-the-global-policies)、それらが組織内の最大数のユーザーに適用されるようにします。  グローバル ポリシーが設定されると、特殊なポリシーを必要とするユーザーにポリシーを割り当てるだけで済みます。

|操作  |条件...  | 使用する技術...
|---------|---------|----|
|[ポリシーを個々のユーザーに割り当てる](#assign-a-policy-to-individual-users)    | Teams を初めて使用する場合、1 つまたはいくつかのポリシーを少数のユーザーに割り当てるだけで済みます。 |Microsoft Teams 管理センターまたは Skype for Business Online PowerShell モジュールの PowerShell コマンドレット
|[ポリシーをグループに割り当てる](#assign-a-policy-to-a-group) |ユーザーのグループ メンバーシップに基づいてポリシーを割り当てる必要があります。 たとえば、セキュリティ グループまたは配布リストのすべてのユーザーにポリシーを割り当てることができます。| Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット|
|[ポリシーをユーザーのバッチに割り当てる](#assign-a-policy-to-a-batch-of-users)   | 多数のユーザー セットにポリシーを割り当てる必要があります。 たとえば、組織内の数百または数千のユーザーに一度にポリシーを割り当てることができます。  |Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット|
| [ポリシー パッケージをユーザーに割り当てる](#assign-a-policy-package-to-users)  | 同じまたは類似の役割を持つ組織内の特定のユーザー セットに、複数のポリシーを割り当てる必要があります。 たとえば、教育機関 (教師) ポリシー パッケージを学校の教師に割り当てて、チャット、通話、および会議へのフル アクセスを許可し、教育機関 (中学生) ポリシー パッケージを中学生に割り当てて、私的な通話などの特定の機能を制限します。  |Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット|
| [ポリシー パッケージをグループに割り当てる](#assign-a-policy-package-to-a-group) (プライベート プレビュー)   |同じまたは類似の役割を持つ組織内のユーザーのグループに、複数のポリシーを割り当てる必要があります。 たとえば、セキュリティ グループまたは配布リストのすべてのユーザーにポリシー パッケージを割り当てることができます。 |Microsoft Teams 管理センター (近日公開予定) または Teams PowerShell モジュールの PowerShell コマンドレット|
| [ポリシー パッケージをユーザーのバッチに割り当てる](#assign-a-policy-package-to-a-batch-of-users)|同じまたは類似の役割を持つ組織内のユーザーのバッチに、複数のポリシーを割り当てる必要があります。 たとえば、バッチ割り当てを使用して教育機関 (教師) ポリシー パッケージを学校のすべての教師に割り当てて、チャット、通話、および会議へのフル アクセスを許可し、教育機関 (中学生) ポリシー パッケージを中学生のバッチに割り当てて、私的な通話などの特定の機能を制限します。|Teams PowerShell モジュールの PowerShell コマンドレット|


## <a name="set-the-global-policies"></a>グローバル ポリシーを設定する

次の手順に従って、ポリシーの種類ごとにグローバルな (組織全体の既定の) ポリシーを設定します。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

1. Microsoft Teams 管理センターの左側のナビゲーションで、更新するポリシー タイプのポリシー ページに移動します。 たとえば、**Teams** > **Teams ポリシー**、**会議** > **会議ポリシー**、**メッセージ ポリシー**、または **音声** > **通話ポリシー** です。
2. 現在の設定を表示するには、**グローバルな (組織全体の既定の)** ポリシーを選択します。
3. 必要に応じてポリシーを更新し、**[適用]** を選択します。

### <a name="using-powershell"></a>PowerShell の使用

PowerShell を使用してグローバル ポリシーを設定するには、グローバル識別子を使用します。  まず、現在のグローバル ポリシーを確認して、変更する設定を決定します。

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

次に、必要に応じてグローバル ポリシーを更新します。  変更する設定の値を指定するだけです。 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a>ポリシーを個々のユーザーに割り当てる

個々のユーザーまたは一度に少数のユーザーにポリシーを割り当てるには、次の手順に従います。

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

ポリシーをグループに割り当てるには:

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。
2. ユーザー名の左側をクリックしてユーザーを選択し、[**編集を設定する**] をクリックします。
3. 割り当てるポリシーを選択し、**[適用]** をクリックします。

または、次の操作も実行できます:

1. Microsoft Teams 管理センターの左側のナビゲーションで、ポリシー ページに移動します。
2. ポリシー名の左側をクリックして割り当てるポリシーを選びます。
3. **[ユーザーを管理する]** を選択します。
4. [**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。 追加するユーザーごとに、この手順を繰り返します。
5. ユーザーの追加が完了したら、**[適用]** を選択します。

### <a name="using-powershell"></a>PowerShell の使用

各ポリシー タイプには、それを管理するための独自のコマンドレットのセットがあります。 特定のポリシー タイプに ```Grant-``` コマンドレットを使用して、ポリシーを割り当てます。 たとえば、```Grant-CsTeamsMeetingPolicy``` コマンドレットを使用して、Teams 会議ポリシーをユーザーに割り当てます。 これらのコマンドレットは、Skype for Business Online PowerShell モジュールに含まれており、[Skype for Business コマンドレットのリファレンス](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps) に記載されています。

 (まだインストールされていない場合は) [Skype for Business Online PowerShell モジュール](https://www.microsoft.com/download/details.aspx?id=39366) をダウンロードしてインストールし、次のコマンドを実行して Skype for Business Online に接続しセッションを開始します。

> [!NOTE]
> Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。
>
> 最新の [Teams PowerShell パブリック リリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)をご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。

```powershell
Import-Module -Name MicrosoftTeams
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

この例では、Student Meeting Policy という名前の Teams 会議ポリシーを、Reda というユーザーに割り当てています。

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

詳細については、「[PowerShell によるポリシーの管理](teams-powershell-managing-teams.md#manage-policies-via-powershell)」を参照してください。

## <a name="assign-a-policy-to-a-group"></a>ポリシーをグループに割り当てる

グループにポリシーを割り当てると、セキュリティ グループや配布リストなど、ユーザーのグループにポリシーを割り当てることができます。 ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。 グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。

ポリシーをグループに割り当てるのは、最大 50,000 ユーザーのグループに推奨されますが、より大きなグループでも機能します。

ポリシーを割り当てると、そのポリシーはすぐにグループに割り当てられます。 ただし、グループのメンバーへのポリシーの割り当ての反映は、バックグラウンド操作として実行され、グループのサイズによっては時間がかかる場合があることに注意してください。 ポリシーがグループから割り当てられていない場合、またはグループからメンバーが追加または削除された場合も同じです。

グループ ポリシーの割り当ては、グループの直接のメンバーであるユーザーにのみ伝達されます。 割り当ては、入れ子になったグループのメンバーには伝達されません。

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>グループへのポリシーの割り当てについて知っておくべきこと

使用を開始する前に、優先規則とグループ割り当てのランク付けを理解することが重要です。

#### <a name="precedence-rules"></a>優先規則

特定のポリシーの種類について、ユーザーの有効なポリシーは、次に従って決定されます。

- ユーザーに直接割り当てられているポリシーは、グループに割り当てられている同じ種類の別のポリシーよりも優先されます。 言い換えると、ユーザーに特定の種類のポリシーが直接割り当てられている場合、そのユーザーはグループから同じ種類のポリシーを継承しません。 つまり、ユーザーが特定の種類のポリシーを直接割り当てられている場合は、ユーザーがグループから同じ種類のポリシーを継承する前に、そのポリシーをユーザーから削除する必要があります。
- ユーザーに直接割り当てられたポリシーがなく、2 つ以上のグループのメンバーであり、各グループに同じ種類のポリシーが割り当てられている場合、ユーザーは最も高いランク付けを持つグループ割り当てのポリシーを継承します。
- ユーザーがポリシーが割り当てられているグループのメンバーではない場合、ユーザーにそのポリシーの種類に対してグローバルな (組織全体の既定の) ポリシーが割り当てられます。

ポリシーを割り当てられているグループにユーザーを追加または削除したとき、ポリシーがグループに割り当てられていないとき、またはユーザーに直接割り当てられているポリシーが削除されたときに、ユーザーの有効なポリシーはこれらの規則に従って更新されます。

#### <a name="group-assignment-ranking"></a>グループ割り当てのランク付け
 
ポリシーをグループに割り当てるときは、グループ割り当てのランクを指定します。 これは、ユーザーが 2 つ以上のグループのメンバーであり、各グループに同じ種類のポリシーが割り当てられている場合に、ユーザーが有効なポリシーとして継承する必要があるポリシーを決定するために使用されます。

グループ割り当てのランク付けは、同じ種類の別のグループ割り当てに関連しています。 たとえば、通話ポリシーを 2 つのグループに割り当てる場合は、1 つの割り当てのランクを 1 に設定し、もう 1 つの割り当てを 2 に設定します。1 が最高のランクです。 グループ割り当てのランク付けは、継承に関して、どのグループ メンバーシップが他のグループ メンバーシップよりも重要または関連性が高いかを示します。
 
たとえば、店舗の従業員と管理者の 2 つのグループがあるとします。 両方のグループには、それぞれ Teams 通話ポリシー、店舗従業員通話ポリシー、および店舗管理者通話ポリシーが割り当てられています。 両方のグループに属する店舗管理者の場合、管理者としての役割は従業員としての役割よりも重要であるため、店舗管理者グループに割り当てられている通話ポリシーにより高いランク付けを行う必要があります。

|グループ |Teams 通話ポリシー名  |ランク|
|---------|---------|---|
|店舗管理者   |店舗管理者通話ポリシー         |1|
|店舗従業員    |店舗従業員通話ポリシー      |2|

ランクを指定しないと、ポリシーの割り当てに最も低いランクが与えられます。 

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

> [!NOTE]
> 現在、Microsoft Teams 管理センターを使用したグループへのポリシー割り当ては、Teams 通話ポリシー、Teams コール パーク ポリシー、Teams ポリシー、Teams ライブ イベント ポリシー、Teams 会議ポリシー、Teams メッセージ ポリシーでのみ使用できます。 他のポリシーの種類については、PowerShell を使用してください。

1. Microsoft Teams 管理センターの左側のナビゲーションで、ポリシーの種類のページに移動します。 たとえば、**会議** > **会議ポリシー** に移動します。
2. **グループ ポリシーの割り当て** タブを選択します。
3. **[グループの追加]** を選択し、**[ポリシーをグループに割り当てる]** ウィンドウで、次の操作を行います:
    1. ポリシーを割り当てるグループを検索し、追加します。
    2. グループ割り当てのランク付けを設定します。
    3. 割り当てるポリシーを選択します。 
    4. **[適用]** を選択します。

グループ ポリシーの割り当てを削除するには、ポリシー ページの **[グループ ポリシーの割り当て]** タブで、グループの割り当てを選び、**[削除]** を選択します。

グループ割り当てのランク付けを変更するには、最初にグループ ポリシーの割り当てを削除する必要があります。 次に、上記の手順に従ってポリシーをグループに割り当てます。

### <a name="using-powershell"></a>PowerShell の使用

> [!NOTE]
> 現在、PowerShell を使用したグループへのポリシーの割り当ては、すべての Teams ポリシー タイプで使用できるわけではありません。 サポートされているポリシー タイプの一覧については、[New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) を参照してください。

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft Teams PowerShell モジュールをインストールして接続する

段階的なガイダンスについては、「[Teams PowerShell をインストールする](teams-powershell-install.md)」を参照してください。

#### <a name="assign-a-policy-to-a-group-of-users"></a>ポリシーをユーザーのグループに割り当てる

ポリシーをグループに割り当てるには、[New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) コマンドレットを使用します。 オブジェクト ID、SIP アドレス、またはメール アドレスを使用して、グループを指定できます。

この例では、Retail Managers Meeting Policy という名前の Teams 会議ポリシーを、割り当てのランクが 1 のグループに割り当てます。

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a>グループのポリシーの割り当てを取得する

[Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) コマンドレットを使用して、グループに割り当てられているすべてのポリシーを取得します。 ポリシーの割り当てに SIP アドレスまたはメール アドレスが使用された場合でも、グループは常にグループ ID 別に一覧表示されることに注意してください。

この例では、特定のグループに割り当てられているすべてのポリシーを取得します。

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

この例では、Teams 会議ポリシーが割り当てられているすべてのグループを返します。

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a>グループからポリシーを削除する

[Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) コマンドレットを使用して、グループからポリシーを削除します。 グループからポリシーを削除すると、そのグループに割り当てられた同じ種類でランクが低い他のポリシーの優先順位が更新されます。 たとえば、ランクが 2 であるポリシーを削除すると、その新しいランク付けを反映して、ランク 3 と 4 のポリシーが更新されます。 次の 2 つの表にこの例を示します。

これは、Teams 会議ポリシーのポリシー割り当てと優先順位のリストです。

|グループ名  |ポリシー名  |ランク|
|---------|---------|---------|
|営業    |営業ポリシー       | 1        |
|西部地域     |西部地域ポリシー         |2         |
|部門    |部門ポリシー         |3         |
|部署   |部署ポリシー        |4         |

西部地域グループから西部地域ポリシーを削除すると、ポリシーの割り当てと優先順位は次のように更新されます。

|グループ名  |ポリシー名  |ランク|
|---------|---------|---------|
|営業    |営業ポリシー       | 1        |
|部門    |部門ポリシー         |2         |
|部署   |部署ポリシー        |3        |

この例では、グループから Teams 会議ポリシーを削除します。

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a>グループのポリシーの割り当てを変更する

> [!NOTE]
> [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) コマンドレットは間もなく使用可能になります。 それまでの間、グループ ポリシーの割り当てを変更するには、現在のポリシーの割り当てをグループから削除して、新しいポリシーの割り当てを追加します。

ポリシーをグループに割り当てたら、[Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) コマンドレットを使用して、グループのポリシーの割り当てを次のように変更できます:

- ランク付けを変更する
- 特定のポリシーの種類のポリシーを変更する
- 特定のポリシーの種類のポリシーとランク付けを変更する

この例では、グループの Teams コール パーク ポリシーを、SupportCallPark という名前のポリシーに変更し、割り当てのランクを 3 に変更します。

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a>ユーザーの有効なポリシーを変更する

これは、ポリシーを直接割り当てるユーザーの有効なポリシーを変更する方法の例です。

最初に、[Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) コマンドレットを ```PolicySource``` パラメーターと共に使用して、ユーザーに関連付けられた Teams 会議ブロードキャスト ポリシーの詳細を取得します。 

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

出力には、Employee Events という名前の Teams 会議ブロードキャスト ポリシーがユーザーに直接割り当てられていることが示されています。これは、ユーザーが属するグループに割り当てられている Vendor Live Events という名前のポリシーよりも優先されます。

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

次に、ユーザーから Employee Events policy を削除します。 つまり、ユーザーに Teams 会議ブロードキャスト ポリシーが直接割り当てられなくなったことを意味し、ユーザーが属するグループに割り当てられている Vendor Live Events policy を継承します。 

この操作を行うには、Skype for Business PowerShell モジュールの次のコマンドレットを使用します。

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

Teams PowerShell モジュールで次のコマンドレットを使用すると、バッチ ポリシーの割り当てを通じて大規模にこれを行うことができます。ここで、$users は指定したユーザーのリストです。

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>ポリシーをユーザーのバッチに割り当てる

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

ポリシーをユーザーに一括で割り当てるには:

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** を選択します。
2. ポリシーを割り当てるユーザーを検索するか、ビューをフィルター処理して必要なユーザーを表示します。
3. [**&#x2713;** (チェックマーク)] の列からユーザーを選択します。 すべてのユーザーを選択するには、表の上部にある [&#x2713; (チェックマーク)] をクリックします。
4. [**設定の編集**] をクリックし、必要な変更を行い、[**適用**] をクリックします。

ポリシーの割り当ての状態を表示するには、**[適用]** をクリックしてポリシーの割り当てを送信した後に **[ユーザー]** ページの上部に表示されるバナーで、**[アクティビティ ログ]** をクリックします。 または、Microsoft Teams 管理センターの左側のナビゲーションで、**[ダッシュボード]** に移動し、**[アクティビティ ログ]** で **[詳細の表示]** をクリックします。 アクティビティ ログには、過去 30 日間の Microsoft Teams 管理センターを通じて、20 人を超えるユーザーのバッチへのポリシー割り当てが表示されます。 詳細については、「[アクティビティ ログでポリシーの割り当てを表示する](activity-log.md)」を参照してください。

### <a name="using-powershell"></a>PowerShell の使用

> [!NOTE]
> 現在、PowerShell を使用したバッチ ポリシーの割り当ては、すべての Teams ポリシー タイプで使用できるわけではありません。 サポートされているポリシー タイプの一覧については、[New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) を参照してください。
 
バッチ ポリシーの割り当てを使用すると、スクリプトを使用せずに、多数のユーザー セットに同時にポリシーを割り当てることができます。 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、割り当てる一群のユーザーおよびポリシーを送信します。 割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。 その後、[Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) コマンドレットを使用して、バッチの割り当ての進捗状況と状態を追跡できます。

ユーザーの指定には、オブジェクト ID またはセッション開始プロトコル (SIP) アドレスを使用します。 多くの場合、ユーザーの SIP アドレスは、ユーザー プリンシパル名 (UPN) またはメール アドレスと同じ値ですが、これは必須ではありません。 ユーザーが UPN またはメールを使用して指定されていても、その値が SIP アドレスとは異なる場合、そのユーザーのポリシー割り当ては失敗します。 バッチのユーザーが重複している場合、処理前に重複がバッチから削除され、バッチに残っている一意のユーザーにのみステータスが提供されます。 

バッチには最大 5,000 のユーザーを含めることができます。 最良の結果を得るには、一度に複数のバッチを送信しないようにします。 さらにバッチを送信する前に、バッチが処理を完了できるようにします。

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft Teams PowerShell モジュールをインストールして接続する

以下を実行して、[Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams) をインストールします。 バージョン 1.0.5 以降をインストールしていることを確認します。

```powershell
Install-Module -Name MicrosoftTeams
```

以下を実行して Teams に接続しセッションを開始します。

```powershell
Connect-MicrosoftTeams
```

メッセージが表示されたら、管理者の資格情報を使用してサイン インします。

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Azure AD PowerShell for Graph モジュールをインストールして接続する (オプション)

また、[Azure AD PowerShell for Graph モジュールをダウンロードしてインストールし](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) （まだインストールしていない場合）、Azure AD に接続して、組織内のユーザーのリストを取得することもできます。

以下を実行して、Azure AD に接続します。

```powershell
Connect-AzureAD
```

メッセージが表示されたら、Teams に接続するために使用したのと同じ管理者資格情報を使用してサイン インします。

#### <a name="assign-a-policy-to-a-batch-of-users"></a>ポリシーをユーザーのバッチに割り当てる

この例では、[New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、HR App Setup Policy という名前のアプリ セットアップ ポリシーを Users_ids.text ファイルに記載されているユーザーのバッチに割り当てます。

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

この例では、Azure AD に接続してユーザーのコレクションを取得し、SIP アドレスを使用して指定されたユーザーのバッチに New Hire Messaging Policy という名前のメッセージ ポリシーを割り当てます。

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a>バッチ割り当ての状態を取得する

以下を実行して、バッチ割り当ての状態を取得します。ここで、OperationId は、特定のバッチの ```New-CsBatchPolicyAssignmentOperation``` コマンドレットによって返される操作 ID です。

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

エラーが発生したことが出力に示されている場合は、次のコマンドを実行して、```UserState``` プロパティにあるエラーに関する詳細情報を取得します。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

詳細については、[Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) を参照してください。

## <a name="assign-a-policy-package-to-users"></a>ポリシー パッケージをユーザーに割り当てる

Teams のポリシー パッケージは、組織内で同じまたは類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。 各ポリシー パッケージは、ユーザーの役割に合わせて設計されており、その役割の一般的なアクティビティをサポートする定義済みのポリシーおよびポリシー設定が含まれています。 ポリシー パッケージの例としては、教育機関 (教師) パッケージと医療機関 (医療従事者) パッケージがあります。 詳細については、「[Teams でポリシー パッケージを管理する](manage-policy-packages.md)」を参照してください。

### <a name="assign-a-policy-package-to-one-user"></a>ポリシー パッケージを 1 人のユーザーに割り当てる

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** に移動してユーザーをクリックします。
2. ユーザーのページで、**[ポリシー]** をクリックし、**[ポリシー パッケージ]** の横の **[編集]** をクリックします。
3. **[ポリシー パッケージの割り当て]** ウィンドウで、割り当てるパッケージを選択し、**[保存]** をクリックします。

### <a name="assign-a-policy-package-to-multiple-users"></a>ポリシー パッケージを複数のユーザーに割り当てる

1. Microsoft Teams 管理センターの左側のナビゲーションで **[ポリシー パッケージ]** に移動し、パッケージ名の左側をクリックして、割り当てるポリシー パッケージを選択します。
2. **[ユーザーの管理]** をクリックします。
3. [**ユーザーを管理する**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] をクリックします。 追加するユーザーごとに、この手順を繰り返します。
4. ユーザーの追加が完了したら、[**保存**] をクリックします。

## <a name="assign-a-policy-package-to-a-group"></a>ポリシー パッケージをグループに割り当てる

**この機能はプライベート プレビューです**

グループにポリシー パッケージを割り当てると、セキュリティ グループや配布リストなど、ユーザーのグループに複数のポリシーを割り当てることができます。 ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。 グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。

ポリシー パッケージをグループに割り当てるのは、最大 50,000 ユーザーのグループに推奨されますが、より大きなグループでも機能します。 

ポリシー パッケージを割り当てると、そのポリシーはすぐにグループに割り当てられます。 ただし、グループのメンバーへのポリシーの割り当ての反映は、バックグラウンド操作として実行され、グループのサイズによっては時間がかかる場合があることに注意してください。 ポリシーがグループから割り当てられていない場合、またはグループからメンバーが追加または削除された場合も同じです。

> [!IMPORTANT]
> 使用を開始する前に、[優先規則](#precedence-rules)と[グループ割り当てのランク付け](#group-assignment-ranking)を理解することが重要です。 この記事の前半の「[グループへのポリシーの割り当てについて知っておくべきこと](#what-you-need-to-know-about-policy-assignment-to-groups)」の概念を必ず読み、理解してください。

### <a name="using-the-microsoft-teams-admin-center-coming-soon"></a>Microsoft Teams 管理センターの使用 (近日公開予定)

Microsoft Teams 管理センターでのグループへのポリシー パッケージの割り当てが近日公開される予定です。 最新の更新プログラムについては、こちらを参照してください。

### <a name="using-powershell"></a>PowerShell の使用

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft Teams PowerShell モジュールをインストールして接続する

段階的なガイダンスについては、「[Teams PowerShell をインストールする](teams-powershell-install.md)」を参照してください。

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>ポリシー パッケージをユーザーのグループに割り当てる

ポリシー パッケージをグループに割り当てるには、[Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) コマンドレットを使用します。 オブジェクト ID、SIP アドレス、またはメール アドレスを使用して、グループを指定できます。 ポリシー パッケージを割り当てる場合は、ポリシー パッケージの各ポリシーの種類に対して[グループ割り当てのランク付け](#group-assignment-ranking)を指定します。 

この例では、Education_Teacher ポリシー パッケージをグループに割り当て、TeamsAppSetupPolicy と TeamsMeetingBroadcastPolicy には 1 のランク付け、TeamsMeetingPolicy には 2 のランク付けを行います。

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>ポリシー パッケージをユーザーのバッチに割り当てる

バッチ ポリシー パッケージの割り当てを使用すると、スクリプトを使用せずに、多数のユーザー セットに同時にポリシー パッケージを割り当てることができます。 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、割り当てる一群のユーザーおよびポリシー パッケージを送信します。 割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。 その後、[Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) コマンドレットを使用して、バッチの割り当ての進捗状況と状態を追跡できます。

ユーザーの指定には、オブジェクト ID またはセッション開始プロトコル (SIP) アドレスを使用します。 多くの場合、ユーザーの SIP アドレスは、ユーザー プリンシパル名 (UPN) またはメール アドレスと同じ値ですが、これは必須ではありません。 ユーザーが UPN またはメールを使用して指定されていても、その値が SIP アドレスとは異なる場合、そのユーザーのポリシー割り当ては失敗します。 バッチのユーザーが重複している場合、処理前に重複がバッチから削除され、バッチに残っている一意のユーザーにのみステータスが提供されます。 

バッチには最大 5,000 のユーザーを含めることができます。 最良の結果を得るには、一度に複数のバッチを送信しないようにします。 さらにバッチを送信する前に、バッチが処理を完了できるようにします。

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft Teams PowerShell モジュールをインストールして接続する

以下を実行して、(まだインストールされていない場合は) [Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams) をインストールします。 バージョン 1.0.5 以降をインストールしていることを確認します。

```powershell
Install-Module -Name MicrosoftTeams
```

以下を実行して Teams に接続しセッションを開始します。

```powershell
Connect-MicrosoftTeams
```

メッセージが表示されたら、管理者の資格情報を使用してサイン インします。

### <a name="assign-a-policy-package-to-a-batch-of-users"></a>ポリシー パッケージをユーザーのバッチに割り当てる

この例では、[New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、ユーザーのバッチに Education_PrimaryStudent ポリシー パッケージを割り当てます。

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="get-the-status-of-a-batch-assignment"></a>バッチ割り当ての状態を取得する

以下を実行して、バッチ割り当ての状態を取得します。ここで、OperationId は、特定のバッチの ```New-CsBatchPolicyAssignmentOperation``` コマンドレットによって返される操作 ID です。

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

エラーが発生したことが出力に示されている場合は、次のコマンドを実行して、```UserState``` プロパティにあるエラーに関する詳細情報を取得します。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

詳細については、[Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) を参照してください。 

## <a name="related-topics"></a>関連トピック

[Teams PowerShell の概要](teams-powershell-overview.md)
