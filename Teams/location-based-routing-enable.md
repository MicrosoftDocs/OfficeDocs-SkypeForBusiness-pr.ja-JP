---
title: ダイレクト ルーティングの場所に基づくルーティングを有効にする
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: ダイレクトルーティングで位置情報に基づくルーティングを有効にする方法について説明します。これには、ユーザー、ネットワークサイト、ゲートウェイ構成、および通話ポリシーを有効にする方法が含まれます。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4daf270dcd67dc732bba5e5fe134d5a0994dcd75
ms.sourcegitcommit: 2295a668a6f118b95f010e81150351741572b076
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412644"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>ダイレクト ルーティングの場所に基づくルーティングを有効にする

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

この記事の手順を実行する前に、「位置[情報](location-based-routing-plan.md)に基づくルーティングのための[ネットワーク設定を構成](location-based-routing-configure-network-settings.md)する」の手順を参照していることを確認してください。

この記事では、ダイレクトルーティングで位置情報に基づくルーティングを有効にする方法について説明します。 電話システムのダイレクトルーティングを展開し、ネットワークのリージョン、サイト、サブネットをセットアップしたら、位置ベースのルーティングを有効にすることができます。 この記事の手順を実行するには、PowerShell コマンドレットについて理解している必要があります。 詳細については、「 [Teams PowerShell の概要](teams-powershell-overview.md)」を参照してください。

 次の目的で、位置情報に基づくルーティングを有効にする必要があります。
- ユーザー
- ネットワークサイト
- ゲートウェイ構成
- 通話ポリシー

[Microsoft チーム管理センター](#using-the-microsoft-teams-admin-center)または[powershel](#using-powershell)l を使用して、位置情報に基づくルーティングを有効にすることができます。

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターの使用

### <a name="enable-location-based-routing-for-users"></a>ユーザーの位置情報に基づくルーティングを有効にする

1. ボイスルーティングポリシーを作成し、PSTN の使用をポリシーに割り当てます。 PSTN の使用状況をポリシーに割り当てるときは、次のいずれかを実行してください。

    - Pstn ゲートウェイを使っているボイスルーティングに関連付けられた PSTN の使用状況をサイトに対して使います。
    - 場所に基づくルーティングの制限が不要な地域内の PSTN ゲートウェイを使用するボイスルーティングに関連付けられた PSTN の使用状況を使用します。
2. ルーティングの制限が強制される必要があるユーザーに、音声ルーティングポリシーを割り当てます。

ボイスルーティングポリシーを作成してユーザーに割り当てる方法の詳細については、「 [Microsoft Teams でボイスルーティングポリシーを管理](manage-voice-routing-policies.md)する」を参照してください。

### <a name="enable-location-based-routing-for-network-sites"></a>ネットワークサイトで位置情報に基づくルーティングを有効にする

ルーティングの制限を適用する必要があるサイトの位置情報に基づくルーティングを有効にします。 これを行うには、Microsoft Teams 管理センターの左のナビゲーションで、[**場所**の  >  **ネットワークトポロジ**] に移動し、ネットワークサイトを選択し、[**編集**] をクリックして、[**場所に基づくルーティング**] を有効にします。  

詳細については、「[ネットワークトポロジを管理](manage-your-network-topology.md)する」を参照してください。

### <a name="enable-location-based-routing-for-gateways"></a>ゲートウェイで位置情報に基づくルーティングを有効にする

PSTN への通話をルーティングする PSTN ゲートウェイへの通話をルーティングするゲートウェイへの位置情報に基づくルーティングを有効にし、ゲートウェイが配置されているネットワークサイトを関連付けます。 

1. 左側のナビゲーションで、[**音声**の直接ルーティング] に移動し、[  >  **Direct Routing** **SBCs** ] タブをクリックします。
2. SBC を選択し、[**編集**] をクリックします。 
3. [**場所に基づくルーティングとメディアの最適化**] で、[**場所に基づくルーティングを有効にする**] をオンにします。
4. ゲートウェイのサイト ID を指定し、バイパスモードを設定します。
5. **[保存]** をクリックします。

### <a name="enable-location-based-routing-for-calling-policies"></a>通話ポリシーで位置情報に基づくルーティングを有効にする

特定のユーザーに対して位置情報に基づくルーティングを適用するには、ユーザーの通話ポリシーを設定して PSTN の有料電話のバイパスを防ぐようにします。 これを行うには、通話ポリシーで [**有料通話を防ぐ**] 設定をオンにします。

詳細については、「 [Teams の通話ポリシー](teams-calling-policy.md)」を参照してください。

## <a name="using-powershell"></a>PowerShell を使用する場合

### <a name="enable-location-based-routing-for-users"></a>ユーザーの位置情報に基づくルーティングを有効にする

1. PSTN の使用状況を設定するには、 [CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps)コマンドレットを使用します。 複数の使用の場合は、それぞれの使用をコンマで区切ります。

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    次に例を示します。
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. ボイスルーティングポリシーを作成するには、 [CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps)コマンドレットを使用して、ユーザーに適切な PSTN 使用法を関連付けます。

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    ボイスルーティングポリシーに PSTN 使用状況を割り当てる場合は、次のいずれかを実行してください。
    - PSTN ゲートウェイを使っているボイスルーティングに関連付けられた PSTN の使用状況をサイトに対して使用する
    - 場所に基づくルーティングの制限が不要な地域内の PSTN ゲートウェイを使用するボイスルーティングに関連付けられた PSTN の使用状況を使用します。

    この例では、2つの新しいボイスルーティングポリシーを作成し、PSTN の使用を割り当てます。 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    次の表は、この例で定義されているボイスルーティングポリシーを示しています。 
    
    ||ボイスルーティングポリシー1|ボイスルーティングポリシー2|
    |---------|---------|---------|
    |オンラインボイスポリシー ID   |ニューデリーオンラインボイスルーティングポリシー   |Hyderabad online ボイスルーティングポリシー    |
    |オンライン PSTN の使用状況  |長距離  |長距離、ローカル、内部  |

3. [CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps)コマンドレットを使用して、ルーティングの制限が強制されるユーザーにオンラインボイスルーティングポリシーを関連付けます。
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a>ネットワークサイトで位置情報に基づくルーティングを有効にする

1.  [CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps)コマンドレットを使用して、位置情報に基づくルーティングを有効にし、ルーティングの制限を適用する必要があるネットワークサイトに音声ルーティングポリシーを関連付けます。
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    この例では、ニューデリーサイトと Hyderabad サイトの位置情報に基づくルーティングを有効にします。 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    次の表は、この例で位置情報に基づくルーティングが有効になっているサイトを示しています。

    ||サイト 1 (ニューデリー)  |サイト 2 (Hyderabad)  |
    |---------|---------|---------|
|サイト名    |サイト 1 (ニューデリー)    |サイト 2 (Hyderabad)   
    |Enablelocationrouting ルーティング    |True    |True    |
    |サブネット     |Subnet 1 (ニューデリー)     |Subnet 2 (Hyderabad)     |

### <a name="enable-location-based-routing-for-gateways"></a>ゲートウェイで位置情報に基づくルーティングを有効にする

1. [新しい-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps)コマンドレットを使用して、各ゲートウェイまたはネットワークサイトのゲートウェイ構成を作成します。 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    複数のゲートウェイがシステム (ゲートウェイや PBX など) に関連付けられている場合は、各ゲートウェイを変更して、位置情報に基づくルーティングの制限を有効にします。 

    この例では、ゲートウェイごとにゲートウェイ構成を1つ作成します。 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    詳細については、「[ダイレクト ルーティングを構成する](direct-routing-configure.md)」を参照してください。
    
2. [CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps)コマンドレットを使用して、ルーティングの制限を適用する必要があるゲートウェイの位置情報に基づくルーティングを有効にします。 

    PSTN への通話をルーティングする PSTN ゲートウェイへの通話をルーティングするゲートウェイへの位置情報に基づくルーティングを有効にし、ゲートウェイが配置されているネットワークサイトを関連付けます。

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    この例では、ニューデリーと Hyderabad サイトの PSTN ゲートウェイに関連付けられている各ゲートウェイの位置情報に基づくルーティングを有効にします。 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    PSTN への通話をルーティングしないゲートウェイの位置情報に基づくルーティングを有効にしないでください。 ただし、その場合も、システムが配置されているネットワークサイトにゲートウェイを関連付ける必要があります。 これは、このゲートウェイ経由で接続されているエンドポイントに到達するために位置情報に基づくルーティング制限が適用されるためです。 この例では、Hyderabad サイトの PBX システムに関連付けられている各ゲートウェイで、位置情報に基づくルーティングが有効になっていません。

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>通話ポリシーで位置情報に基づくルーティングを有効にする

特定のユーザーに対して位置情報に基づくルーティングを適用するには、ユーザーの音声ポリシーを設定して、PTSN の有料のバイパスを防ぐようにします。 

PSTN の有料電話のバイパスを防止することで、位置情報に基づくルーティングを有効にするには、 [Grant-Csteam/の Grant policy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps)コマンドレットを使用します。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
この例では、PSTN の有料電話が User1 の通話ポリシーにバイパスされるのを防ぎます。 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>関連項目

- [Teams でのクラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)
