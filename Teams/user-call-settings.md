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
ms.openlocfilehash: 7d1ab3252461d57a99956c90a011a43620c76bea
ms.sourcegitcommit: 18e66d54a9e349d4516253addc85cc12892c69a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2022
ms.locfileid: "68851848"
---
# <a name="configure-call-settings-for-your-users"></a>ユーザーの通話設定を構成する

この記事では、管理者がユーザーの通話転送と委任の設定を変更する方法について説明します。 次の場合など、これらの設定を変更できます。

- ユーザーが病気休暇中であり、ユーザーへの着信が同僚に確実に転送されるようにする必要があります。
- 部署内のすべてのユーザーの着信転送設定を検査し、必要に応じて修正する可能性があります。
- 新しいアシスタントが採用され、従業員のグループの代理人としてアシスタントを追加する必要があります。

Teams 管理センターまたは Teams PowerShell コマンドレットを使用して、ユーザーの通話設定を表示および変更できます。

ユーザーの通話設定を設定するには、ユーザーに Microsoft Phone System ライセンスが割り当てられている必要があります。

## <a name="use-the-teams-admin-center"></a>Teams 管理センターを使用する

Teams 管理センターを使用して、ユーザーの通話転送と未応答の設定、グループ通話ピックアップ、通話委任を構成できます。

即時通話転送設定を構成するには:

1. Teams 管理センターで、[**ユーザー****] [ユーザー** > の管理] に移動し、ユーザーを選択します。

2. ユーザーの詳細ページで、[ **音声** ] タブに移動します。

3. [ **通話応答ルール**] で、[ **すぐに転送する**] を選択し、適切な通話転送の種類と宛先を選択します。

同時呼び出しを構成するには、同じページで [ **ユーザーのデバイスを呼び出す**] を選択します。 [ **許可も許可** する] ドロップダウンで、適切な同時呼び出し設定を選択します。

未回答の設定を構成するには、同じページの [未 **回答の場合** ] ドロップダウンで適切な設定を選択します。 [ **リダイレクト前のこの秒数のリング** ] ドロップダウンで、待機する秒数を指定します。

通話委任とグループ通話ピックアップの構成は、適切な種類を選択することで、通話転送と未応答の設定に統合されます。 たとえば、呼び出しでユーザーの代理人も呼び出すように構成するには、同じページで[**許可も許可** する] の下の [**通話委任**] を選択します。 次に、[ユーザーの追加] を選択し、[保存] をクリックして、適切なデリゲートを **追加****します**。

このビデオでは、ユーザーの音声設定を表示および編集する手順を示します。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE546F7?autoplay=false]

## <a name="use-powershell"></a>PowerShell を使用する

PowerShell を使用して、ユーザーの通話転送と委任の設定を構成できます。  Teams PowerShell モジュール バージョン 4.0 以降で使用できる次のコマンドレットを使用します。

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings) - ユーザーの通話転送設定、デリゲート、および委任情報を表示します。
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings) - ユーザーの通話転送設定を設定します。
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate) - ユーザーのアクセス許可を持つ新しいデリゲートを追加します。
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate) - 既存のデリゲートのアクセス許可を変更します。
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate) - ユーザーからデリゲートを削除します。

### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>ユーザーの通話転送と委任の設定を表示する

ユーザーの現在の通話転送と委任の設定を表示するには、次の例に示すように、Get-CsUserCallingSettings コマンドレットを使用します。

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

出力は、user1 がデリゲートへの同時呼び出しを構成していることを示しています。 未応答の通話は、20 秒後にボイスメールに送信されます。 User2 は、すべてのデリゲート アクセス許可を持つデリゲートとして定義されます。

### <a name="set-call-forward-settings-for-a-user"></a>ユーザーの着信転送設定を設定する

user1 のすべての呼び出しを user2 に転送するには、次の例に示すように、Set-CsUserCallingSettings コマンドレットを使用します。

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

user3 のすべてのデリゲートを同時に呼び出すには、次の例に示すように、Set-CsUserCallingSettings コマンドレットを使用します。

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

次の例では、Set-CsUserCallingSettings コマンドレットを使用して、user5 と user6 をメンバーとして user4 の呼び出しグループを構成します。 グループのメンバーに対するすべての呼び出しは、定義された順序で転送されます。

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

その他の例については、「 [Set-CsUserCallingSettings」を](/powershell/module/teams/get-csusercallingsettings)参照してください。

### <a name="add-a-calling-delegate-for-a-user"></a>ユーザーの呼び出し元デリゲートを追加する

すべてのアクセス許可が許可されている user1 のデリゲートとして user2 を追加するには、次の例に示すように、New-CsUserCallingDelegate コマンドレットを使用します。

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>呼び出し元のデリゲートのアクセス許可を変更する

デリゲートのアクセス許可を変更するには -- たとえば、user2 が user1 の呼び出しを行うことを許可しないようにするには、次の例に示すように、Set-CsUserCallingDelegate コマンドレットを使用します。

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>ユーザーの呼び出し元デリゲートを削除する

user1 のデリゲートとして user2 を削除するには、次の例に示すように、Remove-CsUserCallingDelegate コマンドレットを使用します。

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```

## <a name="additional-notes"></a>その他の注意事項

- ユーザーまたはテナント管理者によって呼び出し応答ルールが変更されたことがないユーザーの既定の動作は、応答されていない通話が 30 秒後にボイスメールに転送されることです。 Team 管理 Center または Teams PowerShell でユーザーに表示される設定には、未回答のターゲットがなしと 20 秒の遅延として表示されます。

## <a name="related-topics"></a>関連項目

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings)
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate)
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate)
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate)
