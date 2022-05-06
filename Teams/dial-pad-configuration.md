---
title: Teams ダイヤル パッドの構成
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: ユーザーが公衆交換電話網 (PSTN) 機能にアクセスできるように、Teams クライアントでダイヤル パッドを構成する方法について説明します。
ms.openlocfilehash: 7fc2622ce0fda97ce608e13d67ff786431a30aa5
ms.sourcegitcommit: 140c34f20f9cd48d7180ff03fddd60f5d1d3459f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2022
ms.locfileid: "65248929"
---
# <a name="dial-pad-configuration"></a>ダイヤル パッドの構成

Teams クライアントでは、ダイヤル パッドを使用すると、ユーザーは公衆交換電話網 (PSTN) 機能にアクセスできます。 ダイヤル パッドは、適切に構成されていれば、電話システム ライセンスを持つユーザーが使用できます。 ダイヤル パッドを表示するには、次の条件がすべて必要です。

- ユーザーが有効な電話システム ("MCOEV") ライセンスを持っている
- ユーザーが Microsoft 通話プラン、オペレーター接続、またはダイレクト ルーティングが有効になっている
- ユーザーが有効エンタープライズ VoIP
- ユーザーはオンプレミスSkype for Businessではなく、オンラインで自宅にいる
- ユーザーがポリシーの呼び出しTeams有効になっている

次のセクションでは、PowerShell を使用して条件を確認する方法について説明します。 ほとんどの場合、Get-CsOnlineUser コマンドレットの出力でさまざまなプロパティを確認する必要があります。 例では、$userがユーザーの UPN または sip アドレスであることを前提としています。

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>ユーザーが有効な電話システム ("MCOEV") ライセンスを持っている

ユーザーに割り当てられたプランに **、[CapabilityStatus] 属性が [有効] に設定** され、[機能] が **MCOEV** (電話システム ライセンス) に設定されていることを確認します。 MCOEV、MCOEV1 などが表示される場合があります。 機能が MCOEV で始まる限り、すべて許容可能です。

属性が正しく設定されていることを確認するには、次のコマンドを使用します。

```
(Get-CsOnlineUser -Identity $user).AssignedPlan
```

出力は次のようになります。 **CapabilityStatus と Capability** **属性のみを** 確認する必要があります。

```
AssignedTimestamp   Capability      CapabilityStatus ServiceInstance                          ServicePlanId
-----------------   ----------      ---------------- ---------------                          -------------
07-02-2020 12:28:48 MCOEV           Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 4828c8ec-dc2e-4779-b502-…
07-02-2020 12:28:48 Teams           Enabled          TeamspaceAPI/NA001                       57ff2da0-773e-42df-b2af-…
```


## <a name="user-has-microsoft-calling-plan-operator-connect-or-is-enabled-for-direct-routing"></a>ユーザーが Microsoft 通話プランを持っている、オペレーター接続またはダイレクト ルーティングが有効になっている

**ユーザーに Microsoft 通話プランがある場合は**、 **CapabilityStatus 属性が [有効] に設定** されていること、および **機能が MCOPSTN に設定** されていることを確認します。 MCOPSTN1、MCOPSTN2 などが表示される場合があります。 機能が MCOPSTN で始まる限り、すべて許容可能です。

属性を確認するには、次のコマンドを使用します。

```
(Get-CsOnlineUser -Identity $user).AssignedPlan
```

出力は次のようになります。 **CapabilityStatus と Capability** **属性のみを** 確認する必要があります。

```  
AssignedTimestamp   Capability      CapabilityStatus ServiceInstance                          ServicePlanId
-----------------   ----------      ---------------- ---------------                          -------------
07-02-2020 12:28:48 MCOEV           Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 4828c8ec-dc2e-4779-b502-…
07-02-2020 12:28:48 MCOPSTN2        Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 5a10155d-f5c1-411a-a8ec-…
07-02-2020 12:28:48 Teams           Enabled          TeamspaceAPI/NA001                       57ff2da0-773e-42df-b2af-…
```
**ユーザーがオペレーター接続に対して有効になっている場合**、ユーザーは TeamsCarrierEmergencyCallRoutingPolicy の null 以外の値を持っている必要があります。 属性を確認するには、次のコマンドを使用します。
  
```
Get-CsOnlineUser -Identity $user|Select TeamsCarrierEmergencyCallRoutingPolicy
```

出力には、次のように null 以外の値を指定する必要があります。

```
TeamsCarrierEmergencyCallRoutingPolicy
--------------------------------------
Synergy_98d1a5cb-d3e6-4306-885e-69a95f2da5c3
```

**ユーザーがダイレクト ルーティングを有効にしている場合は**、OnlineVoiceRoutingPolicy に null 以外の値を割り当てる必要があります。 属性を確認するには、次のコマンドを使用します。
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

出力には、次のように null 以外の値を指定する必要があります。

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>ユーザーが有効エンタープライズ VoIP

ユーザーが有効エンタープライズ VoIPかどうかを確認するには、次のコマンドを使用します。

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

出力は次のようになります。

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>ユーザーはオンプレミスSkype for Businessではなく、オンラインで自宅にいる

ユーザーがオンラインでオンプレミスにSkype for Businessしないようにするには、RegistrarPool を null にし、HostingProvider に "sipfed.online" で始まる値を含める必要があります。  値を確認するには、次のコマンドを使用します。

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

出力は次のようになります。

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>ユーザーがポリシーの呼び出しTeams有効になっている

ユーザーの有効な TeamsCallingPolicy には、AllowPrivateCalling が true に設定されている必要があります。  既定では、ユーザーはグローバル ポリシーを継承します。このポリシーでは、AllowPrivateCallingPolicy が既定で true に設定されています。

ユーザーの TeamsCallingPolicy を取得し、AllowPrivateCalling が true に設定されていることを確認するには、次のコマンドを使用します。

```
if (($p=Get-CsUserPolicyAssignment -Identity $user -PolicyType TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity Global} else {Get-CsTeamsCallingPolicy -Identity $p.PolicyName}
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

## <a name="additional-notes"></a>その他の注意事項

-   これらの構成を変更した後、Teams クライアントを再起動する必要がある場合があります。

-   上記の条件のいずれかを最近更新した場合は、クライアントが新しい設定を受け取るために数時間待つ必要がある場合があります。

-   ダイヤル パッドがまだ表示されない場合は、次のコマンドを使用してプロビジョニング エラーがあるかどうかを確認します。

  ```
  Get-CsOnlineUser -Identity $user|Select UserValidationErrors
  ```

-    24 時間以上経過しても問題が解決しない場合は、サポートにお問い合わせください。


