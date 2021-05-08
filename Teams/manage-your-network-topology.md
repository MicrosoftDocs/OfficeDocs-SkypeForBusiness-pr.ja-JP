---
title: クラウド音声機能のネットワーク トポロジを管理する Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: クラウド音声機能のネットワーク設定を構成する方法については、Microsoft Teams。
ms.openlocfilehash: c77f1e6d31953ce529bff1fab6aa16e1d889e29f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101063"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>クラウド音声機能のネットワーク トポロジを管理する Microsoft Teams

組織で直接ルーティングまたは動的[](location-based-routing-plan.md)緊急通話用の場所ベースのルーティング[](configure-dynamic-emergency-calling.md)を展開している場合は、Microsoft Teams でこれらのクラウド音声機能で使用するネットワーク設定を構成する必要があります。 ネットワーク設定は、ネットワーク リージョン、ネットワーク サイト、サブネットTeams信頼できる IP アドレスなど、クライアントの場所を特定するために使用されます。 デプロイするクラウド音声機能に応じて、これらの設定の一部またはすべてが構成されます。 これらの用語の詳細については、「クラウド音声機能の [ネットワーク設定」を参照してください](cloud-voice-network-settings.md)。

ネットワーク設定は、管理センターの **[ネットワーク トポロジ**] ページでMicrosoft Teamsを使用して構成Windows PowerShell。

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>管理センターでネットワーク設定Microsoft Teams構成する

[!INCLUDE [preview-feature](includes/preview-feature.md)]

ネットワーク トポロジ ページの [ネットワーク サイト] タブで、ネットワーク リージョン、ネットワーク サイト、サブネット **を定義** します。 ここでは、ネットワーク サイトを作成または変更したり、サイトをネットワーク リージョンに関連付け、サブネットをサイトに関連付け、場所ベースのルーティングを有効にしたり、緊急ポリシーをサイトに割り当てすることができます。 また、すべてのサイトでグローバルに使用できるネットワーク リージョンを追加できます。

#### <a name="add-and-configure-a-network-site"></a>ネットワーク サイトの追加と構成

1. 管理センターの左側のナビゲーションMicrosoft Teams、[**場所**] [ネットワーク トポロジ] に移動し、[ネットワーク サイト]  >  **タブをクリック** します。
2. [ **追加]** をクリックし、サイトの名前と説明を入力します。

    ![[ネットワーク サイトの追加] ページのスクリーンショット](media/manage-network-topology-add-site.png)

3. サイトをネットワーク リージョンに関連付けるには、[ネットワーク リージョンの追加] をクリックし、既存のリージョンを選択するか、[追加] をクリックしてリージョンを追加し、[リンク] を **クリックします**。  
4. サイトのLocation-Basedルーティングを有効にするには、[場所ベースのルーティング **] をオンにします**。
5. 緊急サービス ポリシーをサイトに割り当てるには、次のいずれかの操作を行います。

    - 組織で通話プランを使用している場合、または直接ルーティング電話システムデプロイされている場合は、[緊急通話ポリシー] で目的のポリシーを選択します。
    - 組織が直接ルーティングを電話システム場合は、[**緊急通話ルーティング** ポリシー] で目的のポリシーを選択します。

6. サイトにサブネットを関連付けるには、[サブネット] で [サブネットの追加 **] をクリックします**。 IP バージョン、IP アドレス、ネットワーク範囲を指定し、説明を追加して、[適用] を **クリックします**。 各サブネットは、特定のサイトに関連付けられている必要があります。
7. **[保存]** をクリックします。

#### <a name="modify-a-network-site"></a>ネットワーク サイトを変更する

1. 管理センターの左側のナビゲーションMicrosoft Teams、[**場所**] [ネットワーク トポロジ] に移動し、[ネットワーク サイト]  >  **タブをクリック** します。
2. サイト名の左側をクリックしてサイトを選択し、[編集] をクリック **します**。
3. 必要な変更を加え、[保存] を **クリックします。**

### <a name="manage-external-trusted-ip-addresses"></a>外部の信頼済み IP アドレスを管理する

外部の信頼できる IP アドレスは、管理センターの[ネットワーク トポロジ] ページの [信頼できる IP] タブMicrosoft Teams管理します。 外部の信頼できる IP アドレスの数に制限はありません。

#### <a name="add-a-trusted-ip-address"></a>信頼できる IP アドレスを追加する

1. 管理センターの左側のMicrosoft Teams、[**場所**] ネットワーク トポロジ に移動し、[信頼できる  >  **IPs] タブをクリック** します。
2. [**新規**] をクリックします。
3. [信頼 **できる IP アドレスの追加** ] ウィンドウで、IP バージョン、IP アドレス、ネットワーク範囲を指定し、説明を追加して、[適用] を **クリックします**。

    ![[信頼できる IP アドレスの追加] ウィンドウのスクリーンショット](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>信頼できる IP アドレスを編集する

1. 管理センターの左側のMicrosoft Teams、[**場所**] ネットワーク トポロジ に移動し、[信頼できる  >  **IPs] タブをクリック** します。
2. IP アドレスの左側をクリックして選択し、[編集] をクリック **します**。
3. [信頼 **できる IP アドレスの編集]** ウィンドウで、必要な変更を行い、[適用] を **クリックします**。

## <a name="configure-network-settings-using-powershell"></a>PowerShell を使用してネットワーク設定を構成する

このセクションの手順を完了するには、PowerShell コマンドレットに精通している必要があります。 詳細については[、「PowerShell の概要Teamsを参照してください](teams-powershell-overview.md)。

### <a name="define-network-regions"></a>ネットワーク リージョンを定義する

 [New-CsTenantNetworkRegion](/powershell/module/skype/New-CsTenantNetworkRegion)コマンドレットを使用して、ネットワーク リージョンを定義します。 RegionID パラメーターはリージョンの地理を表す論理名であり、依存関係や制限はありません。CentralSite サイト ID パラメーターは &lt; &gt; 省略可能です。

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

この例では、インドという名前のネットワーク リージョンを作成します。

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

[「Set-CsTenantNetworkRegion」も参照してください](/powershell/module/skype/set-cstenantnetworkregion)。

### <a name="define-network-sites"></a>ネットワーク サイトを定義する

[New-CsTenantNetworkSite コマンドレットを使用して](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps)、ネットワーク サイトを定義します。 各ネットワーク サイトは、ネットワーク リージョンに関連付けられている必要があります。

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

この例では、インドリージョンに 2 つの新しいネットワーク サイト 、Delhi とハイデラバードを作成します。

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

次の表は、この例で定義されているネットワーク サイトを示しています。

||サイト 1 |サイト 2 |
|---------|---------|---------|
|サイト ID    |    サイト 1 (Delhi)     |  サイト 2 (ハイデラバード)       |
|リージョン ID  |     リージョン 1 (インド)    |   リージョン 1 (インド)      |

[「Set-CsTenantNetworkRegion」も参照してください](/powershell/module/skype/set-cstenantnetworksite)。

### <a name="define-network-subnets"></a>ネットワーク サブネットを定義する

[New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps)コマンドレットを使用して、ネットワーク サブネットを定義し、ネットワーク サイトに関連付ける。 各ネットワーク サブネットは、1 つのサイトにのみ関連付けできます。

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

この例では、サブネット 192.168.0.0 と Delhi ネットワーク サイトの間と、サブネット 2001:4898:e8:25:844e:926f:85ad:dd8e と、ハイデラネットワーク サイトの間に関連付けを作成します。

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

次の表は、この例で定義されているサブネットを示しています。

||サイト 1 |サイト 2 |
|---------|---------|---------|
|サブネット ID   |    192.168.0.0     |  2001:4898:e8:25:844e:926f:85ad:dd8e     |
|マスク  |     24    |   120      |
|サイト ID  | サイト (Delhi) | サイト 2 (ハイデラバード) |

複数のサブネットの場合は、次のようなスクリプトを使用して CSV ファイルをインポートできます。

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

この例では、CSV ファイルは次のようになります。

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```


[「Set-CsTenantNetworkSubnet」も参照してください](/powershell/module/skype/set-cstenantnetworksubnet)。


### <a name="define-external-subnets-external-trusted-ip-addresses"></a>外部サブネット (外部信頼済み IP アドレス) を定義する

[New-CsTenantTrustedIPAddress](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps)コマンドレットを使用して外部サブネットを定義し、テナントに割り当てる。 テナントの外部サブネットの数に制限はありません。

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

次に例を示します。

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

[「Set-CsTenantTrustedIPAddress」も参照してください](/powershell/module/skype/set-cstenanttrustedipaddress)。

## <a name="related-topics"></a>関連トピック

- [Teams のクラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)
