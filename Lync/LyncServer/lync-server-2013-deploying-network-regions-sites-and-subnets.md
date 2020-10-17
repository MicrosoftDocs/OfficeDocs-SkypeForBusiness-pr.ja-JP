---
title: 'Lync Server 2013: ネットワーク地域、サイト、およびサブネットの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b95d9f7e38e3169474aee33a3004b388c0b13f14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531150"
---
# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a>Lync Server 2013 でのネットワーク地域、サイト、およびサブネットの展開

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-12_

エンタープライズ Voip を展開したら、次の構成を行う必要があります。

  - ネットワーク地域

  - ネットワークサイト

  - ネットワーク サブネット

<div>

## <a name="define-network-regions"></a>ネットワーク地域の定義

Lync Server Windows PowerShell コマンド、新しい-CsNetworkRegion、または Lync Server コントロールパネルを使用して、ネットワーク地域を定義します。

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

詳細については、「 [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)」を参照してください。

この例では、次の Windows PowerShell コマンドは、このシナリオで定義されたネットワーク地域 (インド) を示しています。

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a>ネットワークサイトの定義

Lync Server Windows PowerShell コマンド、新しい-CsNetworkSite、または Lync Server コントロールパネルを使用して、ネットワークサイトを定義します。

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

詳細については、「 [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)」を参照してください。

この例では、次の表および Lync Server Windows PowerShell コマンドは、このシナリオで定義されているネットワークサイトを示しています。 説明のために、Location-Based ルーティングに固有の設定のみが表に含まれています。

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
<th>サイト 1 (ニューデリー)</th>
<th>サイト 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>サイト ID</p></td>
<td><p>サイト 1 (ニューデリー)</p></td>
<td><p>サイト 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>地域 ID</p></td>
<td><p>地域 1 (インド)</p></td>
<td><p>地域 1 (インド)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a>ネットワークサブネットを定義する

Lync Server Windows PowerShell コマンド、新しい-CsNetworkSubnet、または Lync Server コントロールパネルを使用して、ネットワークサブネットを定義し、それらをネットワークサイトに割り当てます。

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

詳細については、「 [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。

この例では、次の表および Windows PowerShell コマンドを使用して、このシナリオで定義されているネットワークサイト Hyderabad、ニューデリー、およびへのネットワークサブネットの割り当てを示しています。 説明のために、Location-Based ルーティングに固有の設定のみが表に含まれています。

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
<th>サイト 1 (ニューデリー)</th>
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
<td><p>Mask</p></td>
<td><p>ソケット</p></td>
<td><p>ソケット</p></td>
</tr>
<tr class="odd">
<td><p>サイト ID</p></td>
<td><p>サイト 1 (ニューデリー)</p></td>
<td><p>サイト 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での Location-Based ルーティングの構成](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

