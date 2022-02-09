---
title: ダイレクト ルーティングの場所に基づくルーティングを有効にする
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: ユーザー、ネットワーク サイト、ゲートウェイLocation-Based呼び出しポリシーに対して有効にする方法など、ダイレクト ルーティングのルーティングを有効にする方法について説明します。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b2a3d74220b685be8a856dc2398b45d0002129ed
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457197"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>ダイレクト ルーティングの場所に基づくルーティングを有効にする

この記事では、ダイレクト ルーティングのルーティングを有効Location-Based方法について説明します。 この記事の手順を実行する前に、「ダイレクト ルーティングの [計画 Location-Based ルーティング](location-based-routing-plan.md) 」を読み、Location-Based ルーティングのネットワーク設定の構成に関するページの [手順を完了してください](location-based-routing-configure-network-settings.md)。

 ダイレクト ルーティングをデプロイし、ネットワーク リージョン、サイト、サブネットを設定した後は、ネットワーク ルーティングを有効Location-Basedできます。 この記事の手順を完了するには、PowerShell コマンドレットに関する理解が必要です。 詳細については、「[PowerShell の概要Teams」を参照してください。](teams-powershell-overview.md)

 次の場合は、Location-Based ルーティングを有効にする必要があります。

- ユーザー
- ネットワーク サイト
- ゲートウェイの構成
- 通話ポリシー

管理センターまたは [PowerShell Teams使用して、](#using-the-microsoft-teams-admin-center)ルーティングを[](#using-powershell)有効Location-Basedできます。

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

### <a name="enable-location-based-routing-for-users"></a>ユーザーLocation-Basedルーティングを有効にする

1. 音声ルーティング ポリシーを作成し、PSTN 使用法をポリシーに割り当てる。 PSTN の使用状況をポリシーに割り当てる場合は、次のいずれかの操作を行います。

    - サイトにローカルの PSTN ゲートウェイを使用する音声ルートに関連付けられている PSTN 使用法を使用します。

    - ルーティングの制限が不要なリージョンにある PSTN ゲートウェイを使用する音声ルートLocation-Based PSTN 使用法を使用します。

2. ルーティング制限を適用する必要があるユーザーに音声ルーティング ポリシーを割り当てる。

音声ルーティング ポリシーを作成し、ユーザーに割り当てる方法の詳細については、「Microsoft Teams で音声ルーティング ポリシーを管理する」[を参照してください](manage-voice-routing-policies.md)。

### <a name="enable-location-based-routing-for-network-sites"></a>ネットワーク Location-Basedルーティングを有効にする

ルーティングLocation-Basedを適用する必要があるサイトのルーティングを有効にする。 これを行うには、Microsoft Teams  >  管理センターの左側のナビゲーションで、[場所]ネットワーク トポロジに移動し、ネットワーク サイトを選択し、[編集] をクリックして、[場所ベースのルーティング] をオン **に** します。  

詳細については、「ネットワーク トポロジの [管理」を参照してください](manage-your-network-topology.md)。

### <a name="enable-location-based-routing-for-gateways"></a>ゲートウェイLocation-Basedルーティングを有効にする

通話Location-Based PSTN にルーティングする PSTN ゲートウェイに通話をルーティングするゲートウェイへのルーティングを有効にし、ゲートウェイがあるネットワーク サイトを関連付ける。 

1. 左側のナビゲーションで [**VoiceDirect Routing**] **に** > 移動し、[**SBC] タブをクリック** します。

2. SBC を選択し、[編集] を **クリックします**。 

3. [ **場所ベースのルーティングとメディアの最適化] で**、[場所ベースのルーティング **を有効にする] をオンにします**。

4. ゲートウェイ サイト ID を指定し、バイパス モードを設定します。

5. **[保存]** をクリックします。

### <a name="enable-location-based-routing-for-calling-policies"></a>通話ポリシーLocation-Basedルーティングを有効にする

特定のユーザーLocation-Basedルーティングを適用するには、PSTN 有料バイパスを防ぐためにユーザーの通話ポリシーを設定します。 これを行うには、呼び出し元ポリシーで **[有料** バイパスを防止する] 設定をオンにします。

詳細については、「Teams でのポリシーの呼び[出し」を参照してください](teams-calling-policy.md)。

## <a name="using-powershell"></a>PowerShell の使用

### <a name="enable-location-based-routing-for-users"></a>ユーザーLocation-Basedルーティングを有効にする

1. PSTN の使用状況を設定するには、 [Set-CsOnlinePstnUsage コマンドレットを使用](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) します。 複数の使用法の場合は、各使用法をコンマで区切ります。

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```

    次に例を示します。

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```

2. ユーザーを適切な PSTN 使用法に関連付ける音声ルーティング ポリシーを作成するには、 [New-CsOnlineVoiceRoutingPolicy コマンドレットを使用](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) します。

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    PSTN の使用状況を音声ルーティング ポリシーに割り当てる場合は、次のいずれかの操作を行います。

    - サイトにローカルの PSTN ゲートウェイを使用する音声ルートに関連付けられている PSTN 使用法を使用します。

    - ルーティングの制限が不要なリージョンにある PSTN ゲートウェイを使用する音声ルートLocation-Based PSTN 使用法を使用します。

    次の例では、2 つの新しい音声ルーティング ポリシーを作成し、PSTN 使用法を割り当てします。 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ``` 

    次の表は、この例で定義されている音声ルーティング ポリシーを示しています。 
    
    |&nbsp;|音声ルーティング ポリシー 1|音声ルーティング ポリシー 2|
    |---------|---------|---------|
    |オンライン音声ポリシー ID   |Delhi オンライン音声ルーティング ポリシー   |ハイデラバード のオンライン音声ルーティング ポリシー    |
    |オンライン PSTN の使用状況  |距離が長い  |Long Distance、Local、Internal  |

3. ルーティング制限を適用する必要があるユーザーにオンライン音声ルーティング ポリシーを関連付けるには、 [Grant-CsOnlineVoiceRoutingPolicy コマンドレットを使用](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) します。

    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```

### <a name="enable-location-based-routing-for-network-sites"></a>ネットワーク Location-Basedルーティングを有効にする

1. ルーティングを有効Location-Basedルーティングを有効にし、ルーティング制限を適用する必要があるネットワーク サイトに音声ルーティング ポリシーを関連付けるには、 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) コマンドレットを使用します。

    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    この例では、Location-Basedハイデラバード サイトのルーティングを有効にしています。 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    次の表は、この例の Location-Based有効なサイトを示しています。

    |&nbsp;|サイト 1 (Delhi)  |サイト 2 (ハイデラバード)  |
    |---------|---------|---------|
    |サイト名    |サイト 1 (Delhi)    |サイト 2 (ハイデラバード)|
    |EnableLocationBasedRouting    |True    |True    |
    |サブネット     |サブネット 1 (Delhi)     |サブネット 2 (ハイデラバード)     |


### <a name="enable-location-based-routing-for-gateways"></a>ゲートウェイLocation-Basedルーティングを有効にする

1. ゲートウェイまたはネットワーク サイトごとにゲートウェイ構成を作成するには、 [New-CsOnlinePSTNGateway コマンドレットを使用](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) します。 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```

    複数のゲートウェイがシステム (ゲートウェイや PBX など) に関連付けられている場合は、各ゲートウェイを変更して、ルーティングLocation-Based有効にします。 

    次の例では、ゲートウェイごとに 1 つのゲートウェイ構成を作成します。 

    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    詳細については、「[ダイレクト ルーティングを構成する](direct-routing-configure.md)」を参照してください。
    
2. ルーティング制限Location-Basedする必要があるゲートウェイのルーティングを有効にするには、 [Set-CSOnlinePSTNGateway コマンドレットを使用](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) します。 

    通話Location-Based PSTN にルーティングする PSTN ゲートウェイに通話をルーティングするゲートウェイへのルーティングを有効にし、ゲートウェイがあるネットワーク サイトを関連付ける。

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

   次の例ではLocation-Based、Delhi サイトとハイデラバード サイトの PSTN ゲートウェイに関連付けられている各ゲートウェイのルーティングを有効にします。 

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```

    PSTN に通話Location-Basedルーティングしないゲートウェイのルーティングを有効にしない。 ただし、システムが存在するネットワーク サイトにゲートウェイを関連付ける必要があります。 これは、このゲートウェイLocation-Based接続されているエンドポイントに到達する PSTN 通話には、ルーティング制限を適用する必要があるためです。 この例ではLocation-Based、Delhi サイトとハイデラバード サイトの PBX システムに関連付けられているゲートウェイごとに、このルーティングが有効になっていません。

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>通話ポリシーLocation-Basedルーティングを有効にする

特定のユーザーLocation-Basedルーティングを強制するには、PTSN 有料バイパスを防ぐためにユーザーの音声ポリシーを設定します。 

PSTN 有料Location-Basedを防止してルーティングを有効にするには、 [Grant-CsTeamsCallingPolicy コマンドレットを使用](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) します。


```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```

この例では、ユーザー 1 の通話ポリシーへの PSTN 有料バイパスを防止します。 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>関連項目

- [Teams のクラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)