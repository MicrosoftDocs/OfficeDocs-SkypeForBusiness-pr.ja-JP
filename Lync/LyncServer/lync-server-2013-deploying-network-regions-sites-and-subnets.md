---
title: 'Lync Server 2013: ネットワークの領域、サイト、サブネットの展開'
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
ms.openlocfilehash: 04c39a18147bad3f84bd345ec0a56b606db4cae4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a>Lync Server 2013 でのネットワークのリージョン、サイト、サブネットの展開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-12_

エンタープライズ Voip を展開したら、次のように構成する必要があります。

  - ネットワーク領域

  - ネットワークサイト

  - ネットワークサブネット

<div>

## <a name="define-network-regions"></a>ネットワーク領域を定義する

Lync Server Windows PowerShell コマンド、新しい CsNetworkRegion、または Lync Server コントロールパネルを使用して、ネットワークの領域を定義します。

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

詳細については、「[新しい-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)」を参照してください。

この例では、次の Windows PowerShell コマンドは、このシナリオで定義されたネットワークの領域 (インド) を示しています。

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a>ネットワークサイトを定義する

Lync Server Windows PowerShell コマンド、新しい CsNetworkSite、または Lync Server コントロールパネルを使用して、ネットワークサイトを定義します。

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

詳細については、「[新しい-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)」を参照してください。

この例では、次の表と Lync Server Windows PowerShell コマンドはこのシナリオで定義されたネットワークサイトを示しています。 この表には、場所に基づくルーティングに固有の設定のみが含まれています。

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

Lync Server Windows PowerShell コマンド、新しい-CsNetworkSubnet、または Lync Server コントロールパネルを使用して、ネットワークサブネットを定義し、それらをネットワークサイトに割り当てることができます。

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

詳細については、「[新しい-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。

この例では、次の表と Windows PowerShell コマンドは、このシナリオで定義されたネットワークサイト、ニューデリー、Hyderabad へのネットワークサブネットの割り当てを示しています。 この表には、場所に基づくルーティングに固有の設定のみが含まれています。

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
<td><p>24</p></td>
<td><p>24</p></td>
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


[Lync Server 2013 の場所に基づくルーティングの構成](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

