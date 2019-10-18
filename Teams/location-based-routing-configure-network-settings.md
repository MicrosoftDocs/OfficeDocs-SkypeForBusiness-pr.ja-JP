---
title: 場所に基づくルーティングのネットワーク設定を構成する
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: ダイレクトルーティングの位置情報に基づくルーティング用に、ネットワークの領域、サイト、サブネットを作成してセットアップする方法について説明します。
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240bbce48452edf505a61830891d0fcd6a6d199d
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570701"
---
# <a name="configure-network-settings-for-location-based-routing"></a>場所に基づくルーティングのネットワーク設定を構成する

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

まだインストールしていない場合は、「[位置情報に基づくルーティングを計画](location-based-routing-plan.md)する」を参照して、場所に基づくルーティングのネットワーク設定を構成する前に実行する必要があるその他の手順を確認してください。

この記事では、場所に基づくルーティングのネットワーク設定を構成する方法について説明します。 組織で電話システムの直接ルーティングを展開した後、次の手順では、ネットワーク領域、ネットワークサイト、ネットワークサブネットを作成してセットアップします。 この記事の手順を実行するには、PowerShell コマンドレットについて理解している必要があります。 詳細については、「 [Teams PowerShell の概要](teams-powershell-overview.md)」を参照してください。

## <a name="define-network-regions"></a>ネットワーク領域を定義する
 ネットワーク領域は、ネットワークのさまざまな部分を複数の地域で相互接続します。 ネットワーク領域を定義するには、 [CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps)コマンドレットを使用します。 RegionID パラメーターは、領域の地理を表す論理名であり、依存関係または制限がないため、CentralSite &lt;site ID&gt;パラメーターは省略可能であることに注意してください。 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

この例では、インドという名前のネットワーク領域を作成します。 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a>ネットワークサイトを定義する

ネットワークサイトを定義するには、 [CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps)コマンドレットを使用します。 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
この例では、インド地域に2つの新しいネットワークサイト、ニューデリーと Hyderabad を作成します。 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
次の表は、この例で定義されているネットワークサイトを示しています。 

||サイト1 |サイト2 |
|---------|---------|---------|
|サイト ID    |    サイト 1 (ニューデリー)     |  サイト 2 (Hyderabad)       |
|地域 ID  |     地域 1 (インド)    |   地域 1 (インド)      |

## <a name="define-network-subnets"></a>ネットワークサブネットを定義する

ネットワークサブネットを定義してネットワークサイトに関連付けるには、 [CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps)コマンドレットを使用します。 各内部サブネットは、1つのサイトにのみ関連付けることができます。 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
この例では、サブネット192.168.0.0 と、ニューデリーネットワークサイトと subnet 2001: 4898: 844e: 926f: 85ad: dd8e と Hyderabad ネットワークサイト間の関連付けを作成します。
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad" 
```
次の表は、この例で定義されているサブネットを示しています。 

||サイト1 |サイト2 |
|---------|---------|---------|
|サブネット ID   |    192.168.0.0     |  2001: 4898: e8:25: 844e: 926f: 85ad: dd8e     |
|Mask  |     24    |   120      |
|サイト ID  | サイト (ニューデリー) | サイト 2 (Hyderabad) |

複数のサブネットの場合は、次のようなスクリプトを使用して CSV ファイルをインポートできます。
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
この例では、CSV ファイルは次のようになります。
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a>外部サブネットを定義する
[CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps)コマンドレットを使用して外部サブネットを定義し、それをテナントに割り当てます。 1つのテナントに対して無制限の数のサブネットを定義できます。 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
次に例を示します。
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a>次の手順
「[ダイレクトルーティングで位置情報に基づくルーティングを有効](location-based-routing-enable.md)にする」に進みます。

### <a name="related-topics"></a>関連項目
- [ダイレクト ルーティングの場所に基づくルーティングを計画する](location-based-routing-plan.md)
- [場所に基づくルーティングの用語集](location-based-routing-terminology.md)
