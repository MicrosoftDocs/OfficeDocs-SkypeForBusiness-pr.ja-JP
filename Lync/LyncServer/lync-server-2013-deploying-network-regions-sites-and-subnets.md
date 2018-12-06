---
title: Lync Server 2013 でのネットワーク領域、サイト、サブネットの展開
TOCTitle: Lync Server 2013 でのネットワーク領域、サイト、サブネットの展開
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994067(v=OCS.15)
ms:contentKeyID: 52056701
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのネットワーク領域、サイト、サブネットの展開

 

_**トピックの最終更新日:** 2015-03-09_

エンタープライズ VoIP の展開後は構成を行う必要があります。

  - ネットワーク地域

  - ネットワーク サイト

  - ネットワーク サブネット

## ネットワーク地域の定義

Lync ServerWindows PowerShell コマンドの New-CsNetworkRegion、または Lync Server コントロール パネルを使用してネットワーク地域を定義します。

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

詳細については、「[New-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegion)」を参照してください。

この例では、次の Windows PowerShell コマンドは、このシナリオで定義されているネットワーク地域 region 1 (India) を示しています。

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"


## ネットワーク サイトの定義

Lync ServerWindows PowerShell コマンドの New-CsNetworkSite または Lync Server コントロール パネルを使用してネットワーク サイトを定義します。

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

詳細については、「[New-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSite)」を参照してください。

この例では、次の表および Lync ServerWindows PowerShell コマンドがこのシナリオで定義されるネットワーク サイトを示しています。わかりやすく説明するために、表に含まれているのは場所に基づくルーティングに固有の設定のみです。

    New-CsNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
    New-CsNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>サイト 1 (Delhi)</th>
<th>サイト 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>サイト ID</p></td>
<td><p>サイト 1 (Delhi)</p></td>
<td><p>サイト 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>地域 ID</p></td>
<td><p>地域 1 (India)</p></td>
<td><p>地域 1 (India)</p></td>
</tr>
</tbody>
</table>



## ネットワーク サブネットの定義

Lync ServerWindows PowerShell コマンドの New-CsNetworkSubnet または Lync Server コントロール パネルを使用してネットワーク サブネットを定義し、ネットワーク サイトに割り当てます。

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

詳細については、「[New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。

この例では、ネットワーク サイト (Delhi および Hyderabad) へのネットワーク サブネットの割り当てを次の表および Windows PowerShell コマンドに示します。わかりやすく説明するために、表に含まれているのは場所に基づくルーティングに固有の設定のみです。

    New-CsNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
    New-CsNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>サイト 1 (Delhi)</th>
<th>サイト 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>サブネット ID</p></td>
<td><p>192.168.0.0</p></td>
<td><p>192.168.1.0</p></td>
</tr>
<tr class="even">
<td><p>マスク</p></td>
<td><p>24</p></td>
<td><p>24</p></td>
</tr>
<tr class="odd">
<td><p>サイト ID</p></td>
<td><p>サイト 1 (Delhi)</p></td>
<td><p>サイト 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>



## 関連項目

#### その他のリソース

[Lync Server 2013 の場所に基づくルーティングの構成](lync-server-2013-configuring-location-based-routing.md)

