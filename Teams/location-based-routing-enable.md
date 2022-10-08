---
title: ダイレクト ルーティングの場所に基づくルーティングを有効にする
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: ユーザー、ネットワーク サイト、ゲートウェイ構成、通話ポリシーの有効化など、ダイレクト ルーティングのLocation-Basedルーティングを有効にする方法について説明します。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4039105fe27df6fa8acb3f14c0db076e56910403
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999322"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>ダイレクト ルーティングの場所に基づくルーティングを有効にする

この記事では、ダイレクト ルーティングのLocation-Basedルーティングを有効にする方法について説明します。 この記事の手順に従う前に、「 [ダイレクト ルーティングのLocation-Basedルーティングを計画する](location-based-routing-plan.md) 」を参照し、「 [Location-Based ルーティングのネットワーク設定を構成する](location-based-routing-configure-network-settings.md)」の手順を完了していることを確認してください。

 ダイレクト ルーティングを展開し、ネットワークリージョン、サイト、サブネットを設定したら、Location-Basedルーティングを有効にする準備が整います。 この記事の手順を完了するには、PowerShell コマンドレットに関する知識が必要です。 詳細については、「[Teams PowerShell の概要](teams-powershell-overview.md)」を参照してください。

 次のLocation-Basedルーティングを有効にする必要があります。

- ユーザー
- ネットワーク サイト
- ゲートウェイの構成
- 通話ポリシー

[Teams 管理センター](#using-the-microsoft-teams-admin-center)または [PowerShell](#using-powershell) を使用して、Location-Basedルーティングを有効にすることができます。

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

### <a name="enable-location-based-routing-for-users"></a>ユーザーのLocation-Basedルーティングを有効にする

1. 音声ルーティング ポリシーを作成し、PSTN 使用法をポリシーに割り当てます。 ポリシーに PSTN 使用法を割り当てる場合は、次のいずれかの操作を行うことを確認します。

    - サイトにローカルの PSTN ゲートウェイを使用する音声ルートに関連付けられている PSTN 使用法を使用します。

    - Location-Basedルーティング制限が必要ないリージョンにある PSTN ゲートウェイを使用する音声ルートに関連付けられた PSTN 使用法を使用します。

2. ルーティング制限を適用する必要があるユーザーに音声ルーティング ポリシーを割り当てます。

音声ルーティング ポリシーを作成し、ユーザーに割り当てる方法の詳細については、「 [Microsoft Teams での音声ルーティング ポリシーの管理](manage-voice-routing-policies.md)」を参照してください。

### <a name="enable-location-based-routing-for-network-sites"></a>ネットワーク サイトのLocation-Basedルーティングを有効にする

ルーティング制限を適用する必要があるサイトのLocation-Basedルーティングを有効にします。 これを行うには、Microsoft Teams 管理センターの左側のナビゲーションで、 **場所** > **ネットワーク トポロジに移動し、ネットワーク サイトを** 選択して **[編集]** をクリックし、[ **場所ベースのルーティング]** をオンにします。  

詳細については、「 [ネットワーク トポロジの管理」を参照してください](manage-your-network-topology.md)。

### <a name="enable-location-based-routing-for-gateways"></a>ゲートウェイのLocation-Basedルーティングを有効にする

PSTN に通話をルーティングする PSTN ゲートウェイに通話をルーティングするゲートウェイへのLocation-Basedルーティングを有効にし、ゲートウェイが配置されているネットワーク サイトを関連付けます。 

1. 左側のナビゲーションで、[ **音声** > **ダイレクト ルーティング**] に移動し、[ **SBC** ] タブをクリックします。

2. SBC を選択し、[編集] をクリック **します**。 

3. **[場所ベースのルーティングとメディアの最適化**] で、[**場所ベースのルーティングを有効にする] を** オンにします。

4. ゲートウェイ サイト ID を指定し、バイパス モードを設定します。

5. **[保存]** をクリックします。

### <a name="enable-location-based-routing-for-calling-policies"></a>ポリシーを呼び出すためのLocation-Basedルーティングを有効にする

特定のユーザーに対してLocation-Basedルーティングを適用するには、PSTN 有料バイパスを防止するようにユーザーの通話ポリシーを設定します。 これを行うには、呼び出し元ポリシーで **[通行料バイパスの防止** ] 設定をオンにします。

詳細については、「 [Teams でのポリシーの呼び出し](teams-calling-policy.md)」を参照してください。

## <a name="using-powershell"></a>PowerShell の使用

### <a name="enable-location-based-routing-for-users"></a>ユーザーのLocation-Basedルーティングを有効にする

1. PSTN 使用法を設定するには、 [Set-CsOnlinePstnUsage コマンドレットを](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) 使用します。 複数の使用法の場合は、各使用法をコンマで区切ります。

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```

    次に例を示します。

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```

2. 適切な PSTN 使用法にユーザーを関連付ける音声ルーティング ポリシーを作成するには、 [New-CsOnlineVoiceRoutingPolicy コマンドレットを](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) 使用します。

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    音声ルーティング ポリシーに PSTN 使用法を割り当てる場合は、次のいずれかの操作を行うことを確認します。

    - サイトにローカルの PSTN ゲートウェイを使用する音声ルートに関連付けられている PSTN 使用法を使用します。

    - Location-Basedルーティング制限が必要ないリージョンにある PSTN ゲートウェイを使用する音声ルートに関連付けられた PSTN 使用法を使用します。

    次の例では、2 つの新しい音声ルーティング ポリシーを作成し、PSTN 使用法をそれらに割り当てます。 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ``` 

    次の表は、この例で定義されている音声ルーティング ポリシーを示しています。 
    
    |&nbsp;|音声ルーティング ポリシー 1|音声ルーティング ポリシー 2|
    |---------|---------|---------|
    |オンライン音声ポリシー ID   |オンライン音声ルーティング ポリシー   |ハイダラーバット オンライン音声ルーティング ポリシー    |
    |オンライン PSTN 使用法  |長距離  |長距離、ローカル、内部  |

3. オンライン音声ルーティング ポリシーを、ルーティング制限を適用する必要があるユーザーに関連付けるには、 [Grant-CsOnlineVoiceRoutingPolicy コマンドレットを](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) 使用します。

    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```

### <a name="enable-location-based-routing-for-network-sites"></a>ネットワーク サイトのLocation-Basedルーティングを有効にする

1. Location-Basedルーティングを有効にし、ルーティング制限を適用する必要があるネットワーク サイトに音声ルーティング ポリシーを関連付けるには、 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) コマンドレットを使用します。

    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    次の使用例は、Location-Basedルーティングを有効にし、この方法で、1 つ 1 つを指定します。 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    次の表は、この例でLocation-Basedルーティングが有効になっているサイトを示しています。

    |&nbsp;|サイト 1 (インド)  |サイト 2 (ハイダラード)  |
    |---------|---------|---------|
    |サイト名    |サイト 1 (インド)    |サイト 2 (ハイダラード)|
    |EnableLocationBasedRouting    |True    |True    |
    |サブネット     |サブネット 1 (1)     |サブネット 2 (ハイダラード)     |


### <a name="enable-location-based-routing-for-gateways"></a>ゲートウェイのLocation-Basedルーティングを有効にする

1. ゲートウェイまたはネットワーク サイトごとにゲートウェイ構成を作成するには、 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) コマンドレットを使用します。 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```

    複数のゲートウェイがシステム (ゲートウェイや PBX など) に関連付けられている場合は、Location-Basedルーティング制限を有効にするように各ゲートウェイを変更します。 

    次の例では、ゲートウェイごとに 1 つのゲートウェイ構成を作成します。 

    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    詳細については、「[ダイレクト ルーティングを構成する](direct-routing-configure.md)」を参照してください。
    
2. ルーティング制限を適用する必要があるゲートウェイのLocation-Basedルーティングを有効にするには、 [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) コマンドレットを使用します。 

    PSTN に通話をルーティングする PSTN ゲートウェイに通話をルーティングするゲートウェイへのLocation-Basedルーティングを有効にし、ゲートウェイが配置されているネットワーク サイトを関連付けます。

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

   次の例では、1 つのゲートウェイに対してLocation-Basedルーティングを有効にします。このルーティングは、このゲートウェイが、このゲートウェイに関連付けられている場合は、Pstn ゲートウェイに関連付けられます。 

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```

    PSTN に通話をルーティングしないゲートウェイのLocation-Basedルーティングを有効にしないでください。 ただし、システムが配置されているネットワーク サイトにゲートウェイを関連付ける必要があります。 これは、このゲートウェイ経由で接続されているエンドポイントに到達する PSTN 通話に対して、Location-Basedルーティング制限を適用する必要があるためです。 この例では、Location-Based ルーティングは、Deli および 2016 サイトの PBX システムに関連付けられているゲートウェイごとに有効になっていません。

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>ポリシーを呼び出すためのLocation-Basedルーティングを有効にする

特定のユーザーに対してLocation-Basedルーティングを適用するには、PTSN 有料バイパスを防止するようにユーザーの音声ポリシーを設定します。 

PSTN 有料バイパスを防止してLocation-Basedルーティングを有効にするには、 [Grant-CsTeamsCallingPolicy コマンドレットを](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) 使用します。


```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```

この例では、ユーザー 1 の通話ポリシーへの PSTN 有料バイパスを防止します。 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>関連項目

- [Teams のクラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)