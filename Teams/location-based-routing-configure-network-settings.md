---
title: 場所に基づくルーティングのネットワーク設定を構成する
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: 作成し、直接ルーティングの場所ベースのルーティング ネットワーク領域、サイト、およびサブネットを設定する方法について説明します。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 60ed4b1c69f2b6495e21fe28653b19ca905dfc6c
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "30353443"
---
# <a name="configure-network-settings-for-location-based-routing"></a>場所に基づくルーティングのネットワーク設定を構成する

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

まだためには、他の手順を確認するのには[Plan Location-Based が直接ルーティングのルーティング](location-based-routing-plan.md)を読み取る場合は、場所ベースのルーティングのネットワーク設定を展開する前に実行する必要があります。

この資料では、場所ベースのルーティングのネットワーク設定を構成する方法について説明します。 組織の電話システムの直接のルーティングを展開した後次の手順は、ネットワーク地域、ネットワーク サイト、およびネットワーク サブネットを作成して設定します。 この資料の手順を完了するには、PowerShell コマンドレットをある程度必要があります。 詳細については、[チームの PowerShell の概要](teams-powershell-overview.md)を参照してください。

## <a name="define-network-regions"></a>ネットワークの領域を定義します。
 ネットワークの領域は、複数の地理的な分野にわたって、ネットワークのさまざまな部分を相互接続します。 使用して、``New-CsTenantNetworkRegion``ネットワークの領域を定義する PowerShell コマンドレットです。 注意して、``RegionID``パラメーターは、論理名を地域の地理的な位置を表し、依存関係または制約を持たないと、``CentralSite <site ID>``パラメーターは省略可能です。 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

この例では、インドをという名前のネットワーク領域を作成します。 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a>ネットワークのサイトを定義します。

使用して、``New-CsTenantNetworkSite``ネットワーク サイトを定義するための PowerShell コマンドレットです。 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
この例では、2 つの新しいネットワーク サイト、デリーおよび Hyderabad、インドの領域に作成します。 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
次の表は、次の使用例で定義されているネットワークのサイトを示しています。 

||サイト 1 |サイト 2 |
|---------|---------|---------|
|サイト ID    |    サイト 1 (デリー)     |  サイト 2 (Hyderabad)       |
|地域 ID  |     領域 1 (インド)    |   領域 1 (インド)      |

## <a name="define-network-subnets"></a>ネットワークのサブネットを定義します。

使用して、``New-CsTenantNetworkSubnet``コマンドレットには、ネットワークのサブネットを定義し、ネットワーク サイトに関連付けます。 各内部のサブネットは、1 つのサイトに関連付けられているのみできます。 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
この例では、サブネット 192.168.0.0 とサイト間で、デリー ネットワークとサブネット 192.168.1.0 と Hyderabad のネットワーク サイトとの間の関連付けを作成します。
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad" 
```
次の表は、次の使用例で定義されているサブネットを示しています。 

||サイト 1 |サイト 2 |
|---------|---------|---------|
|サブネット ID   |    192.168.0.0     |  192.168.1.0     |
|マスク  |     24    |   24      |
|サイト ID  | サイト (デリー) | サイト 2 (Hyderabad) |

複数のサブネットに次のようなスクリプトを使用して CSV ファイルをインポートできます。
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
この例では、CSV ファイル次のようにします。
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a>外部サブネットを定義します。
使用して、``New-CsTenantTrustedIPAddress``コマンドレットには、外部のサブネットを定義し、テナントに割り当てます。 テナントの無制限の数のサブネットを定義できます。 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
次に例を示します。
```
New-CsTenantTrustedIPAddress -IPAddress 167.220.2.206 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a>次の手順
[直接ルーティングのための場所ベースのルーティングを有効にするの](location-based-routing-enable.md)に移動します。

### <a name="related-topics"></a>関連トピック
- [ダイレクト ルーティングの場所に基づくルーティングを計画する](location-based-routing-plan.md)
- [場所に基づくルーティングの用語集](location-based-routing-terminology.md)
