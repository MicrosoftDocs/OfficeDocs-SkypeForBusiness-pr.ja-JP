---
title: Teamsパッドの構成
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: ユーザーが公衆交換電話網 (PSTN) 機能にアクセスできるよう、Teams クライアントでダイヤル パッドを構成する方法について説明します。
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012418"
---
# <a name="dial-pad-configuration"></a>ダイヤル パッドの構成

クライアントTeamsダイヤル パッドを使用すると、ユーザーは公衆交換電話網 (PSTN) 機能にアクセスできます。 ダイヤル パッドは、適切に構成されている場合電話システムライセンスを持つユーザーが使用できます。 ダイヤル パッドに表示するには、次の条件が必要です。

- ユーザーが有効な電話システム ("MCOEV") ライセンスがある
- ユーザーが Microsoft 通話プランを使用している、または直接ルーティングが有効になっている
- ユーザーが有効エンタープライズ VoIPしました
- ユーザーはオンラインで自宅にいて、オンプレミスSkype for Businessではありません
- ユーザーが通話Teams有効になっている

次のセクションでは、PowerShell を使用して条件を確認する方法について説明します。 ほとんどの場合、Get-CsOnlineUser コマンドレットの出力でさまざまなプロパティを確認する必要があります。 例では、$userユーザーの UPN アドレスまたは sip アドレスのいずれかです。

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>ユーザーが有効な電話システム ("MCOEV") ライセンスがある

ユーザーに割り当てられたプランに **、CapabilityStatus** 属性が [Enabled] に設定され、Capability Plan が **MCOEV** (電話システム) に設定されている必要があります。 MCOEV、MCOEV1 などと表示される場合があります。 機能プランが MCOEV で始まる限り、すべて許容されます。

属性が正しく設定されていることを確認するには、次のコマンドを使用します。

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

出力は次のようになります。 CapabilityStatus 属性と **Capability Plan 属性** のみを確認 **する必要** があります。

```
<Plan SubscribedPlanId="2f9eda01-4630-4a5c-bdb3-cf195f22d240"  
   ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
   CapabilityStatus="Enabled"  
   AssignedTimestamp="2020-04-21T18:31:13Z" 
   ServicePlanId="4828c8ec-dc2e-4779-b502-87ac9ce28ab7" 
   xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11"> 
  <Capability> 
     <Capability Plan="MCOEV" 
     xmlns="http://schemas.microsoft.com/online/MCO/2009/01"/> 
  </Capability>
</Plan>
```


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a>ユーザーが Microsoft 通話プランを使用している、または直接ルーティングが有効になっている

**ユーザーが Microsoft 通話プラン を** 持っている場合は **、CapabilityStatus** 属性が [有効] に設定され、機能プランが **MCOPSTN** に設定されている必要があります。 MCOPSTN1、MCOPSTN2 などと表示される場合があります。 機能プランが MCOPSTN で始まる限り、すべて許容されます。

属性を確認するには、次のコマンドを使用します。

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

出力は次のようになります。 CapabilityStatus 属性と **Capability Plan 属性** のみを確認 **する必要** があります。

```  
<Plan SubscribedPlanId="71d1258e-a4e6-443f-884e-0f3d6f644bb1" 
ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
CapabilityStatus="Enabled"    
AssignedTimestamp="2018-09-18T18:41:42Z" 
ServicePlanId="5a10155d-f5c1-411a-a8ec-e99aae125390" 
xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11">
 <Capability>
    <Capability Plan="MCOPSTN2" 
    xmlns="http://schemas.microsoft.com/online/MCO/2009/01" />
 </Capability>
</Plan>
  ```

**ユーザーが直接ルーティングに対して有効** になっている場合、ユーザーには OnlineVoiceRoutingPolicy に null 以外の値を割り当てる必要があります。 属性を確認するには、次のコマンドを使用します。
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

出力には null 以外の値が必要です。次に例を示します。

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>ユーザーが有効エンタープライズ VoIPしました

ユーザーが有効になっているエンタープライズ VoIP、次のコマンドを使用します。

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

出力は次のように表示されます。

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>ユーザーはオンラインで自宅にいて、オンプレミスSkype for Businessではありません

ユーザーがオンプレミスの Skype for Business ではなくオンラインで自宅にいなければならない場合は、RegistrarPool を null にし、HostingProvider に "sipfed.online" で始まる値を含める必要があります。  値を確認するには、次のコマンドを使用します。

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

出力は次の形式である必要があります。

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>ユーザーが通話Teams有効になっている

ユーザーの有効な TeamsCallingPolicy には、AllowPrivateCalling が true に設定されている必要があります。  既定では、ユーザーはグローバル ポリシーを継承します。AllowPrivateCallingPolicy は既定で true に設定されています。

ユーザーの TeamsCallingPolicy を取得し、AllowPrivateCalling が true に設定されているのを確認するには、次のコマンドを使用します。

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

出力は次のように表示されます。

```
Identity                   : Global
Description                :
AllowPrivateCalling        : True
AllowWebPSTNCalling        : True
AllowVoicemail             : UserOverride
AllowCallGroups            : True
AllowDelegation            : True
AllowCallForwardingToUser  : True
AllowCallForwardingToPhone : True
PreventTollBypass          : False
BusyOnBusyEnabledType      : Disabled
MusicOnHoldEnabledType     : Enabled
``` 

## <a name="additional-notes"></a>その他のメモ

-   これらの構成変更を行った後Teamsクライアントを再起動する必要がある場合があります。

-   上記の条件を最近更新した場合は、クライアントが新しい設定を受信するまで数時間待つ必要があります。

-   それでもダイヤル パッドが表示しない場合は、次のコマンドを使用してプロビジョニング エラーが発生した場合を確認します。

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    24 時間を超え、問題が引き続き発生する場合は、サポートにお問い合わせください。


