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
description: ユーザー、ネットワーク サイト、ゲートウェイLocation-Based呼び出しポリシーに対して有効にする方法など、ダイレクト ルーティングのルーティングを有効にする方法について説明します。
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

この記事の手順を実行する前に、「直接ルーティングの [Location-Based ルーティング](location-based-routing-plan.md) の計画」を読み、Location-Based ルーティングのネットワーク設定の構成に関するページ [の手順を完了してください](location-based-routing-configure-network-settings.md)。

この記事では、ダイレクト ルーティングのルーティングを有効Location-Based方法について説明します。 直接ルーティング電話システムデプロイし、ネットワーク リージョン、サイト、サブネットを設定した後、ネットワーク ルーティングを有効Location-Basedできます。 この記事の手順を完了するには、PowerShell コマンドレットに精通している必要があります。 詳細については[、「PowerShell の概要Teamsを参照してください](teams-powershell-overview.md)。

 次の場合は、Location-Basedルーティングを有効にする必要があります。
- ユーザー
- ネットワーク サイト
- ゲートウェイの構成
- 通話ポリシー

Microsoft Team 管理センター [または](#using-the-microsoft-teams-admin-center) [PowerShel](#using-powershell)l を使用して、ルーティングを有効Location-Basedできます。

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

### <a name="enable-location-based-routing-for-users"></a>ユーザーLocation-Basedルーティングを有効にする

1. 音声ルーティング ポリシーを作成し、PSTN 使用法をポリシーに割り当てる。 PSTN の使用状況をポリシーに割り当てる場合は、次のいずれかの操作を行います。

    - サイトにローカルの PSTN ゲートウェイを使用する音声ルートに関連付けられている PSTN 使用法を使用します。
    - ルーティングの制限が不要なリージョンにある PSTN ゲートウェイを使用する音声ルートLocation-Based PSTN 使用法を使用します。
2. ルーティング制限を適用する必要があるユーザーに音声ルーティング ポリシーを割り当てる。

音声ルーティング ポリシーを作成してユーザーに割り当てる方法の詳細については、「音声ルーティング ポリシーを管理する」を参照[Microsoft Teams。](manage-voice-routing-policies.md)

### <a name="enable-location-based-routing-for-network-sites"></a>ネットワーク Location-Basedルーティングを有効にする

ルーティングLocation-Basedを適用する必要があるサイトのルーティングを有効にする。 これを行うには、Microsoft Teams 管理センターの左側のナビゲーションで、[場所] ネットワークトポロジに移動し、ネットワーク サイトを選択し、[編集] をクリックして、[場所ベースのルーティング] をオン  >  **にします**。   

詳細については、「ネットワーク トポロジの [管理」を参照してください](manage-your-network-topology.md)。

### <a name="enable-location-based-routing-for-gateways"></a>ゲートウェイLocation-Basedルーティングを有効にする

通話Location-Based PSTN にルーティングする PSTN ゲートウェイにルーティングするゲートウェイへのルーティングを有効にし、ゲートウェイがあるネットワーク サイトを関連付ける。 

1. 左側のナビゲーションで、[**音声ダイレクト** ルーティング]  >  **に移動し****、[SBC] タブをクリック** します。
2. SBC を選択し、[編集] を **クリックします**。 
3. [ **場所ベースのルーティングとメディアの最適化] で**、[場所ベースのルーティング **を有効にする] をオンにします**。
4. ゲートウェイ サイト ID を指定し、バイパス モードを設定します。
5. **[保存]** をクリックします。

### <a name="enable-location-based-routing-for-calling-policies"></a>通話ポリシーLocation-Basedルーティングを有効にする

特定のユーザーLocation-Basedルーティングを強制するには、PSTN 有料バイパスを防ぐために、ユーザーの呼び出しポリシーを設定します。 これを行うには、呼び出し元ポリシーで **[有料** バイパスを防止する] 設定をオンにします。

詳細については、「Teams でのポリシーの呼び出し[」を参照してください](teams-calling-policy.md)。

## <a name="using-powershell"></a>PowerShell の使用

### <a name="enable-location-based-routing-for-users"></a>ユーザーLocation-Basedルーティングを有効にする

1. [SET-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps)コマンドレットを使用して PSTN の使用状況を設定します。 複数の使用法の場合は、各使用法をコンマで区切ります。

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    次に例を示します。
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps)コマンドレットを使用して、ユーザーを適切な PSTN 使用法に関連付ける音声ルーティング ポリシーを作成します。

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    PSTN の使用状況を音声ルーティング ポリシーに割り当てる場合は、次のいずれかの操作を行います。
    - サイトにローカルの PSTN ゲートウェイを使用する音声ルートに関連付けられている PSTN 使用法を使用する
    - ルーティングの制限が不要なリージョンにある PSTN ゲートウェイを使用する音声ルートLocation-Based PSTN 使用法を使用します。

    この例では、2 つの新しい音声ルーティング ポリシーを作成し、PSTN 使用法を割り当てします。 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    次の表は、この例で定義されている音声ルーティング ポリシーを示しています。 
    
    ||音声ルーティング ポリシー 1|音声ルーティング ポリシー 2|
    |---------|---------|---------|
    |オンライン音声ポリシー ID   |Delhi オンライン音声ルーティング ポリシー   |ハイデラバード のオンライン音声ルーティング ポリシー    |
    |オンライン PSTN の使用状況  |距離が長い  |Long Distance、Local、Internal  |

3. [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps)コマンドレットを使用して、ルーティング制限を適用する必要があるユーザーにオンライン音声ルーティング ポリシーを関連付ける。
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a>ネットワーク Location-Basedルーティングを有効にする

1.  [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps)コマンドレットを使用して、Location-Based ルーティングを有効にし、ルーティング制限を適用する必要があるネットワーク サイトに音声ルーティング ポリシーを関連付ける。
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    この例では、Delhi サイトLocation-Basedハイデラバード サイトのルーティングを有効にしています。 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    次の表は、この例でルーティングをLocation-Basedサイトを示しています。

    ||サイト 1 (Delhi)  |サイト 2 (ハイデラバード)  |
    |---------|---------|---------|
|サイト名    |サイト 1 (Delhi)    |サイト 2 (ハイデラバード)   
    |EnableLocationBasedRouting    |True    |True    |
    |サブネット     |サブネット 1 (Delhi)     |サブネット 2 (ハイデラバード)     |

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
    
2. [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps)コマンドレットを使用して、ルーティングLocation-Basedを適用する必要があるゲートウェイのルーティングを有効にできます。 

    通話Location-Based PSTN にルーティングする PSTN ゲートウェイにルーティングするゲートウェイへのルーティングを有効にし、ゲートウェイがあるネットワーク サイトを関連付ける。

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    この例では、delhi サイトとハイLocation-Basedサイトの PSTN ゲートウェイに関連付けられている各ゲートウェイのルーティングを有効にします。 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    PSTN に通話Location-Basedルーティングしないゲートウェイのルーティングを有効にしない。 ただし、システムが存在するネットワーク サイトにゲートウェイを関連付ける必要があります。 これは、このゲートウェイLocation-Based接続されているエンドポイントに到達する PSTN 通話には、ルーティング制限を適用する必要があるためです。 この例ではLocation-Based、Delhi サイトとハイデラバード サイトの PBX システムに関連付けられている各ゲートウェイで、このルーティングが有効になっていません。

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>通話ポリシーLocation-Basedルーティングを有効にする

特定のユーザーLocation-Basedルーティングを適用するには、PTSN 有料バイパスを防ぐためにユーザーの音声ポリシーを設定します。 

[Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps)コマンドレットを使用して、PSTN 有料バイパスLocation-Basedルーティングを有効にします。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
この例では、ユーザー 1 の通話ポリシーへの PSTN 有料バイパスを防止します。 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>関連トピック

- [Teams のクラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)