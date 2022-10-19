---
title: Microsoft Teams でクラウド音声機能のネットワーク トポロジを管理する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams でクラウド音声機能のネットワーク設定を構成する方法について説明します。
ms.openlocfilehash: a75ce05a29df84bb46cb430016e1a3453e96b64e
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584248"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>Microsoft Teams でクラウド音声機能のネットワーク トポロジを管理する

組織が直接ルーティングまたは[動的緊急通報](configure-dynamic-emergency-calling.md)[用に場所ベースのルーティング](location-based-routing-plan.md)を展開している場合は、Microsoft Teams でこれらのクラウド音声機能で使用するネットワーク設定を構成する必要があります。 ネットワーク設定は、Teams クライアントの場所を決定するために使用され、ネットワークリージョン、ネットワーク サイト、サブネット、信頼された IP アドレスが含まれます。 デプロイするクラウド音声機能と機能に応じて、これらの設定の一部またはすべてを構成します。 これらの用語の詳細については、「 [クラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)」を参照してください。

ネットワーク設定は、Microsoft Teams 管理センターの **[ネットワーク トポロジ**] ページで行うか、Windows PowerShellを使用して構成します。

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでネットワーク設定を構成する

ネットワーク 領域、ネットワーク サイト、サブネットは、[ネットワーク トポロジ] ページの [ **ネットワーク サイト** ] タブ **で** 定義します。 ここでは、ネットワーク サイトの作成または変更、サイトとネットワーク リージョンの関連付け、サイトへのサブネットの関連付け、場所ベースのルーティングの有効化、およびサイトへの緊急ポリシーの割り当てを行うことができます。 また、すべてのサイトでグローバルに使用できるネットワークリージョンを追加することもできます。

#### <a name="add-and-configure-a-network-site"></a>ネットワーク サイトを追加して構成する

1. Microsoft Teams 管理センターの左側のナビゲーションで、 **場所** > **ネットワーク トポロジに** 移動し、[ **ネットワーク サイト** ] タブをクリックします。
2. [ **追加]** をクリックし、サイトの名前と説明を入力します。

    ![[ネットワーク サイトの追加] ページのスクリーンショット。](media/manage-network-topology-add-site.png)

3. サイトをネットワーク リージョンに関連付けるには、[ネットワーク リージョンの **追加]** をクリックし、既存のリージョンを選択するか、[ **追加** ] をクリックしてリージョンを追加し、[ **リンク**] をクリックします。  
4. サイトのLocation-Basedルーティングを有効にするには、[ **場所ベースのルーティング]** をオンにします。
5. サイトに緊急サービス ポリシーを割り当てるには、次のいずれかまたは両方を実行します。

    - 組織で通話プラン、オペレーター接続、またはダイレクト ルーティングを使用している場合は、[ **緊急通話ポリシー**] で目的のポリシーを選択します。
    - 組織がダイレクト ルーティングを展開した場合は、[ **緊急通話ルーティング ポリシー**] で、目的のポリシーを選択します。

6. サブネットをサイトに関連付けるには、[ **サブネット]** の [サブネットの **追加**] をクリックします。 IP バージョン、IP アドレス、ネットワーク範囲を指定し、説明を追加して、[ **適用**] をクリックします。 各サブネットは、特定のサイトに関連付ける必要があります。
7. **[保存]** をクリックします。

#### <a name="modify-a-network-site"></a>ネットワーク サイトを変更する

1. Microsoft Teams 管理センターの左側のナビゲーションで、 **場所** > **ネットワーク トポロジに** 移動し、[ **ネットワーク サイト** ] タブをクリックします。
2. サイト名の左側をクリックしてサイトを選択し、[ **編集]** をクリックします。
3. 必要な変更を加え、[保存] をクリック **します。**

### <a name="manage-external-trusted-ip-addresses"></a>外部信頼済み IP アドレスを管理する

外部の信頼済み IP アドレスは、Microsoft Teams 管理センターの **[ネットワーク トポロジ**] ページの [**信頼された IP**] タブで管理します。 外部信頼済み IP アドレスの数に制限はありません。

#### <a name="add-a-trusted-ip-address"></a>信頼できる IP アドレスを追加する

1. Microsoft Teams 管理センターの左側のナビゲーションで、 **場所** > **ネットワーク トポロジに** 移動し、[ **信頼された IP** ] タブをクリックします。
2. [**新規**] をクリックします。
3. [ **信頼できる IP アドレスの追加]** ウィンドウで、IP バージョン、IP アドレス、ネットワーク範囲を指定し、説明を追加して、[ **適用**] をクリックします。

    ![[信頼できる IP アドレスの追加] ウィンドウのスクリーンショット。](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>信頼された IP アドレスを編集する

1. Microsoft Teams 管理センターの左側のナビゲーションで、 **場所** > **ネットワーク トポロジに** 移動し、[ **信頼された IP** ] タブをクリックします。
2. 左側をクリックして IP アドレスを選択し、[ **編集]** をクリックします。
3. [ **信頼された IP アドレスの編集]** ウィンドウで、必要な変更を行い、[ **適用**] をクリックします。

## <a name="configure-network-settings-using-powershell"></a>PowerShell を使用してネットワーク設定を構成する

このセクションの手順を完了するには、PowerShell コマンドレットに関する知識が必要です。 詳細については、「 [Teams PowerShell の概要](teams-powershell-overview.md)」を参照してください。

### <a name="define-network-regions"></a>ネットワークリージョンを定義する

 [New-CsTenantNetworkRegion](/powershell/module/skype/New-CsTenantNetworkRegion) コマンドレットを使用して、ネットワーク領域を定義します。 RegionID パラメーターは、リージョンの地理を表す論理名であり、依存関係や制限はなく、CentralSite &lt;サイト ID&gt; パラメーターは省略可能であることに注意してください。

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

この例では、インドという名前のネットワーク リージョンを作成します。

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

[Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworkregion) も参照してください。

### <a name="define-network-sites"></a>ネットワーク サイトを定義する

[New-CsTenantNetworkSite](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) コマンドレットを使用して、ネットワーク サイトを定義します。 各ネットワーク サイトは、ネットワーク リージョンに関連付けられている必要があります。

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

この例では、インドリージョンに 2 つの新しいネットワーク サイト (インドのインド) を作成します。

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

次の表は、この例で定義されているネットワーク サイトを示しています。

|&nbsp;|サイト 1 |サイト 2 |
|---------|---------|---------|
|サイト ID    |    サイト 1 (インド)     |  サイト 2 (ハイダラード)       |
|リージョン ID  |     リージョン 1 (インド)    |   リージョン 1 (インド)      |

[Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworksite) も参照してください。

### <a name="define-network-subnets"></a>ネットワーク サブネットを定義する

[New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) コマンドレットを使用して、ネットワーク サブネットを定義し、それらをネットワーク サイトに関連付けます。 各ネットワーク サブネットは、1 つのサイトにのみ関連付けることができます。

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

この例では、サブネット 192.168.0.0 と、Subnet 2001:4898:e8:25:844e:926f:85ad:dd8e と 2001:4898:926f:85ad:dd8e と 2001:4898:8898:85ad:dd8e と 85ad:dd8e の間に関連付けを作成します。

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

次の表は、この例で定義されているサブネットを示しています。

|&nbsp;|サイト 1 |サイト 2 |
|---------|---------|---------|
|サブネット ID   |    192.168.0.0     |  2001:4898:e8:25:844e:926f:85ad:dd8e     |
|マスク  |     24    |   120      |
|サイト ID  | Site (2018 年 10 月) | サイト 2 (ハイダラード) |

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


[Set-CsTenantNetworkSubnet](/powershell/module/skype/set-cstenantnetworksubnet) も参照してください。


### <a name="define-external-subnets-external-trusted-ip-addresses"></a>外部サブネット (外部信頼済み IP アドレス) を定義する

[New-CsTenantTrustedIPAddress](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) コマンドレットを使用して、外部サブネットを定義し、テナントに割り当てます。 テナントの外部サブネットの数に制限はありません。

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

次に例を示します。

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

[Set-CsTenantTrustedIPAddress](/powershell/module/skype/set-cstenanttrustedipaddress) も参照してください。

## <a name="related-topics"></a>関連項目

- [Teams のクラウド音声機能のネットワーク設定](cloud-voice-network-settings.md)
