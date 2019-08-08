---
title: ダイレクト ルーティングの場所に基づくルーティングを有効にする
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: ダイレクトルーティングで位置情報に基づくルーティングを有効にする方法について説明します。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 160a4646ba212c9e654ec06fca2fdd107b2671c7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245130"
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

## <a name="enable-location-based-routing-for-users"></a>ユーザーの位置情報に基づくルーティングを有効にする

1. PSTN の使用状況を設定するには、 [CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps)コマンドレットを使用します。 複数の使用の場合は、それぞれの使用をコンマで区切ります。

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    次に例を示します。
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. ボイスルーティングポリシーを作成するには、 [CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps)コマンドレットを使用して、ユーザーに適切な PSTN 使用法を関連付けます。

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    ボイスルーティングポリシーに PSTN 使用状況を割り当てる場合は、次のいずれかを実行してください。
    - PSTN ゲートウェイを使っているボイスルーティングに関連付けられた PSTN の使用状況をサイトに対して使用する
    - 場所に基づくルーティングの制限が不要な地域内の PSTN ゲートウェイを使用するボイスルーティングに関連付けられた PSTN の使用状況を使用します。

    この例では、2つの新しいボイスルーティングポリシーを作成し、PSTN の使用を割り当てます。 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    次の表は、この例で定義されているボイスルーティングポリシーを示しています。 
    
    ||ボイスルーティングポリシー1|ボイスルーティングポリシー2|
    |---------|---------|---------|
    |オンラインボイスポリシー ID   |ニューデリーオンラインボイスルーティングポリシー   |Hyderabad online ボイスルーティングポリシー    |
    |オンライン PSTN の使用状況  |長距離  |長距離、ローカル、内部  |

3. [CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps)コマンドレットを使用して、ルーティングの制限が強制されるユーザーにオンラインボイスルーティングポリシーを関連付けます。
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a>ネットワークサイトで位置情報に基づくルーティングを有効にする
1.  [CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps)コマンドレットを使用して、位置情報に基づくルーティングを有効にし、ルーティングの制限を適用する必要があるネットワークサイトに音声ルーティングポリシーを関連付けます。
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    この例では、ニューデリーサイトと Hyderabad サイトの位置情報に基づくルーティングを有効にします。 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    次の表は、この例で位置情報に基づくルーティングが有効になっているサイトを示しています。

    ||サイト 1 (ニューデリー)  |サイト 2 (Hyderabad)  |
    |---------|---------|---------|
|サイト名    |サイト 1 (ニューデリー)    |サイト 2 (Hyderabad)   
    |Enablelocationrouting ルーティング    |True    |True    |
    |サブネット     |Subnet 1 (ニューデリー)     |Subnet 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-gateways"></a>ゲートウェイで位置情報に基づくルーティングを有効にする
1. [新しい-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps)コマンドレットを使用して、各ゲートウェイまたはネットワークサイトのゲートウェイ構成を作成します。 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    複数のゲートウェイがシステム (ゲートウェイや PBX など) に関連付けられている場合は、各ゲートウェイを変更して、位置情報に基づくルーティングの制限を有効にします。 

    この例では、ゲートウェイごとにゲートウェイ構成を1つ作成します。 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    詳細については、「[直接ルーティングを構成する](direct-routing-configure.md)」を参照してください。
    
2. [CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps)コマンドレットを使用して、ルーティングの制限を適用する必要があるゲートウェイの位置情報に基づくルーティングを有効にします。 

    PSTN への通話をルーティングする PSTN ゲートウェイへの通話をルーティングするゲートウェイへの位置情報に基づくルーティングを有効にし、ゲートウェイが配置されているネットワークサイトを関連付けます。

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    この例では、ニューデリーと Hyderabad サイトの PSTN ゲートウェイに関連付けられている各ゲートウェイの位置情報に基づくルーティングを有効にします。 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    PSTN への通話をルーティングしないゲートウェイの位置情報に基づくルーティングを有効にしないでください。 ただし、その場合も、システムが配置されているネットワークサイトにゲートウェイを関連付ける必要があります。 これは、このゲートウェイ経由で接続されているエンドポイントに到達するために位置情報に基づくルーティング制限が適用されるためです。 この例では、Hyderabad サイトの PBX システムに関連付けられている各ゲートウェイで、位置情報に基づくルーティングが有効になっていません。

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    PSTN への通話をルーティングしないシステムに接続されたエンドポイント (たとえば、PBX など) には、位置情報に基づくルーティングが有効になっている Teams ユーザーのエンドポイントと同様の制限があります。 つまり、これらのユーザーは、ユーザーの場所に関係なく、Teams ユーザーとの間での通話の発信と受信を行うことができます。 また、システムが関連付けられているネットワークサイトに関係なく、PSTN ネットワーク (たとえば、別の PBX に接続されているエンドポイント) との間で通話を送受信することはできません。 PSTN エンドポイントを含むすべての着信通話、発信通話、通話転送、通話転送には、位置に基づくルーティング enforcements が適用されます。 これらの呼び出しでは、そのシステムにローカルとして定義されている PSTN ゲートウェイのみを使用する必要があります。 

    次の表は、2つの異なるネットワークサイトでの4ゲートウェイのゲートウェイ構成を示しています。2つは PSTN ゲートウェイに接続され、2つは PBX システムに接続されています。 

    ||GatewaySiteLbrEnabled   |NetworkSiteID  |
    |---------|---------|---------|
    |PstnGateway: ゲートウェイ1の DEL-GW    |    True     |   サイト 1 (ニューデリー)      |
    |PstnGateway: ゲートウェイ 2 HYD     |   True      |      サイト 2 (Hyderabad)   |
    |PstnGateway: ゲートウェイ 3 DEL-PBX    |    False     |     サイト 1 (ニューデリー)    |
    |PstnGateway: ゲートウェイ 4 HYD-PBX    |    False     |    サイト 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-calling-policies"></a>通話ポリシーで位置情報に基づくルーティングを有効にする

特定のユーザーに対して位置情報に基づくルーティングを適用するには、ユーザーの音声ポリシーを設定して、PTSN の有料のバイパスを防ぐようにします。 

PSTN の有料電話のバイパスを防止することで、位置情報に基づくルーティングを有効にするには、 [Grant-Csteam/の Grant policy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps)コマンドレットを使用します。

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
この例では、PSTN の有料電話が User1 の通話ポリシーにバイパスされるのを防ぎます。 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a>関連トピック
- [ダイレクト ルーティングの場所に基づくルーティングを計画する](location-based-routing-plan.md)
- [場所に基づくルーティングのネットワーク設定を構成する](location-based-routing-configure-network-settings.md)
- [場所に基づくルーティングの用語集](location-based-routing-terminology.md)
