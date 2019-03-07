---
title: ダイレクト ルーティングの場所に基づくルーティングを有効にする
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: 直接ルーティングのための場所ベースのルーティングを有効にする方法を説明します。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 809e48e4a770906b93642356cc5f37fd03c411c4
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460333"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>ダイレクト ルーティングの場所に基づくルーティングを有効にする

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

この資料の手順を実行する前に、 [Plan Location-Based を直接ルーティングのルーティング](location-based-routing-plan.md)を参照し、[場所ベースのルーティング用のネットワーク設定の構成](location-based-routing-configure-network-settings.md)手順を完了したことを確認してください。

この資料では、直接ルーティングするための場所ベースのルーティングを有効にする方法について説明します。 電話システムの直接のルーティングを展開し、ネットワーク領域、サイト、およびサブネットを設定すると、場所ベースのルーティングを有効にする準備ができています。 この資料の手順を完了するには、PowerShell コマンドレットをある程度必要があります。 詳細については、[チームの PowerShell の概要](teams-powershell-overview.md)を参照してください。

 次の場所ベースのルーティングを有効にする必要があります。
- ユーザー
- ネットワーク サイト
- ゲートウェイの構成
- ポリシーを呼び出す

## <a name="enable-location-based-routing-for-users"></a>ユーザーの場所ベースのルーティングを有効にします。

1. 使用して、``Set-CsOnlinePstnUsages``コマンドレットは PSTN の使用法を設定します。 複数の使用状況を毎回使用をカンマで区切ります。

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    次に例を示します。
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. 使用して、``New-CsOnlineVoiceRoutingPolicy``にユーザーを関連付ける適切な PSTN 使用法の音声ルーティング ポリシーを作成するコマンドレットです。

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    音声ルーティング ポリシーに PSTN 使用法を割り当てると、次のいずれかの操作を行うことを確認します。
    - サイトをローカルの PSTN ゲートウェイを使用してボイス ルートに関連付けられている PSTN 使用法を使用します。
    - 場所ベースのルーティングの制限が不要の領域内にある PSTN ゲートウェイを使用してボイス ルートに関連付けられている PSTN 使用法を使用します。

    この例は、2 つの新しい音声ルーティング ポリシーを作成し、PSTN の使用法に割り当てることです。 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    次の表は、次の使用例で定義されている音声ルーティング ポリシーを示します。 
    
    ||音声ルーティング ポリシー 1|音声ルーティング ポリシー 2|
    |---------|---------|---------|
    |オンラインでのボイス ポリシー ID   |デリー オンライン音声ルーティング ポリシー   |Hyderabad のオンラインの音声ルーティング ポリシー    |
    |オンラインの PSTN 使用法  |市外通話  |長い距離、ローカルな内部  |

    詳細については、[新規 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)を参照してください。
3. 使用して、``Grant-CsOnlineVoiceRoutingPolicy``オンラインに関連付けるには、コマンドレットの音声ルーティング ポリシーを適用するルーティングの制限を必要とするユーザーです。
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a>ネットワークのサイトの場所ベースのルーティングを有効にします。
1.  使用して、``Set-CsTenantNetworkSite``コマンドレットには、場所ベースのルーティングを有効にして、関連付けの音声ルーティング ポリシー、ルーティングの制限を適用する必要があるネットワーク サイトです。
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    この例では、Delhi サイトおよび Hyderabad のサイトの場所ベースのルーティングを有効にします。 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    次の表は、この例では、場所ベースのルーティングを有効になっているサイトを示します。

    ||サイト 1 (デリー)  |サイト 2 (Hyderabad)  |
    |---------|---------|---------|
|サイト名    |サイト 1 (デリー)    |サイト 2 (Hyderabad)   
    |EnableLocationBasedRouting    |True    |True    |
    |サブネット     |サブネット 1 (デリー)     |サブネット 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-gateways"></a>ゲートウェイの場所ベースのルーティングを有効にします。
1. 使用して、``New-CsOnlinePstnGateway``ゲートウェイ、またはネットワークの各サイトのゲートウェイの構成を作成するコマンドレットです。 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    複数のゲートウェイ (たとえば、ゲートウェイまたは PBX) システムに関連付けられている場合は、場所ベースのルーティングの制限を有効にするには、各ゲートウェイを変更します。 

    この例では、各ゲートウェイの 1 つのゲートウェイの構成を作成します。 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    詳細については、[直接ルーティングの構成](direct-routing-configure.md)を参照してください。
    
2. 使用して、 ``Set-CSOnlinePSTNGateway`` 、ルーティングの制限を適用する必要があるゲートウェイの場所ベースのルーティングを有効にするコマンドレットです。 

    呼び出しをルーティングするゲートウェイに場所ベースのルーティングを有効にする PSTN ゲートウェイが PSTN への呼び出しをルーティングし、ゲートウェイが配置されているネットワーク サイトに関連付けることにします。

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    この例では、デリーおよび Hyderabad のサイトでの PSTN ゲートウェイに関連付けられているゲートウェイごとに場所ベースのルーティングを有効にします。 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    PSTN への呼び出しをルーティングしないゲートウェイの場所ベースのルーティングを有効にしません。 ただし、まだ、システムが配置されているネットワーク サイトへのゲートウェイを関連付ける必要があります。 これは、場所ベースのルーティングの制限は、このゲートウェイ経由で接続されているエンドポイントに到達する PSTN の呼び出しに適用する必要があるためにです。 この例では、場所ベースのルーティングは、デリーおよび Hyderabad のサイト内の PBX システムに関連付けられている各ゲートウェイを有効になっていません。

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    (PBX など) の PSTN への呼び出しをルーティングしないシステムに接続されているエンドポイントでは、場所ベースのルーティングが有効なチームのユーザーのエンドポイントとして、同様の制限があります。 これは、これらのユーザーが配置し、ユーザーの場所に関係なくチームのユーザーとの間の呼び出しを受信することを意味します。 したりすることがどのシステムと関連付けられているネットワーク サイト (たとえば、別の PBX に接続されているエンドポイント) PSTN ネットワークへの呼び出しをルーティングしないその他のシステムとの間の呼び出しを受信します。 着信、発信、転送、PSTN エンドポイントに関連する呼び出しの転送は、場所ベースのルーティングを制限するまで対象となります。 これらの呼び出しは、このようなシステムにローカルに定義されている PSTN ゲートウェイのみを使用してください。 

    次の表は、2 つの別のネットワークのサイトに 4 つのゲートウェイのゲートウェイの構成を示します。 PBX システムに接続されている 2 つの 2 つの PSTN ゲートウェイを接続します。 

    ||GatewaySiteLbrEnabled   |NetworkSiteID  |
    |---------|---------|---------|
    |PstnGateway:Gateway 1 DEL-GW    |    True     |   サイト 1 (デリー)      |
    |PstnGateway:Gateway 2 HYD の GW     |   True      |      サイト 2 (Hyderabad)   |
    |DEL-PBX の PstnGateway:Gateway 3    |    False     |     サイト 1 (デリー)    |
    |PstnGateway:Gateway 4 HYD の PBX    |    False     |    サイト 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-calling-policies"></a>ポリシーを呼び出すための場所ベースのルーティングを有効にします。

特定のユーザーの場所ベースのルーティングを適用するには、PTSN の有料電話を防ぐために、ユーザーの音声ポリシーを設定をバイパスします。 

使用、``Grant-CsTeamsCallingPolicy``の場所ベースの PSTN 通話を防止することでルーティングを有効にするコマンドレットをバイパスします。

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
この例では、User1 に PSTN 有料のバイパス ポリシーを呼び出すことを防ぐことです。 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a>関連トピック
- [ダイレクト ルーティングの場所に基づくルーティングを計画する](location-based-routing-plan.md)
- [場所に基づくルーティングのネットワーク設定を構成する](location-based-routing-configure-network-settings.md)
- [場所に基づくルーティングの用語集](location-based-routing-terminology.md)
