---
title: Microsoft Teams でクラウド音声機能のネットワークトポロジを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams でクラウド音声機能のネットワーク設定を構成する方法について説明します。
ms.openlocfilehash: 21d47b5b2fae0b22ea585168acdce4a5e25af2ea
ms.sourcegitcommit: 7631af666ae439cc85f1dae8955653a67170cf20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "48304581"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>Microsoft Teams でクラウド音声機能のネットワークトポロジを管理する

組織で、ダイレクトルーティングまたは[動的な緊急通話](configure-dynamic-emergency-calling.md)[のための位置情報に基づくルーティング](location-based-routing-plan.md)を展開している場合は、Microsoft Teams でこれらのクラウド音声機能を使用するためのネットワーク設定を構成する必要があります。 [ネットワーク設定] は、Teams クライアントの場所を決定するために使用され、ネットワークの領域、ネットワークサイト、サブネット、および信頼された IP アドレスを含みます。 展開しているクラウドの音声機能と機能に応じて、これらの設定の一部またはすべてを構成します。 これらの用語の詳細については、「 [クラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)」を参照してください。

ネットワーク設定は、Microsoft Teams 管理センターの [ **ネットワークトポロジ** ] ページ、または Windows PowerShell を使用して構成します。

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでネットワーク設定を構成する

[!INCLUDE [preview-feature](includes/preview-feature.md)]

ネットワーク**トポロジ**ページの [**ネットワークサイト**] タブで、ネットワーク領域、ネットワークサイト、サブネットを定義します。 ここでは、ネットワークサイトを作成または変更し、ネットワーク領域にサイトを関連付け、サブネットをサイトに関連付け、場所に基づくルーティングを有効にして、サイトに緊急ポリシーを割り当てることができます。 また、すべてのサイトでグローバルに使用できるネットワーク領域を追加することもできます。

#### <a name="add-and-configure-a-network-site"></a>ネットワークサイトを追加および構成する

1. Microsoft Teams 管理センターの左のナビゲーションで、[**場所**のネットワークトポロジ] に移動し、[  >  **Network topology****ネットワークサイト**] タブをクリックします。
2. [ **追加**] をクリックして、サイトの名前と説明を入力します。

    ![[ネットワークサイトの追加] ページのスクリーンショット](media/manage-network-topology-add-site.png)

3. ネットワーク領域にサイトを関連付けるには、[ **ネットワーク領域の追加**] をクリックし、既存の地域を選択するか、[ **追加** ] をクリックして地域を追加し、[ **リンク**] をクリックします。  
4. サイトの位置情報に基づくルーティングを有効にするには、 **場所に基づくルーティング**を有効にします。
5. サイトに緊急サービスポリシーを割り当てるには、次のいずれか、または両方の操作を行います。

    - 組織で通話プランまたは展開された電話システムのダイレクトルーティングを使用している場合は、[ **緊急通話ポリシー**] で、目的のポリシーを選びます。
    - 組織で電話システムのダイレクトルーティングを展開している場合は、[ **緊急着信ルーティングポリシー**] で、目的のポリシーを選びます。

6. サブネットをサイトに関連付けるには、[ **サブ**ネット] で [ **サブネットの追加**] をクリックします。 IP のバージョン、IP アドレス、ネットワークの範囲を指定し、説明を追加して、[ **適用**] をクリックします。 各サブネットは、特定のサイトに関連付けられている必要があります。
7. [**保存**] をクリックします。

#### <a name="modify-a-network-site"></a>ネットワークサイトを変更する

1. Microsoft Teams 管理センターの左のナビゲーションで、[**場所**のネットワークトポロジ] に移動し、[  >  **Network topology****ネットワークサイト**] タブをクリックします。
2. サイト名の左側をクリックして、サイトを選択し、[ **編集**] をクリックします。
3. 必要な変更を加えて、[保存] をクリックし **ます。**

### <a name="manage-external-trusted-ip-addresses"></a>外部の信頼できる IP アドレスを管理する

外部の信頼できる IP アドレスは、Microsoft Teams 管理センターの**ネットワークトポロジ**ページの [**信頼済み**ip] タブで管理します。 外部の信頼済み IP アドレスは無制限に追加することができます。

#### <a name="add-a-trusted-ip-address"></a>信頼できる IP アドレスを追加する

1. Microsoft Teams 管理センターの左のナビゲーションで、[**場所**のネットワークトポロジ] に移動し、[  >  **Network topology****信頼さ**れている ip] タブをクリックします。
2. [**新規**] をクリックします。
3. [ **信頼できる ip アドレスの追加** ] ウィンドウで、ip のバージョン、ip アドレス、ネットワークの範囲を指定し、説明を追加して、[ **適用**] をクリックします。

    ![[信頼できる IP アドレスの追加] ウィンドウのスクリーンショット](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>信頼できる IP アドレスを編集する

1. Microsoft Teams 管理センターの左のナビゲーションで、[**場所**のネットワークトポロジ] に移動し、[  >  **Network topology****信頼さ**れている ip] タブをクリックします。
2. [IP アドレス] の左側をクリックして選び、[ **編集**] をクリックします。
3. [ **信頼できる IP アドレスの編集** ] ウィンドウで、必要な変更を行い、[ **適用**] をクリックします。

## <a name="configure-network-settings-using-powershell"></a>PowerShell を使用してネットワーク設定を構成する

このセクションの手順を実行するには、PowerShell コマンドレットについて理解している必要があります。 詳細については、「 [Teams PowerShell の概要](teams-powershell-overview.md)」を参照してください。

### <a name="define-network-regions"></a>ネットワーク領域を定義する

 ネットワーク領域を定義するには、 [CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) コマンドレットを使用します。 RegionID パラメーターは、領域の地理を表す論理名であり、依存関係または制限がないため、CentralSite &lt; SITE ID &gt; パラメーターは省略可能であることに注意してください。

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

この例では、インドという名前のネットワーク領域を作成します。
```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

「 [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion)」も参照してください。

### <a name="define-network-sites"></a>ネットワークサイトを定義する

ネットワークサイトを定義するには、 [CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) コマンドレットを使用します。 各ネットワークサイトは、ネットワーク領域に関連付けられている必要があります。

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

この例では、インド地域に2つの新しいネットワークサイト、ニューデリーと Hyderabad を作成します。

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

次の表は、この例で定義されているネットワークサイトを示しています。

||サイト1 |サイト2 |
|---------|---------|---------|
|サイト ID    |    サイト 1 (ニューデリー)     |  サイト 2 (Hyderabad)       |
|地域 ID  |     地域 1 (インド)    |   地域 1 (インド)      |

「 [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite)」も参照してください。

### <a name="define-network-subnets"></a>ネットワークサブネットを定義する

ネットワークサブネットを定義してネットワークサイトに関連付けるには、 [CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) コマンドレットを使用します。 各ネットワークサブネットは、1つのサイトにのみ関連付けることができます。

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

この例では、サブネット192.168.0.0 と、ニューデリーネットワークサイトと subnet 2001: 4898: 844e: 926f: 85ad: dd8e と Hyderabad ネットワークサイト間の関連付けを作成します。

```PowerShell
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

「 [Set-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet)」も参照してください。

### <a name="define-external-subnets-external-trusted-ip-addresses"></a>外部のサブネット (外部の信頼できる IP アドレス) を定義する

[CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps)コマンドレットを使用して外部サブネットを定義し、それをテナントに割り当てます。 テナントに対して無制限の数の外部サブネットを定義できます。

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

次に例を示します。

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

「 [Set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress)」も参照してください。

## <a name="related-topics"></a>関連項目

- [Teams でのクラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)
