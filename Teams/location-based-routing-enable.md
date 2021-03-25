---
title: ダイレクト ルーティングの場所に基づくルーティングを有効にする
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: ユーザー、ネットワーク Location-Basedゲートウェイの構成、通話ポリシーに対して有効にする方法など、直接ルーティングのルーティングを有効にする方法について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d43d650384dd538ff481ac9625c15b9a9f420d95
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120578"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>ダイレクト ルーティングの場所に基づくルーティングを有効にする

この記事の手順を実行する前に、「ダイレクト ルーティングの計画 [Location-Based](location-based-routing-plan.md) ルーティング」を参照し、「Location-Based ルーティングのネットワーク設定を構成する」の手順 [を完了](location-based-routing-configure-network-settings.md)してください。

この記事では、直接ルーティングの自動ルーティングLocation-Basedする方法について説明します。 電話システム ダイレクト ルーティングを展開し、ネットワーク領域、サイト、サブネットを設定した後、ネットワーク ルーティングを有効Location-Basedできます。 この記事の手順を完了するには、PowerShell コマンドレットに関する理解が必要です。 詳細については [、「Teams PowerShell の概要」を参照してください](teams-powershell-overview.md)。

 次の場合、Location-Basedルーティングを有効にする必要があります。
- ユーザー
- ネットワーク サイト
- ゲートウェイの構成
- 通話ポリシー

Microsoft チーム管理 [センターまたは](#using-the-microsoft-teams-admin-center) [PowerShel](#using-powershell)l を使用して、ルーティングLocation-Basedできます。

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

### <a name="enable-location-based-routing-for-users"></a>ユーザーのLocation-Basedルーティングを有効にする

1. 音声ルーティング ポリシーを作成し、PSTN 使用状況をポリシーに割り当てる。 PSTN 使用状況をポリシーに割り当てる場合は、次のいずれかの操作を行います。

    - サイトにローカルな PSTN ゲートウェイを使用する音声ルートに関連付けられている PSTN 使用状況を使用します。
    - ルーティングの制限が不要な地域にある PSTN ゲートウェイを使用する音声ルートLocation-Based PSTN 使用状況を使用します。
2. ルーティング制限を適用する必要があるユーザーに音声ルーティング ポリシーを割り当てる。

音声ルーティング ポリシーを作成してユーザーに割り当てる方法の詳細については [、「Microsoft Teams](manage-voice-routing-policies.md)で音声ルーティング ポリシーを管理する」を参照してください。

### <a name="enable-location-based-routing-for-network-sites"></a>ネットワーク Location-Basedルーティングを有効にする

ルーティングLocation-Based適用する必要があるサイトのルーティングを有効にする。 これを行うには、Microsoft Teams 管理センターの左側のナビゲーションで、[場所ネットワーク トポロジ] に移動し、ネットワーク サイトを選択し、[編集] をクリックして、[場所に基づくルーティング] をオン  >  **に** します。   

詳細については、「ネットワーク トポロジ [を管理する」を参照してください](manage-your-network-topology.md)。

### <a name="enable-location-based-routing-for-gateways"></a>ゲートウェイLocation-Basedルーティングを有効にする

通話Location-Based PSTN にルーティングする PSTN ゲートウェイに通話をルーティングするゲートウェイへのルーティングを有効にし、ゲートウェイがあるネットワーク サイトを関連付ける。 

1. 左側のナビゲーションで、[**音声ダイレクト** ルーティング]  >  **に移動** し **、[SPC] タブをクリック** します。
2. SBC を選択し、[編集] を **クリックします**。 
3. [ **場所に基づくルーティングとメディアの最適化**] で、[場所に基づく **ルーティングを有効にする] をオンにします**。
4. ゲートウェイ サイト ID を指定し、バイパス モードを設定します。
5. **[保存]** をクリックします。

### <a name="enable-location-based-routing-for-calling-policies"></a>通話Location-Basedルーティングを有効にする

特定のLocation-Basedルーティングを適用するには、PSTN 有料バイパスを防止するためにユーザーの通話ポリシーを設定します。 これを行うには、通話 **ポリシーの** [有料バイパスを防止する] 設定をオンにします。

詳細については [、Teams の通話ポリシーを参照してください](teams-calling-policy.md)。

## <a name="using-powershell"></a>PowerShell の使用

### <a name="enable-location-based-routing-for-users"></a>ユーザーのLocation-Basedルーティングを有効にする

1. PSTN 使用状況 [を設定するには、Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) コマンドレットを使用します。 複数の使用法の場合は、各使用法をコンマで区切ります。

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    次に例を示します。
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps)コマンドレットを使用して音声ルーティング ポリシーを作成し、ユーザーを適切な PSTN 使用状況に関連付ける。

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    PSTN 使用状況を音声ルーティング ポリシーに割り当てる場合は、次のいずれかの操作を行います。
    - サイトにローカルな PSTN ゲートウェイを使用する音声ルートに関連付けられている PSTN 使用状況を使用する
    - ルーティングの制限が不要な地域にある PSTN ゲートウェイを使用する音声ルートLocation-Based PSTN 使用状況を使用します。

    この例では、2 つの新しい音声ルーティング ポリシーを作成し、PSTN 使用状況を割り当てにします。 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    次の表は、この例で定義されている音声ルーティング ポリシーを示しています。 
    
    ||音声ルーティング ポリシー 1|音声ルーティング ポリシー 2|
    |---------|---------|---------|
    |オンライン音声ポリシー ID   |Delhi オンライン音声ルーティング ポリシー   |インターネット音声ルーティング ポリシー    |
    |オンライン PSTN 使用状況  |長距離  |長距離、ローカル、内部  |

3. [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps)コマンドレットを使用して、ルーティング制限を適用する必要があるユーザーにオンライン音声ルーティング ポリシーを関連付ける。
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a>ネットワーク Location-Basedルーティングを有効にする

1.  [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps)コマンドレットを使用して、Location-Based ルーティングを有効にし、ルーティング制限を適用する必要があるネットワーク サイトに音声ルーティング ポリシーを関連付ける。
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    この例では、Delhi サイトとLocation-Basedサイトのルーティングを有効にしています。 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    次の表は、この例の Location-Based有効になっているサイトを示しています。

    ||サイト 1 (Delhi)  |サイト 2 (一時使用数)  |
    |---------|---------|---------|
|サイト名    |サイト 1 (Delhi)    |サイト 2 (一時使用数)   
    |EnableLocationBasedRouting    |True    |True    |
    |サブネット     |サブネット 1 (Delhi)     |サブネット 2 (一時使用数)     |

### <a name="enable-location-based-routing-for-gateways"></a>ゲートウェイLocation-Basedルーティングを有効にする

1. [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps)コマンドレットを使用して、ゲートウェイまたはネットワーク サイトごとにゲートウェイ構成を作成します。 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    複数のゲートウェイがシステム (ゲートウェイや PBX など) に関連付けられている場合は、各ゲートウェイを変更して、ルーティングLocation-Based有効にします。 

    この例では、ゲートウェイごとに 1 つのゲートウェイ構成を作成します。 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    詳細については、「[ダイレクト ルーティングを構成する](direct-routing-configure.md)」を参照してください。
    
2. [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps)コマンドレットを使用して、ルーティングLocation-Based適用する必要があるゲートウェイのルーティングを有効にできます。 

    通話Location-Based PSTN にルーティングする PSTN ゲートウェイに通話をルーティングするゲートウェイへのルーティングを有効にし、ゲートウェイがあるネットワーク サイトを関連付ける。

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    この例では、delhi サイトLocation-Based Pstn ゲートウェイに関連付けられている各ゲートウェイのルーティングを有効にします。 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    PSTN に通話をLocation-Basedゲートウェイのルーティングを有効にしません。 ただし、システムが存在するネットワーク サイトにゲートウェイを関連付ける必要があります。 これは、このLocation-Based経由して接続されるエンドポイントに到達する PSTN 通話には、ルーティング制限を適用する必要があるためです。 この例では、Location-Basedサイトの PBX システムに関連付けられている各ゲートウェイで、ルーティングが有効になっていません。

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>通話Location-Basedルーティングを有効にする

特定のLocation-Basedルーティングを適用するには、PTSN 有料バイパスを防止するためにユーザーの音声ポリシーを設定します。 

[GRANT-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps)コマンドレットを使用して、PSTN 有料Location-Basedによるルーティングを有効にします。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
この例では、User1 の通話ポリシーへの PSTN 有料バイパスを防止します。 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>関連項目

- [Teams のクラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)