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
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams でユーザーにポリシーを割り当てる方法について説明します。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 858a28843fc883712ab12b868eca505069e5ab4f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727886"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a>Microsoft Teams でユーザーにポリシーを割り当てる

管理者は、ポリシーを使用して、組織のユーザーが利用できる Teams 機能を制御できます。 たとえば、ほんの一例を挙げると、通話ポリシー、会議ポリシー、メッセージ ポリシーなどがあります。

組織には、固有のニーズを持つユーザーの種類が異なります。 作成して割り当てるカスタム ポリシーを使用すると、それらのニーズに基づいてポリシー設定をさまざまなユーザー セットに合わせて調整できます。

組織のポリシーを簡単に管理するには、Teamsにポリシーを割り当てる方法がいくつか用意されています。 ポリシーをユーザーに直接割り当てる (個別に割り当てるか、バッチ割り当てによって大規模に割り当てるか、ユーザーがメンバーであるグループに割り当てる)。 ポリシー パッケージを使用して、ポリシーの既定のコレクションを、同様の役割を持つ組織内のユーザーに割り当てることもできます。 選択するオプションは、管理しているポリシーの数と、ポリシーを割り当てるユーザーの数によって異なります。 グローバル (組織全体の既定) ポリシーは、組織内の最大ユーザー数に適用されます。 ポリシーは、特殊なポリシーを必要とするユーザーにのみ割り当てる必要があります。

この記事では、ユーザーにポリシーを割り当てるさまざまな方法と、何をいつ使用するかについての推奨シナリオについて説明します。

## <a name="which-policy-takes-precedence"></a>どのポリシーが優先されますか?

ユーザーには、ポリシーの種類ごとに 1 つの有効なポリシーがあります。 ユーザーにポリシーが直接割り当てられている可能性があります。また、同じ種類のポリシーが割り当てられている 1 つ以上のグループのメンバーである可能性があります。 このようなシナリオでは、どのポリシーが優先されますか? ユーザーの有効なポリシーは、次の優先規則に従って決定されます。

ユーザーに直接ポリシーが割り当てられている場合 （個別に、またはバッチ割り当てによって）、そのポリシーが優先されます。 次の視覚的な例では、ユーザーの有効なポリシーは、ユーザーに直接割り当てられる、Square 会議ポリシーです。

![直接割り当てられたポリシーが優先される方法を示す図。](media/assign-policies-example-directly-assigned.png)

ユーザーに特定の種類のポリシーが直接割り当てられていない場合は、そのユーザーがメンバーになっているグループに割り当てられているポリシーが優先されます。 ユーザーが複数のグループのメンバーである場合、特定のポリシーの種類に対して、[グループ割り当てのランク付け](#group-assignment-ranking) が最も高いポリシーが優先されます。

この視覚的な例では、ユーザーの有効なポリシーは Exec Teams ポリシーと HD ポリシーです。これは、ユーザーがメンバーであり、同じポリシーの種類のポリシーも割り当てられている他のグループに対して最も高い割り当て順位が付けられます。  

![グループから継承されたポリシーが優先される方法を示す図。](media/assign-policies-example-group.png)

ユーザーが直接ポリシーを割り当てられていない場合や、ポリシーが割り当てられているグループのメンバーではない場合、ユーザーはそのポリシーの種類に対してグローバルな (組織全体の既定の) ポリシーを取得します。 視覚的な例を次に示します。

![グローバル ポリシーが優先される方法を示す図。](media/assign-policies-example-global.png)

詳細については、「[優先規則](#precedence-rules)」を参照してください。

## <a name="ways-to-assign-policies"></a>ポリシーを割り当てる方法

これは、ユーザーにポリシーを割り当てる方法と、それぞれに推奨されるシナリオの概要です。 詳細については、リンクを選択してください。

個々のユーザーまたはグループにポリシーを割り当てる前に、[グローバルな （組織全体の既定の） ポリシーを設定して](#set-the-global-policies)、それらが組織内の最大数のユーザーに適用されるようにします。  グローバル ポリシーが設定された後は、特殊なポリシーを必要とするユーザーにポリシーを割り当てる必要があります。

|操作  |条件...  | 使用する技術...
|---------|---------|----|
|[ポリシーを個々のユーザーに割り当てる](#assign-a-policy-to-individual-users)    | Teams を初めて使用する場合、1 つまたはいくつかのポリシーを少数のユーザーに割り当てるだけで済みます。 |Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット
|[ポリシーをグループに割り当てる](#assign-a-policy-to-a-group) |ユーザーのグループ メンバーシップに基づいてポリシーを割り当てる。 たとえば、セキュリティ グループまたは配布リスト内のすべてのユーザーにポリシーを割り当てるとします。| Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット|
|[ポリシーをユーザーのバッチに割り当てる](#assign-a-policy-to-a-batch-of-users)   | 多数のユーザーにポリシーを割り当てる。 たとえば、組織内の数百または数千人のユーザーにポリシーを一度に割り当てるとします。 |Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット|
| [ポリシー パッケージをユーザーに割り当てる](#assign-a-policy-package-to-users)  |同じロールまたは同様のロールを持つ組織内の特定のユーザー セットに複数のポリシーを割り当てます。 たとえば、学校の教師に教育 (教師) ポリシー パッケージを割り当て、チャット、通話、会議へのフル アクセス権を与えます。 Education (中学生) ポリシー パッケージをセカンダリ 学生に割り当て、プライベート通話などの特定の機能を制限します。  |Microsoft Teams 管理センターまたは Teams PowerShell モジュールの PowerShell コマンドレット|
| [ポリシー パッケージをグループに割り当てる](#assign-a-policy-package-to-a-group) (プライベート プレビュー)   |同じロールまたは同様のロールを持つ組織内のユーザーグループに複数のポリシーを割り当てます。 たとえば、セキュリティ グループまたは配布リスト内のすべてのユーザーにポリシー パッケージを割り当てるとします。 |Microsoft Teams 管理センター (近日公開予定) または Teams PowerShell モジュールの PowerShell コマンドレット|
| [ポリシー パッケージをユーザーのバッチに割り当てる](#assign-a-policy-package-to-a-batch-of-users)|同じロールまたは同様のロールを持つ組織内のユーザーのバッチに複数のポリシーを割り当てます。 たとえば、バッチ割り当てを使用して、学校内のすべての教師に教育 (教師) ポリシー パッケージを割り当て、チャット、通話、会議へのフル アクセス権を与えます。 Education (中学生) ポリシー パッケージをセカンダリ 学生のバッチに割り当て、プライベート通話などの特定の機能を制限します。|Teams PowerShell モジュールの PowerShell コマンドレット|

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

### <a name="use-the-microsoft-teams-admin-center"></a>管理センター Microsoft Teams使用する

ポリシーをグループに割り当てるには:

1. 管理センターの左側のMicrosoft Teams、[ユーザー] に移動し、ユーザーを選択します。
2. ユーザー名の左側をクリックしてユーザーを選択し、[設定の編集] **を選択します**。
3. 割り当てるポリシーを選択し、[適用] を **選択します**。

または、次の操作も実行できます:

1. Microsoft Teams 管理センターの左側のナビゲーションで、ポリシー ページに移動します。
2. ポリシー名の左側をクリックして割り当てるポリシーを選びます。
3. **[ユーザーを管理する]** を選択します。
4. [**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。 追加するユーザーごとに、この手順を繰り返します。
5. ユーザーの追加が完了したら、**[適用]** を選択します。

### <a name="use-powershell"></a>PowerShell を使用する

各ポリシー タイプには、それを管理するための独自のコマンドレットのセットがあります。 特定のポリシー タイプに ```Grant-``` コマンドレットを使用して、ポリシーを割り当てます。 たとえば、```Grant-CsTeamsMeetingPolicy``` コマンドレットを使用して、Teams 会議ポリシーをユーザーに割り当てます。 これらのコマンドレットは PowerShell モジュールの Teamsに含まれており、このコマンドレット リファレンス[にSkype for Business記載されています](/powershell/skype/intro?view=skype-ps)。

PowerShell の[](https://www.powershellgallery.com/packages/MicrosoftTeams/)パブリック Teamsをダウンロードしてインストールし (まだインストールしていない場合)、次のコマンドを実行して接続します。

> [!NOTE]
> Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。
>
> 最新の [Teams PowerShell パブリック リリース](https://www.powershellgallery.com/packages/MicrosoftTeams/)をご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。

```powershell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
```

この例では、Student Meeting Policy という名前の Teams 会議ポリシーを、Reda というユーザーに割り当てています。

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

詳細については、「[PowerShell によるポリシーの管理](teams-powershell-managing-teams.md#manage-policies-via-powershell)」を参照してください。

## <a name="assign-a-policy-to-a-group"></a>ポリシーをグループに割り当てる

グループにポリシーを割り当てると、セキュリティ グループや配布リストなど、ユーザーのグループにポリシーを割り当てることができます。 ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。 グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。

ポリシーをグループに割り当てるのは、最大 50,000 ユーザーのグループに推奨されますが、より大きなグループでも機能します。

ポリシーを割り当てると、そのポリシーはすぐにグループに割り当てられます。 ただし、グループのメンバーへのポリシー割り当ての反映はバックグラウンド操作として実行され、グループのサイズによっては時間がかかる場合があります。 ポリシーがグループから割り当てられていない場合、またはグループからメンバーが追加または削除された場合も同じです。

グループ ポリシーの割り当ては、グループの直接メンバーであるユーザーにのみ伝達されます。 割り当ては、入れ子になったグループのメンバーには伝達されません。

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>グループへのポリシーの割り当てについて知っておくべきこと

使用を開始する前に、優先規則とグループ割り当てのランク付けを理解することが重要です。

#### <a name="precedence-rules"></a>優先規則

特定のポリシーの種類について、ユーザーの有効なポリシーは、次に従って決定されます。

- ユーザーに直接割り当てられているポリシーは、グループに割り当てられている同じ種類の別のポリシーよりも優先されます。 言い換えると、ユーザーに特定の種類のポリシーが直接割り当てられている場合、そのユーザーはグループから同じ種類のポリシーを継承しません。 つまり、ユーザーが特定の種類のポリシーを直接割り当てられている場合は、ユーザーがグループから同じ種類のポリシーを継承する前に、そのポリシーをユーザーから削除する必要があります。

- ユーザーに直接割り当てられたポリシーがなく、2 つ以上のグループのメンバーであり、各グループに同じ種類のポリシーが割り当てられている場合、ユーザーは最も高いランク付けを持つグループ割り当てのポリシーを継承します。

- ユーザーがポリシーが割り当てられているグループのメンバーではない場合、ユーザーにそのポリシーの種類に対してグローバルな (組織全体の既定の) ポリシーが割り当てられます。

ユーザーの有効なポリシーは、次の規則に従って更新されます。

- ポリシーが割り当てられているグループにユーザーが追加または削除された場合。
- ポリシーはグループから割り当て解除されます。
- ユーザーに直接割り当てられているポリシーは削除されます。

#### <a name="group-assignment-ranking"></a>グループ割り当てのランク付け

ポリシーをグループに割り当てるときは、グループ割り当てのランクを指定します。 これは、ユーザーが 2 つ以上のグループのメンバーであり、各グループに同じ種類のポリシーが割り当てられている場合に、ユーザーが有効なポリシーとして継承する必要があるポリシーを決定するために使用されます。

グループ割り当てのランク付けは、同じ種類の別のグループ割り当てに関連しています。 たとえば、通話ポリシーを 2 つのグループに割り当てる場合は、1 つの割り当てのランクを 1 に設定し、もう 1 つの割り当てを 2 に設定します。1 が最高のランクです。 グループ割り当てランキングは、継承に関する他のグループ メンバーシップよりも重要または関連性の高いグループ メンバーシップを示します。

たとえば、店舗の従業員と管理者の 2 つのグループがあるとします。 両方のグループには、それぞれ Teams 通話ポリシー、店舗従業員通話ポリシー、および店舗管理者通話ポリシーが割り当てられています。 両方のグループに属する店舗管理者の場合、管理者としての役割は従業員としての役割よりも重要であるため、店舗管理者グループに割り当てられている通話ポリシーにより高いランク付けを行う必要があります。

|グループ |Teams 通話ポリシー名  |ランク|
|---------|---------|---|
|店舗管理者   |店舗管理者通話ポリシー         |1|
|店舗従業員    |店舗従業員通話ポリシー      |2|

ランクを指定しないと、ポリシーの割り当てに最も低いランクが与えられます。

### <a name="in-the-teams-admin-center"></a>管理センター Teamsで

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

### <a name="use-the-powershell-option"></a>PowerShell オプションを使用する

> [!NOTE]
> 現在、PowerShell を使用したグループへのポリシーの割り当ては、すべての Teams ポリシー タイプで使用できるわけではありません。 サポートされているポリシー タイプの一覧については、[New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) を参照してください。

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft Teams PowerShell モジュールをインストールして接続する

段階的なガイダンスについては、「[Teams PowerShell をインストールする](teams-powershell-install.md)」を参照してください。

#### <a name="assign-a-policy-to-a-group-of-users"></a>ポリシーをユーザーのグループに割り当てる

[New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment)コマンドレットを使用して、グループにポリシーを割り当てる。 オブジェクト ID、SIP アドレス、または電子メール アドレスを使用して、グループを指定できます。

この例では、Retail Managers Meeting Policy という名前の Teams 会議ポリシーを、割り当てのランクが 1 のグループに割り当てます。

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a>グループのポリシーの割り当てを取得する

[Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) コマンドレットを使用して、グループに割り当てられているすべてのポリシーを取得します。 SIP アドレスまたは電子メール アドレスがポリシーの割り当てに使用された場合でも、グループは常にグループ ID で一覧表示されます。

この例では、特定のグループに割り当てられているすべてのポリシーを取得します。

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

この例では、Teams 会議ポリシーが割り当てられているすべてのグループを返します。

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a>グループからポリシーを削除する

[Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) コマンドレットを使用して、グループからポリシーを削除します。 グループからポリシーを削除すると、そのグループに割り当てられている、ランクが低い同じ種類の他のポリシーの優先順位が更新されます。 たとえば、ランクが 2 であるポリシーを削除すると、その新しいランク付けを反映して、ランク 3 と 4 のポリシーが更新されます。 次の 2 つの表にこの例を示します。

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
> [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) コマンドレットは間もなく使用可能になります。 それまでの間、グループ ポリシーの割り当てを変更するには、現在のポリシーの割り当てをグループから削除して、新しいポリシーの割り当てを追加します。

ポリシーをグループに割り当てたら、[Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) コマンドレットを使用して、グループのポリシーの割り当てを次のように変更できます:

- ランク付けを変更する
- 特定のポリシーの種類のポリシーを変更する
- 特定のポリシーの種類のポリシーとランク付けを変更する

この例では、グループの Teams コール パーク ポリシーを、SupportCallPark という名前のポリシーに変更し、割り当てのランクを 3 に変更します。

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a>ユーザーの有効なポリシーを変更する

これは、ポリシーを直接割り当てるユーザーの有効なポリシーを変更する方法の例です。

最初に、[Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) コマンドレットを `PolicySource` パラメーターと共に使用して、ユーザーに関連付けられた Teams 会議ブロードキャスト ポリシーの詳細を取得します。

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

Teams PowerShell モジュールで次のコマンドレットを使用して、バッチ ポリシーの割り当てを大規模に実行します。$users は、指定したユーザーの一覧です。

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>ポリシーをユーザーのバッチに割り当てる

### <a name="use-the-admin-center"></a>管理センターを使用する

ポリシーをユーザーに一括で割り当てるには:

1. Microsoft Teams 管理センターの左側のナビゲーションで、**[ユーザー]** を選択します。

2. ポリシーを割り当てるユーザーを検索するか、ビューをフィルター処理して必要なユーザーを表示します。

3. [**&#x2713;** (チェックマーク)] の列からユーザーを選択します。 すべてのユーザーを選択するには、表の上部にある [&#x2713; (チェックマーク)] をクリックします。

4. [設定 **の編集]** を選択し、必要な変更を行い、[適用] を **選択します**。

ポリシー割り当ての状態を表示するには、[適用] を選択した後に [ユーザー] ページの上部に表示されるバナーで、[アクティビティ ログ] を **選択します**。 または、管理センターの左側のナビゲーションMicrosoft Teams **ダッシュボード** に移動し、[アクティビティ ログ] で[詳細の表示]**を選択します**。 アクティビティ ログには、過去 30 日間の Microsoft Teams 管理センターを通じて、20 人を超えるユーザーのバッチへのポリシー割り当てが表示されます。 詳細については、「[アクティビティ ログでポリシーの割り当てを表示する](activity-log.md)」を参照してください。

### <a name="use-powershell-method"></a>PowerShell メソッドを使用する

> [!NOTE]
> 現在、PowerShell を使用したバッチ ポリシーの割り当ては、すべての Teams ポリシー タイプで使用できるわけではありません。 サポートされているポリシー タイプの一覧については、[New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) を参照してください。

バッチ ポリシーの割り当てを使用すると、スクリプトを使用せずに、多数のユーザー セットに同時にポリシーを割り当てることができます。 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、割り当てる一群のユーザーおよびポリシーを送信します。 割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。 その後、[Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) コマンドレットを使用して、バッチの割り当ての進捗状況と状態を追跡できます。

ユーザーをオブジェクト ID またはセッション開始プロトコル (SIP) アドレスで指定します。 多くの場合、ユーザーの SIP アドレスの値はユーザー プリンシパル名 (UPN) またはメール アドレスと同じですが、これは必須ではありません。 ユーザーが UPN またはメールを使用して指定されていても、その値が SIP アドレスとは異なる場合、そのユーザーのポリシー割り当ては失敗します。 バッチのユーザーが重複している場合、処理前に重複がバッチから削除され、バッチに残っている一意のユーザーにのみステータスが提供されます。

バッチには最大 5,000 のユーザーを含めることができます。 最適な結果を得る場合は、一度に複数のバッチを送信しない。 さらにバッチを送信する前に、バッチが処理を完了できるようにします。

#### <a name="install-and-connect-to-the-teams-powershell-module"></a>PowerShell モジュールをインストールTeams接続する

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

[Azure AD PowerShell for Graph](/powershell/azure/active-directory/install-adv2)モジュール (まだインストールしていない場合) をダウンロードしてインストールし、Azure AD に接続して、組織内のユーザーの一覧を取得することもできます。

以下を実行して、Azure AD に接続します。

```powershell
Connect-AzureAD
```

メッセージが表示されたら、Teams に接続するために使用したのと同じ管理者資格情報を使用してサイン インします。

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a>ユーザーのバッチにセットアップ ポリシーを割り当てる

この例では [、New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、HR App Setup Policy という名前のアプリ セットアップ ポリシーを Users_ids.txt ファイルに一覧表示されているユーザーのバッチに割り当てします。

```powershell
$users_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

この例では、Azure AD に接続してユーザーのコレクションを取得し、SIP アドレスを使用して指定されたユーザーのバッチに New Hire Messaging Policy という名前のメッセージ ポリシーを割り当てます。

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a>バッチ割り当ての状態を取得する

以下を実行して、バッチ割り当ての状態を取得します。ここで、OperationId は、特定のバッチの `New-CsBatchPolicyAssignmentOperation` コマンドレットによって返される操作 ID です。

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

エラーが発生したことが出力に示されている場合は、次のコマンドを実行して、`UserState` プロパティにあるエラーに関する詳細情報を取得します。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

詳細については、[Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) を参照してください。

## <a name="assign-a-policy-package-to-users"></a>ポリシー パッケージをユーザーに割り当てる

Teams のポリシー パッケージは、組織内で同じまたは類似の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定のコレクションです。 各ポリシー パッケージは、ユーザーの役割に合わせて設計されており、その役割の一般的なアクティビティをサポートする定義済みのポリシーおよびポリシー設定が含まれています。 ポリシー パッケージの例としては、教育機関 (教師) パッケージと医療機関 (医療従事者) パッケージがあります。 詳細については、「[Teams でポリシー パッケージを管理する](manage-policy-packages.md)」を参照してください。

### <a name="assign-a-policy-package-to-one-user"></a>ポリシー パッケージを 1 人のユーザーに割り当てる

1. 管理センターの左側のMicrosoft Teams、[ユーザー] に移動し、ユーザーを選択します。

2. ユーザーのページで 、[ポリシー]を選択し、[ポリシーパッケージ] の横にある [編集] を **選択します**。

3. [ポリシー パッケージ **の割り** 当て] ウィンドウで、割り当てるパッケージを選択し、[保存] を **選択します**。

### <a name="assign-a-policy-package-to-multiple-users"></a>ポリシー パッケージを複数のユーザーに割り当てる

1. Microsoft Teams 管理センターの左側のナビゲーションで **[ポリシー パッケージ]** に移動し、パッケージ名の左側をクリックして、割り当てるポリシー パッケージを選択します。

2. **[ユーザーを管理する]** を選択します。

3. [**ユーザーを管理**] ウィンドウで、表示名またはユーザー名でユーザーを検索し、名前を選択して [**追加**] を選びます。 追加するユーザーごとに、この手順を繰り返します。

4. ユーザーの追加が完了したら、**[保存]** を選択します。

## <a name="assign-a-policy-package-to-a-group"></a>ポリシー パッケージをグループに割り当てる

グループにポリシー パッケージを割り当てると、セキュリティ グループや配布リストなど、ユーザーのグループに複数のポリシーを割り当てることができます。 ポリシーの割り当ては、優先規則に従ってグループのメンバーに反映されます。 グループのメンバーが追加または削除されると、それに応じて継承されたポリシーの割り当てが更新されます。

グループへのポリシー パッケージの割り当ては、最大 50,000 人のユーザーのグループに対して推奨されますが、大規模なグループでも機能します。

ポリシー パッケージを割り当てると、そのポリシーはすぐにグループに割り当てられます。 ただし、グループのメンバーへのポリシー割り当ての反映はバックグラウンド操作として実行され、グループのサイズによっては時間がかかる場合があります。 ポリシーがグループから割り当てられていない場合、またはグループからメンバーが追加または削除された場合も同じです。

> [!IMPORTANT]
> 使用を開始する前に、[優先規則](#precedence-rules)と[グループ割り当てのランク付け](#group-assignment-ranking)を理解することが重要です。 この記事の前半の「[グループへのポリシーの割り当てについて知っておくべきこと](#what-you-need-to-know-about-policy-assignment-to-groups)」の概念を必ず読み、理解してください。

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>管理センターでユーザーのグループにポリシー パッケージを割り当てる

1. Teams 管理センターにサインインします。

2. 左側のナビゲーションで、ポリシー パッケージ ページに移動します。

3. グループ ポリシーの割り当て タブを選択します。

4. [ **グループの追加]** を選択し、[グループにポリシー パッケージを割り当てる] ウィンドウで、次の操作を行います。

    1. ポリシー パッケージを割り当てるグループを検索して追加します。
    
    1. ポリシー パッケージを選択します。
    
    1. ポリシーの種類ごとにランク付けを設定します。
    
    1. **[適用]** を選択します。
    
    ![グループ ポリシーの割り当てを表示します。](media/group-pkg-assignment.png)

5. 特定のポリシーの種類のランク付けを管理するには、特定のポリシー ページに移動します。

6. ポリシー パッケージをグループに再割り当てするには、最初にグループ ポリシーの割り当てを削除します。 次に、上記の手順に従って、ポリシー パッケージをグループに割り当てします。

### <a name="work-with-powershell"></a>PowerShell を使用する

#### <a name="get-the-teams-powershell-module"></a>PowerShell モジュールTeams取得する

段階的なガイダンスについては、「[Teams PowerShell をインストールする](teams-powershell-install.md)」を参照してください。

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>ポリシー パッケージをユーザーのグループに割り当てる

[Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment)コマンドレットを使用して、ポリシー パッケージをグループに割り当てる。 オブジェクト ID、SIP アドレス、または電子メール アドレスを使用して、グループを指定できます。 ポリシー パッケージを割り当てる場合は、ポリシー パッケージの各ポリシーの種類に対して[グループ割り当てのランク付け](#group-assignment-ranking)を指定します。

この例では、Education_Teacher ポリシー パッケージをグループに割り当て、TeamsAppSetupPolicy と TeamsMeetingBroadcastPolicy には 1 のランク付け、TeamsMeetingPolicy には 2 のランク付けを行います。

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>ポリシー パッケージをユーザーのバッチに割り当てる

バッチ ポリシー パッケージの割り当てを使用すると、スクリプトを使用せずに、多数のユーザー セットに同時にポリシー パッケージを割り当てることができます。 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、割り当てる一群のユーザーおよびポリシー パッケージを送信します。 割り当てはバックグラウンド操作として処理され、各バッチの操作 ID が生成されます。 その後、[Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) コマンドレットを使用して、バッチの割り当ての進捗状況と状態を追跡できます。

ユーザーをオブジェクト ID またはセッション開始プロトコル (SIP) アドレスで指定します。 ユーザーの SIP アドレスの値は、多くの場合、ユーザー プリンシパル名 (UPN) またはメール アドレスと同じですが、これは必須ではありません。 ユーザーが UPN またはメールを使用して指定されていても、その値が SIP アドレスとは異なる場合、そのユーザーのポリシー割り当ては失敗します。 バッチのユーザーが重複している場合、処理前に重複がバッチから削除され、バッチに残っている一意のユーザーにのみステータスが提供されます。

バッチには最大 5,000 人のユーザーが含まれる。 最適な結果を得る場合は、一度に複数のバッチを送信しない。 さらにバッチを送信する前に、バッチが処理を完了できるようにします。

### <a name="use-the-teams-powershell-module"></a>PowerShell モジュールTeams使用する

以下を実行して、(まだインストールされていない場合は) [Microsoft Teams PowerShell モジュール](https://www.powershellgallery.com/packages/MicrosoftTeams) をインストールします。 バージョン 1.0.5 以降をインストールしていることを確認します。

```powershell
Install-Module -Name MicrosoftTeams
```

以下を実行して Teams に接続しセッションを開始します。

```powershell
Connect-MicrosoftTeams
```

メッセージが表示されたら、管理者の資格情報を使用してサイン インします。

### <a name="assign-policy-packages-to-a-batch-of-users"></a>ポリシー パッケージをユーザーのバッチに割り当てる

この例では、[New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) コマンドレットを使用して、ユーザーのバッチに Education_PrimaryStudent ポリシー パッケージを割り当てます。

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>バッチ割り当ての状態を確認する

以下を実行して、バッチ割り当ての状態を取得します。ここで、OperationId は、特定のバッチの `New-CsBatchPolicyAssignmentOperation` コマンドレットによって返される操作 ID です。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

エラーが発生したことが出力に示されている場合は、次のコマンドを実行して、`UserState` プロパティにあるエラーに関する詳細情報を取得します。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

詳細については、[Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) を参照してください。

## <a name="related-topics"></a>関連トピック

[Teams PowerShell の概要](teams-powershell-overview.md)
