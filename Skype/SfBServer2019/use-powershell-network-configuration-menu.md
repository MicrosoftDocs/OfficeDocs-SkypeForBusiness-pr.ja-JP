---
title: '[ネットワーク構成] メニューのタスクに PowerShell を使用する'
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: '概要: [ネットワークSkype for Business Serverのコマンドレット マッピング] メニューにコントロール パネルを表示します。'
ms.openlocfilehash: aa42ac465ffd72a4aff9c03293124c857e5b712c
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626303"
---
# <a name="network-configuration"></a>ネットワーク構成

この記事では、従来のコントロール パネルの[ネットワーク構成] メニュー項目と同様の結果をコマンドレットを使用してどのように実現できるのかについて説明します。

この記事では、次のサブメニューについて説明します。

- [ネットワーク構成](#network-configuration)
  - [場所のポリシー](#location-policy)
  - [帯域幅ポリシー](#bandwidth-policy)
  - [Region](#region)
  - [サイト](#site)
  - [Subnet](#subnet)
  - [地域リンク](#region-link)
  - [地域ルート](#region-route)

## <a name="location-policy"></a>場所ポリシー

LOCATION **POLICY サブメニュー** は、E9-1-1 の機能に関連する設定を適用するために使用されます。 場所のポリシーには、ユーザーを E9-1-1 に対して有効にするかどうか、および有効にする場合、緊急電話の動作を指定します。

ユーザーが LOCATION **POLICY** で実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessするコマンドレットについて説明します。

---

> **シナリオ 1**: すべての場所ポリシーを一覧表示する

   ![リストの場所ポリシー](./media/location-policy-1.png)

***コマンドレット***

[Get-CsLocationPolicy](/powershell/module/skype/get-cslocationpolicy)

***例***

```powershell
 Get-CsLocationPolicy
```

---

> **シナリオ 2:** 新しい場所ポリシーを作成する

   ![場所ポリシーの作成](./media/location-policy-2.png)

***コマンドレット***

[New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy)  

***例***

```powershell
 New-CsLocationPolicy -Identity site:Redmond -EnhancedEmergencyServicesEnabled $True
```

---

> **シナリオ 3:** 選択した場所ポリシーの詳細を取得する

   ![場所ポリシーの取得](./media/location-policy-3.png)

***コマンドレット***

[Get-CsLocationPolicy](/powershell/module/skype/get-cslocationpolicy)

***例***

```powershell
 Get-CsLocationPolicy -Identity Reno
```

---

> **シナリオ 4**: 選択した場所ポリシーを削除する

   ![場所ポリシーの削除](./media/location-policy-4.png)

***コマンドレット***

[Remove-CsLocationPolicy](/powershell/module/skype/remove-cslocationpolicy)

***例***

```powershell
 Remove-CsLocationPolicy -Identity Reno
```

---

> **シナリオ 5**: 場所ポリシーを更新する

   ![場所の更新ポリシー](./media/location-policy-5.png)

***コマンドレット***

[Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy)

***例***

```powershell
 Set-CsLocationPolicy -Identity site:Redmond -EnhancedEmergencyServicesEnabled $True
```

---

## <a name="bandwidth-policy"></a>帯域幅ポリシー

帯域幅ポリシーは、通話受付管理 (CAC) の一部として、特定のモダリティの帯域幅制限を定義する際に使用します。 (このSkype for Business Server、オーディオとビデオのモダリティにのみ帯域幅の制限を割り当てることができます。このコマンドレットは、これらのポリシーのコンテナー プロファイルを作成します。 コンテナー内の個々のポリシーを定義するには、このコマンドレットを呼び出す際にオーディオとビデオの帯域幅の制限を指定します。

帯域幅ポリシーでユーザーが実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessコマンドレットについて検討します。

---
> **シナリオ 1**: すべての帯域幅ポリシーを一覧表示する

   ![帯域幅ポリシーの一覧表示](./media/bandwidth-policy-1.png)

***コマンドレット***

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile)

***例***

```powershell
 Get-CsNetworkBandwidthPolicyProfile
```

---

> **シナリオ 2:** 新しい帯域幅ポリシーを作成する

   ![新しい帯域幅ポリシー](./media/bandwidth-policy-2.png)

***コマンドレット***

[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/new-csnetworkbandwidthpolicyprofile)  

***例***

```powershell
 New-CsNetworkBandwidthPolicyProfile -Identity LowBWLimits -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400 -VideoBWSessionLimit 500
```

---

> **シナリオ 3:** 選択した帯域幅ポリシーの詳細を取得する

   ![帯域幅ポリシーの取得](./media/bandwidth-policy-3.png)

***コマンドレット***

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile)

***例***

```powershell
 Get-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile
```

---

> **シナリオ 4**: 選択した帯域幅ポリシーを削除する

   ![帯域幅ポリシーの削除](./media/bandwidth-policy-4.png)

***コマンドレット***

[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile)

***例***

```powershell
 Remove-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile
```

---

> **シナリオ 5**: 帯域幅ポリシーの更新

   ![帯域幅ポリシーの更新](./media/bandwidth-policy-5.png)

***コマンドレット***

[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/set-csnetworkbandwidthpolicyprofile)

***例***

```powershell
 Set-CsNetworkBandwidthPolicyProfile -Identity LowBWLimit -VideoBWLimit 2500 -VideoBWSessionLimit 300
```

---

## <a name="region"></a>地域

ネットワーク地域は、複数の地理的な領域にまたがるネットワークのさまざまな部分を相互接続します。 すべてのネットワーク地域は、セントラル サイトと関連付ける必要があります。 管理者は REGIONメニューを使用して、1 つ以上のネットワーク領域に関する情報 (関連付けられた中央サイトや、オーディオおよびビデオ接続に代替パスを許可するかどうかを決定する設定、および地域内のサイトをメディア バイパス構成に関連付ける設定など) を管理できます。

---

> **シナリオ 1**: すべての地域を一覧表示する

   ![リスト領域](./media/network-region-1.png)

***コマンドレット***

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion)

***例***

```powershell
 Get-CsNetworkRegion
```

---

> **シナリオ 2:** 新しい地域を作成する

   ![地域の作成](./media/network-region-2.png)

***コマンドレット***

[New-CsNetworkRegion](/powershell/module/skype/new-csnetworkregion)  

***例***

```powershell
 New-CsNetworkRegion -Identity NorthAmerica -Description "All North American Locations" -CentralSite Redmond-NA-MLS
```

---

> **シナリオ 3:** 選択した地域の詳細を取得する

   ![地域の取得](./media/network-region-3.png)

***コマンドレット***

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion)

***例***

```powershell
 Get-CsNetworkRegion -Identity NorthAmerica
```

---

> **シナリオ 4**: 選択した地域を削除する

   ![地域の削除](./media/network-region-4.png)

***コマンドレット***

[Remove-CsNetworkRegion](/powershell/module/skype/remove-csnetworkregion)

***例***

```powershell
 Remove-CsNetworkRegion -Identity NorthAmerica
```

---

> **シナリオ 5**: 地域を更新する

   ![地域の更新](./media/network-region-5.png)

- **注釈 1 - 結果**

    画像上のこの注釈は、結果、つまり取得および表示されるデータを示します。

    ***コマンドレット***

    [地域からの Get-CsNetworkSite](/powershell/module/skype/get-csnetworksite)

    ***例***

    ```powershell
     Get-CsNetworkSite | Where-Object {$_.NetworkRegionID -eq "AKR"}
    ```

- **注釈 2 - オプション (ユーザーの場合)**

    イメージ上のこの注釈は、ユーザーがネットワーク領域を保存するために実装するオプションを示します。

    [Set-CsNetworkRegion](/powershell/module/skype/set-csnetworkregion)

   ***例***

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -Description "North American Region"
   ```

---

## <a name="site"></a>サイト

ネットワーク サイトは、CAC または E9-1-1 展開の各地域内で構成されるオフィスまたは拠点です。 **SITE** サブメニューは、管理者が設定を追加、削除、または管理するのに役立ちます。

ユーザーが SITE で実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessコマンドレットについて検討します。

---

> **シナリオ 1**: すべてのサイトを一覧表示する

   ![リスト サイト](./media/network-site-1.png)

***コマンドレット***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksite)

***例***

```powershell
 Get-CsNetworkSite
```

---

> **シナリオ 2:** 新しいサイトを作成する

   ![サイトの作成](./media/network-site-2.png)

***コマンドレット***

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksite)  

***例***

```powershell
 New-CsNetworkSite -Identity Vancouver -NetworkRegionID NorthAmerica
```

---

> **シナリオ 3:** 選択したサイトの詳細を取得する

   ![サイトの取得](./media/network-site-3.png)

***コマンドレット***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksite)

***例***

```powershell
 Get-CsNetworkSite -Identity Redmond
```

---

> **シナリオ 4**: 選択したサイトを削除する

   ![サイトの削除](./media/network-site-4.png)

***コマンドレット***

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksite)

***例***

```powershell
 Remove-CsNetworkSite -Identity Vancouver
```

---

> **シナリオ 5**: サイトを更新する

   ![サイトの更新](./media/network-site-5.png)

- **注釈 1 - 結果**

    画像上のこの注釈は、結果、つまり取得および表示されるデータを示します。

    ***コマンドレット***

    [Get-CsNetworkSubnet from Site](/powershell/module/skype/get-csnetworksubnet)

    ***例***

    ```powershell
     Get-CsNetworkSubnet | Where-Object {$_.NetworkSiteID -eq "Vancouver"}
    ```

- **注釈 2 - オプション (ユーザーの場合)**

    イメージ上のこの注釈は、ユーザーがネットワーク サイトを保存するために実装するオプションを示します。

   ***コマンドレット***

   [Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksite)

   ***例***

   ```powershell
    Set-CsNetworkSite -Identity Vancouver - BWPolicyProfileID LowBWLimits
   ```

---

## <a name="subnet"></a>サブネット

管理者は **、SUBNET** サブメニューを使用して、ネットワーク サブネットを作成、更新、管理できます。

SUBNET でユーザーが実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessするコマンドレットについて説明します。

---

> **シナリオ 1**: すべてのサブネットを一覧表示する

   ![サブネットの一覧](./media/network-subnet-1.png)

***コマンドレット***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet)

***例***

```powershell
 Get-CsNetworkSubnet
```

---

> **シナリオ 2:** 新しいサブネットを作成する

   ![サブネットの作成](./media/network-subnet-2.png)

***コマンドレット***

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksubnet)  

***例***

```powershell
 New-CsNetworkSubnet -Identity 172.11.15.0 -MaskBits 24 -NetworkSiteID Vancouver
```

---

> **シナリオ 3:** 選択したサブネットの詳細を取得する

   ![Get Subnet](./media/network-subnet-3.png)

***コマンドレット***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet)

***例***

```powershell
 Get-CsNetworkSubnet -Identity 172.11.15.0
```

---

> **シナリオ 4**: 選択したサブネットを削除する

   ![サブネットの削除](./media/network-subnet-4.png)

***コマンドレット***

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksubnet)

***例***

```powershell
 Remove-CsNetworkSubnet -Identity 172.11.15.0
```

---

> **シナリオ 5**: サブネットを更新する

   ![サブネットの更新](./media/network-subnet-5.png)

***コマンドレット***

[Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksubnet)

***例***

```powershell
 Set-CsNetworkSubnet -Identity 172.11.15.0 -MaskBits 25 -NetworkSiteID Chicago
```

---

## <a name="region-link"></a>地域リンク

ネットワーク内の領域は、物理的な WAN 接続を介してリンクされます。管理者は REGION LINK サブ **メニュー** を使用して、ネットワーク サブネットを作成、更新、管理できます。

REGION **LINK** でユーザーが実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessコマンドレットについて説明します。

---

> **シナリオ 1**: すべての地域リンクを一覧表示する

   ![[地域のリスト] リンク](./media/network-regionlink-1.png)

***コマンドレット***

[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

***例***

```powershell
 Get-CsNetworkRegionLink
```

---

> **シナリオ 2:** 新しい地域リンクを作成する

   ![[地域リンクの作成]](./media/network-regionlink-2.png)

***コマンドレット***

[New-CsNetworkRegionLink](/powershell/module/skype/new-csnetworkregionLink)  

***例***

```powershell
 New-CsNetworkRegionLink -Identity NA_EMEA -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID LowBWLimits
```

---

> **シナリオ 3:** 選択した地域リンクの詳細を取得する

   ![地域リンクの取得](./media/network-regionlink-3.png)

***コマンドレット***

[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

***例***

```powershell
 Get-CsNetworkRegionLink -Identity NA_EMEA
```

---

> **シナリオ 4**: 選択した地域リンクを削除する

   ![[地域の削除] リンク](./media/network-regionlink-4.png)

***コマンドレット***

[Remove-CsNetworkRegionLink](/powershell/module/skype/remove-csnetworkregionLink)

***例***

```powershell
 Remove-CsNetworkRegionLink -Identity NA_EMEA
```

---

> **シナリオ 5**: 地域リンクを更新する

   ![[地域の更新] リンク](./media/network-regionlink-5.png)

***コマンドレット***

[Set-CsNetworkRegionLink](/powershell/module/skype/set-csnetworkregionLink)

***例***

```powershell
 Set-CsNetworkRegionLink -Identity NA_EMEA -BWPolicyProfileID HighBWLimits
```

---

## <a name="region-route"></a>地域ルート

CAC 構成内の各地域から他の各地域にアクセスするいくつかの方法が必要です。 地域のリンクが地域間の接続に対する帯域幅制限を設定し、物理リンクも表す一方、ルートはある地域から別の地域へ接続が通過するリンクされたパスを決定します。 管理者は REGION ROUTE サブ **メニュー** を使用して、これらを作成、更新、および管理できます。

REGION **ROUTE** でユーザーが実行できるさまざまなタスクと、それらのタスクがマップSkype for Businessするコマンドレットについて説明します。

---

> **シナリオ 1**: すべての地域ルートを一覧表示する

   ![地域ルートの一覧](./media/network-regionroute-1.png)

***コマンドレット***

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute)

***例***

```powershell
 Get-CsNetworkInterRegionRoute
```

---

> **シナリオ 2:** 新しい地域ルートを作成する

   ![地域ルートの作成](./media/network-regionroute-2.png)

***コマンドレット***

[New-CsNetworkInterRegionRoute](/powershell/module/skype/new-csnetworkinterregionroute)  

***例***

```powershell
 New-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA_EMEA,EMEA_APAC"
```

---

> **シナリオ 3:** 選択した地域ルートの詳細を取得する

   ![地域ルートの取得](./media/network-regionroute-3.png)

***コマンドレット***

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute)

***例***

```powershell
 Get-CsNetworkInterRegionRoute -Filter *APAC*
```

---

> **シナリオ 4**: 選択した地域ルートを削除する

   ![地域ルートの削除](./media/network-regionroute-4.png)

***コマンドレット***

[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/remove-csnetworkinterregionroute)

***例***

```powershell
 Remove-CsNetworkInterRegionRoute -Identity NA_APAC_Route
```

---

> **シナリオ 5**: 地域ルートを更新する

   ![地域ルートの更新](./media/network-regionroute-5.png)

- **注釈 1 - オプション (ユーザーの場合)**

    画像上のこの注釈は、結果、つまり取得および表示されるデータを示します。

   ***コマンドレット***

   [Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

   ***例***

   ```powershell
   Get-CsNetworkRegionLink
   ```

- **注釈 2 - オプション (ユーザーの場合)**

    イメージ上のこの注釈は、ユーザーがネットワーク地域ルートを保存する方法を実装するためのオプションを示します。

    ***コマンドレット***

   [Set-CsNetworkInterRegionRoute](/powershell/module/skype/set-csnetworkinterregionroute)

   ***例***

   ```powershell
   Set-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionLinkIDs "NA_SA,SA_APAC"
   ```

---
---
