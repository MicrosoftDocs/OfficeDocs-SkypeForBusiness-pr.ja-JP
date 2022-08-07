---
title: ユーザーの通話設定を構成する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
description: 通話転送と委任のユーザー設定を構成する方法について説明します。
ms.openlocfilehash: 64907043448f44ff861ede026d0a4343899ad98b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272232"
---
# <a name="configure-call-settings-for-your-users"></a>ユーザーの通話設定を構成する

この記事では、管理者がユーザーの通話転送と委任の設定を変更する方法について説明します。 次のような場合は、これらの設定を変更できます。

- ユーザーが病気休暇中であるため、ユーザーへの着信呼び出しが同僚に確実に転送されるようにする必要があります。
- 部門内のすべてのユーザーの通話転送設定を調べて、必要に応じて修正する必要があります。
- 新しいアシスタントが採用され、従業員のグループの代理人としてアシスタントを追加する必要があります。

Teams 管理センターまたは Teams PowerShell コマンドレットを使用して、ユーザーの通話設定を表示および変更できます。

ユーザーの通話設定を設定するには、ユーザーに Microsoft Phone System ライセンスが割り当てられている必要があります。

## <a name="use-the-teams-admin-center"></a>Teams 管理センターを使用する

Teams 管理センターを使用して、ユーザーの転送と未応答の設定、グループ通話ピックアップ、通話委任を構成できます。

即時転送の設定を構成するには:

1. Teams 管理センターで、[ユーザー **の管理****] に** > 移動し、ユーザーを選択します。

2. ユーザーの詳細ページで、[ **音声** ] タブに移動します。

3. [ **通話応答ルール**] で、[ **すぐに転送する**] を選択し、適切な呼び出し転送の種類と宛先を選択します。

同時呼び出しを構成するには、同じページで **[ユーザーのデバイスを呼び出す**] を選択します。 [ **また許可]** ドロップダウンで、適切な同時呼び出し設定を選択します。

未回答の設定を構成するには、同じページで [ **未回答の場合** ] ドロップダウンで適切な設定を選択します。 **[リダイレクトする前のこの秒数のリング**] ドロップダウンで、待機する秒数を指定します。

呼び出し委任とグループ通話ピックアップの構成は、適切な種類を選択することで、通話転送と応答のない設定に統合されます。 たとえば、呼び出しがユーザーの代理人を呼び出すように構成するには、同じページで [**また許可**] で [**委任の呼び出し**] を選択します。 次に、[ **ユーザー** の追加] を選択して **[保存]** をクリックして、適切な代理人を追加します。

## <a name="use-powershell"></a>PowerShell を使用する

PowerShell を使用して、ユーザーの呼び出し転送と委任の設定を構成できます。  Teams PowerShell モジュール バージョン 4.0 以降で使用できる次のコマンドレットを使用します。

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings) - ユーザーの通話転送設定、代理人、委任者情報を表示します。
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings) - ユーザーの通話転送設定を設定します。
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate) - ユーザーのアクセス許可を持つ新しいデリゲートを追加します。
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate) - 既存のデリゲートのアクセス許可を変更します。
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate) - ユーザーからデリゲートを削除します。

### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>ユーザーの通話転送と委任の設定を表示する

ユーザーの現在の呼び出し転送と委任の設定を表示するには、次の例に示すように、Get-CsUserCallingSettings コマンドレットを使用します。

```PowerShell
Get-CsUserCallingSettings -Identity user1@contoso.com
SipUri                    : sip:opr1@contoso.com
IsForwardingEnabled       : True
ForwardingType            : Simultaneous
ForwardingTarget          :
ForwardingTargetType      : MyDelegates
IsUnansweredEnabled       : True
UnansweredTarget          :
UnansweredTargetType      : Voicemail
UnansweredDelay           : 00:00:20
Delegates                 : Id:sip:user2@contoso.com
Delegators                :
CallGroupOrder            : InOrder
CallGroupTargets          : {}
GroupMembershipDetails    :
GroupNotificationOverride : Ring

(Get-CsUserCallingSettings -Identity user1@contoso.com).Delegates

Id             : sip:user2@contoso.com
MakeCalls      : True
ManageSettings : True
ReceiveCalls   : True
```

出力は、user1 が構成されているデリゲートへの同時呼び出しを持っていることを示しています。 応答のない通話は、20 秒後にボイスメールに送信されます。 User2 は、すべてのデリゲートアクセス許可を持つデリゲートとして定義されます。

### <a name="set-call-forward-settings-for-a-user"></a>ユーザーの転送呼び出し設定を設定する

user1 のすべての呼び出しを user2 に転送するには、次の例に示すように、Set-CsUserCallingSettings コマンドレットを使用します。

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

user3 のすべてのデリゲートを同時に呼び出すには、次の例に示すように、Set-CsUserCallingSettings コマンドレットを使用します。

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

次の例では、Set-CsUserCallingSettings コマンドレットを使用して、user5 と user6 をメンバーとして使用する user4 の呼び出しグループを構成します。 グループのメンバーに対するすべての呼び出しは、定義された順序で転送されます。

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

その他の例については、「 [Set-CsUserCallingSettings」を参照してください](/powershell/module/teams/get-csusercallingsettings)。

### <a name="add-a-calling-delegate-for-a-user"></a>ユーザーの呼び出し元デリゲートを追加する

許可されているすべてのアクセス許可を持つ user1 の代理人として user2 を追加するには、次の例に示すように、New-CsUserCallingDelegate コマンドレットを使用します。

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>呼び出し元のデリゲートのアクセス許可を変更する

委任のアクセス許可を変更するには(たとえば、user2 が user1 の呼び出しを許可しないようにする)、次の例に示すように、Set-CsUserCallingDelegate コマンドレットを使用します。

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>ユーザーの呼び出し元デリゲートを削除する

user1 の代理人として user2 を削除するには、次の例に示すように、Remove-CsUserCallingDelegate コマンドレットを使用します。

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```

## <a name="related-topics"></a>関連項目

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings)
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate)
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate)
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate)
