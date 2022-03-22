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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System - seo-marvel-apr2020
description: 呼び出しの転送と委任のユーザー設定を構成する方法について説明します。
ms.openlocfilehash: 5443ad958d23753b1d67d42782ddab41d9d6d080
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2022
ms.locfileid: "63689121"
---
# <a name="configure-call-settings-for-your-users"></a>ユーザーの通話設定を構成する

この記事では、管理者がユーザーの通話の転送と委任の設定を変更する方法について説明します。 次の場合に、これらの設定を変更できます。

- ユーザーが病休中で、ユーザーへの着信呼び出しが同僚に転送される必要があります。

- 部署内のすべてのユーザーの通話転送設定を検査し、必要に応じて修正する必要があります。

- 新しいアシスタントが採用され、従業員のグループの代理人としてアシスタントを追加する必要があります。

管理センターまたは powerShell Teamsを使用して、Teamsの通話設定を表示および変更できます。

ユーザーの通話設定を設定するには、ユーザーにシステム ライセンスが割り当Microsoft 電話必要があります。

## <a name="use-the-teams-admin-center"></a>管理センター Teams使用する

管理センターのTeamsを使用して、ユーザーのグループ通話の集荷と通話の委任を構成できます。 

> [!NOTE]
> 現在、コール転送設定を構成するためのオプションは、管理センター Teamsできません。

グループ通話の集荷を構成するには:

1. 管理センター Teams **UsersManage**  >  users に移動し、ユーザーを選択します。

2. ユーザーの詳細ページで、[音声] タブに **移動** します。

3. [グループ **通話の集荷] で、[** ユーザーの **追加] を選択します**。 

4. 通話の遅延と注文 **の設定を指定します**。

委任を構成するには、同じページで [通話の委任] **に移動し** 、[ユーザーの追加 **] を選択します**。

## <a name="use-powershell"></a>PowerShell を使用する

PowerShell を使用して、ユーザーの転送と委任の設定を構成できます。  PowerShell モジュール バージョン 4.0 以降Teams使用できる次のコマンドレットを使用します。

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) - ユーザーの呼び出しの転送設定、代理人、および委任者情報を表示します。

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) - ユーザーの呼び出しの転送設定を設定します。

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) - ユーザーのアクセス許可を持つ新しいデリゲートを追加します。

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) - 既存のデリゲートのアクセス許可を変更します。

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) - ユーザーからデリゲートを削除します。


### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>ユーザーの呼び出し転送と委任の設定を表示する

ユーザーの現在の呼び出し転送と委任設定を表示するには、次の例に示すように Get-CsUserCallingSettings コマンドレットを使用します。

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
Delegates                 : Id:user2@contoso.com
Delegators                : 
CallGroupOrder            : InOrder
CallGroupTargets          : {}
GroupMembershipDetails    :
GroupNotificationOverride : Ring

(Get-CsUserCallingSettings -Identity user1@contoso.com).Delegates

Id             : user2@contoso.com
MakeCalls      : True
ManageSettings : True
ReceiveCalls   : True
```

出力は、user1 が代理人に対して同時呼び出し音が構成されていることを示しています。 応答のない通話は、20 秒後にボイスメールに送信されます。 User2 は、すべての代理人アクセス許可を持つ代理人として定義されます。


### <a name="set-call-forward-settings-for-a-user"></a>ユーザーの呼び出し転送設定を設定する

user1 のすべての呼び出しを user2 に転送するには、次の例に示すように Set-CsUserCallingSettings コマンドレットを使用します。 

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

user3 のすべてのデリゲートを同時に呼び出すには、次の例に示すように Set-CsUserCallingSettings コマンドレットを使用します。 

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

次の例では、Set-CsUserCallingSettings コマンドレットを使用して、user5 と user6 をメンバーとして持つ user4 の呼び出しグループを構成します。 グループのメンバーに対する呼び出しはすべて、定義された順序で転送されます。 

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

その他の例については、「 [Set-CsUserCallingSettings」を参照してください](/powershell/module/teams/get-csusercallingsettings?view=teams-ps)。

### <a name="add-a-calling-delegate-for-a-user"></a>ユーザーの呼び出し元の代理人を追加する

すべてのアクセス許可が許可されている user1 の代理人として user2 を追加するには、次の例に示すように New-CsUserCallingDelegate コマンドレットを使用します。 

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>呼び出し元の代理人のアクセス許可を変更する

代理人のアクセス許可を変更するには(たとえば、user2 が user1 の呼び出しを許可しないなど)、次の例に示すように Set-CsUserCallingDelegate コマンドレットを使用します。 

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>ユーザーの呼び出し元の代理人を削除する

user1 の代理人として user2 を削除するには、次の例に示すように Remove-CsUserCallingDelegate コマンドレットを使用します。 

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```


## <a name="related-topics"></a>関連項目

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) 

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) 

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) 

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) 

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) 
