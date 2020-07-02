---
title: チームダイヤルパッドの構成
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
description: ユーザーが公衆交換電話網 (PSTN) 機能にアクセスできるように、Teams クライアントでダイヤルパッドを構成する方法について説明します。
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012418"
---
# <a name="dial-pad-configuration"></a>ダイヤルパッドの構成

チームクライアントでは、ダイヤルパッドを使って、ユーザーが公衆交換電話網 (PSTN) 機能にアクセスできるようにします。 ダイヤルパッドは、電話システムのライセンスを持っているユーザーが適切に構成されている場合に利用できます。 ダイヤルパッドを表示するには、次の条件を満たす必要があります。

- ユーザーに有効な電話システム ("MCOEV") ライセンスがある
- ユーザーは Microsoft 通話プランを持っているか、直接ルーティングが有効になっています
- ユーザーがエンタープライズ音声を有効にしている
- ユーザーは、オンプレミスの Skype for Business ではなく、ホームになっています
- ユーザーがチーム呼び出しポリシーを有効にしている

以下のセクションでは、PowerShell を使用して条件を確認する方法について説明します。 ほとんどの場合は、Csonline ユーザーコマンドレットの出力でさまざまなプロパティを確認する必要があります。 例として、ユーザーの UPN または sip アドレスのいずれかを $user と仮定します。

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>ユーザーに有効な電話システム ("MCOEV") ライセンスがある

ユーザーに割り当てられているプランに、 **CapabilityStatus 属性が Enabled に設定**されていて、**機能計画が mcoev** (電話システムライセンス) に設定されていることを確認する必要があります。 MCOEV、MCOEV1 が表示されることがあります。 機能計画が MCOEV で開始されている限り、すべての機能を使用することができます。

属性が正しく設定されていることを確認するには、次のコマンドを使用します。

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

出力は次のようになります。 **CapabilityStatus**と**機能プラン**の属性を確認する必要があるのは、次の場合だけです。

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


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a>ユーザーは Microsoft 通話プランを持っているか、直接ルーティングが有効になっています

**ユーザーが Microsoft の通話プランを持っている場合**は、 **CapabilityStatus 属性が Enabled に設定さ**れていること、および**機能計画が mcopstn に設定さ**れていることを確認する必要があります。 MCOPSTN1、MCOPSTN2 などが表示されることがあります。 機能計画が MCOPSTN で開始されている限り、すべてが受け入れられます。

属性を確認するには、次のコマンドを使用します。

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

出力は次のようになります。 **CapabilityStatus**と**機能プラン**の属性を確認する必要があるのは、次の場合だけです。

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

**ユーザーが直接ルーティングを有効**にしている場合は、OnlineVoiceRoutingPolicy に対して null 以外の値が割り当てられている必要があります。 属性を確認するには、次のコマンドを使用します。
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

出力に null 以外の値が含まれている必要があります。たとえば、次のようになります。

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>ユーザーがエンタープライズ音声を有効にしている

ユーザーがエンタープライズ Voip を有効にしているかどうかを確認するには、次のコマンドを使用します。

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

出力は次のようになります。

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>ユーザーは、オンプレミスの Skype for Business ではなく、ホームになっています

ユーザーがオンプレミスの Skype for Business ではなく、オンラインであることを確認するには、RegistrarPool を null にすることはできません。また、HostingProvider には "sipfed" で始まる値が含まれている必要があります。  値を確認するには、次のコマンドを使用します。

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

出力は次のようになります。

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>ユーザーがチーム呼び出しポリシーを有効にしている

ユーザーの有効な Teamの "ポリシー" は、AllowPrivateCalling が true に設定されている必要があります。  既定では、ユーザーはグローバルポリシーを継承します。既定では、AllowPrivateCallingPolicy が true に設定されています。

ユーザーの TeamAllowPrivateCalling ポリシーを取得し、が true に設定されていることを確認するには、次のコマンドを使用します。

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

出力は次のようになります。

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

## <a name="additional-notes"></a>追加のメモ

-   これらの構成変更を行った後、Teams クライアントの再起動が必要になることがあります。

-   最近上記の条件のいずれかを更新した場合、クライアントが新しい設定を受け取るまでに数時間かかることがあります。

-   それでもダイヤルパッドが表示されない場合は、次のコマンドを使用してプロビジョニングエラーがあるかどうかを確認します。

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    24時間以上経過しても問題が解決しない場合は、サポートにお問い合わせください。


