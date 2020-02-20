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
ms.openlocfilehash: eb1409213e2ba40936743e604af79d1fe564530c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="5b21f-102">Lync Server 2013 でのネットワーク地域、サイト、およびサブネットの展開</span><span class="sxs-lookup"><span data-stu-id="5b21f-102">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b21f-103">_**トピックの最終更新日:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="5b21f-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="5b21f-104">エンタープライズ Voip を展開したら、次の構成を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b21f-104">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="5b21f-105">ネットワーク地域</span><span class="sxs-lookup"><span data-stu-id="5b21f-105">Network regions</span></span>

  - <span data-ttu-id="5b21f-106">ネットワークサイト</span><span class="sxs-lookup"><span data-stu-id="5b21f-106">Network sites</span></span>

  - <span data-ttu-id="5b21f-107">ネットワーク サブネット</span><span class="sxs-lookup"><span data-stu-id="5b21f-107">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="5b21f-108">ネットワーク地域の定義</span><span class="sxs-lookup"><span data-stu-id="5b21f-108">Define Network Regions</span></span>

<span data-ttu-id="5b21f-109">Lync Server Windows PowerShell コマンド、新しい-CsNetworkRegion、または Lync Server コントロールパネルを使用して、ネットワーク地域を定義します。</span><span class="sxs-lookup"><span data-stu-id="5b21f-109">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="5b21f-110">詳細については、「 [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b21f-110">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="5b21f-111">この例では、次の Windows PowerShell コマンドは、このシナリオで定義されたネットワーク地域 (インド) を示しています。</span><span class="sxs-lookup"><span data-stu-id="5b21f-111">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="5b21f-112">ネットワークサイトの定義</span><span class="sxs-lookup"><span data-stu-id="5b21f-112">Define Network Sites</span></span>

<span data-ttu-id="5b21f-113">Lync Server Windows PowerShell コマンド、新しい-CsNetworkSite、または Lync Server コントロールパネルを使用して、ネットワークサイトを定義します。</span><span class="sxs-lookup"><span data-stu-id="5b21f-113">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="5b21f-114">詳細については、「 [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b21f-114">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="5b21f-115">この例では、次の表および Lync Server Windows PowerShell コマンドは、このシナリオで定義されているネットワークサイトを示しています。</span><span class="sxs-lookup"><span data-stu-id="5b21f-115">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="5b21f-116">説明のため、表には場所に基づいたルーティングに固有の設定のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b21f-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="5b21f-117">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="5b21f-117">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="5b21f-118">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="5b21f-118">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b21f-119">サイト ID</span><span class="sxs-lookup"><span data-stu-id="5b21f-119">Site ID</span></span></p></td>
<td><p><span data-ttu-id="5b21f-120">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="5b21f-120">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="5b21f-121">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="5b21f-121">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b21f-122">地域 ID</span><span class="sxs-lookup"><span data-stu-id="5b21f-122">Region ID</span></span></p></td>
<td><p><span data-ttu-id="5b21f-123">地域 1 (インド)</span><span class="sxs-lookup"><span data-stu-id="5b21f-123">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="5b21f-124">地域 1 (インド)</span><span class="sxs-lookup"><span data-stu-id="5b21f-124">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="5b21f-125">ネットワークサブネットを定義する</span><span class="sxs-lookup"><span data-stu-id="5b21f-125">Define Network Subnets</span></span>

<span data-ttu-id="5b21f-126">Lync Server Windows PowerShell コマンド、新しい-CsNetworkSubnet、または Lync Server コントロールパネルを使用して、ネットワークサブネットを定義し、それらをネットワークサイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5b21f-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="5b21f-127">詳細については、「 [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b21f-127">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="5b21f-128">この例では、次の表および Windows PowerShell コマンドを使用して、このシナリオで定義されているネットワークサイト Hyderabad、ニューデリー、およびへのネットワークサブネットの割り当てを示しています。</span><span class="sxs-lookup"><span data-stu-id="5b21f-128">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="5b21f-129">説明のため、表には場所に基づいたルーティングに固有の設定のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b21f-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="5b21f-130">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="5b21f-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="5b21f-131">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="5b21f-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b21f-132">サブネット ID</span><span class="sxs-lookup"><span data-stu-id="5b21f-132">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="5b21f-133">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="5b21f-133">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="5b21f-134">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="5b21f-134">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b21f-135">Mask</span><span class="sxs-lookup"><span data-stu-id="5b21f-135">Mask</span></span></p></td>
<td><p><span data-ttu-id="5b21f-136">ソケット</span><span class="sxs-lookup"><span data-stu-id="5b21f-136">24</span></span></p></td>
<td><p><span data-ttu-id="5b21f-137">ソケット</span><span class="sxs-lookup"><span data-stu-id="5b21f-137">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b21f-138">サイト ID</span><span class="sxs-lookup"><span data-stu-id="5b21f-138">Site ID</span></span></p></td>
<td><p><span data-ttu-id="5b21f-139">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="5b21f-139">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="5b21f-140">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="5b21f-140">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5b21f-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b21f-141">See Also</span></span>


[<span data-ttu-id="5b21f-142">Lync Server 2013 での場所に基づくルーティングの構成</span><span class="sxs-lookup"><span data-stu-id="5b21f-142">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

