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

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="60c01-102">Lync Server 2013 でのネットワークのリージョン、サイト、サブネットの展開</span><span class="sxs-lookup"><span data-stu-id="60c01-102">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60c01-103">_**最終更新日:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="60c01-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="60c01-104">エンタープライズ Voip を展開したら、次のように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60c01-104">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="60c01-105">ネットワーク領域</span><span class="sxs-lookup"><span data-stu-id="60c01-105">Network regions</span></span>

  - <span data-ttu-id="60c01-106">ネットワークサイト</span><span class="sxs-lookup"><span data-stu-id="60c01-106">Network sites</span></span>

  - <span data-ttu-id="60c01-107">ネットワークサブネット</span><span class="sxs-lookup"><span data-stu-id="60c01-107">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="60c01-108">ネットワーク領域を定義する</span><span class="sxs-lookup"><span data-stu-id="60c01-108">Define Network Regions</span></span>

<span data-ttu-id="60c01-109">Lync Server Windows PowerShell コマンド、新しい CsNetworkRegion、または Lync Server コントロールパネルを使用して、ネットワークの領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="60c01-109">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="60c01-110">詳細については、「[新しい-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60c01-110">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="60c01-111">この例では、次の Windows PowerShell コマンドは、このシナリオで定義されたネットワークの領域 (インド) を示しています。</span><span class="sxs-lookup"><span data-stu-id="60c01-111">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="60c01-112">ネットワークサイトを定義する</span><span class="sxs-lookup"><span data-stu-id="60c01-112">Define Network Sites</span></span>

<span data-ttu-id="60c01-113">Lync Server Windows PowerShell コマンド、新しい CsNetworkSite、または Lync Server コントロールパネルを使用して、ネットワークサイトを定義します。</span><span class="sxs-lookup"><span data-stu-id="60c01-113">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="60c01-114">詳細については、「[新しい-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60c01-114">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="60c01-115">この例では、次の表と Lync Server Windows PowerShell コマンドはこのシナリオで定義されたネットワークサイトを示しています。</span><span class="sxs-lookup"><span data-stu-id="60c01-115">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="60c01-116">この表には、場所に基づくルーティングに固有の設定のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="60c01-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="60c01-117">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="60c01-117">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="60c01-118">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="60c01-118">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60c01-119">サイト ID</span><span class="sxs-lookup"><span data-stu-id="60c01-119">Site ID</span></span></p></td>
<td><p><span data-ttu-id="60c01-120">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="60c01-120">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="60c01-121">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="60c01-121">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60c01-122">地域 ID</span><span class="sxs-lookup"><span data-stu-id="60c01-122">Region ID</span></span></p></td>
<td><p><span data-ttu-id="60c01-123">地域 1 (インド)</span><span class="sxs-lookup"><span data-stu-id="60c01-123">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="60c01-124">地域 1 (インド)</span><span class="sxs-lookup"><span data-stu-id="60c01-124">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="60c01-125">ネットワークサブネットを定義する</span><span class="sxs-lookup"><span data-stu-id="60c01-125">Define Network Subnets</span></span>

<span data-ttu-id="60c01-126">Lync Server Windows PowerShell コマンド、新しい-CsNetworkSubnet、または Lync Server コントロールパネルを使用して、ネットワークサブネットを定義し、それらをネットワークサイトに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="60c01-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="60c01-127">詳細については、「[新しい-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60c01-127">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="60c01-128">この例では、次の表と Windows PowerShell コマンドは、このシナリオで定義されたネットワークサイト、ニューデリー、Hyderabad へのネットワークサブネットの割り当てを示しています。</span><span class="sxs-lookup"><span data-stu-id="60c01-128">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="60c01-129">この表には、場所に基づくルーティングに固有の設定のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="60c01-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="60c01-130">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="60c01-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="60c01-131">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="60c01-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60c01-132">サブネット ID</span><span class="sxs-lookup"><span data-stu-id="60c01-132">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="60c01-133">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="60c01-133">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="60c01-134">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="60c01-134">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60c01-135">Mask</span><span class="sxs-lookup"><span data-stu-id="60c01-135">Mask</span></span></p></td>
<td><p><span data-ttu-id="60c01-136">24</span><span class="sxs-lookup"><span data-stu-id="60c01-136">24</span></span></p></td>
<td><p><span data-ttu-id="60c01-137">24</span><span class="sxs-lookup"><span data-stu-id="60c01-137">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60c01-138">サイト ID</span><span class="sxs-lookup"><span data-stu-id="60c01-138">Site ID</span></span></p></td>
<td><p><span data-ttu-id="60c01-139">サイト 1 (ニューデリー)</span><span class="sxs-lookup"><span data-stu-id="60c01-139">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="60c01-140">サイト 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="60c01-140">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="60c01-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="60c01-141">See Also</span></span>


[<span data-ttu-id="60c01-142">Lync Server 2013 の場所に基づくルーティングの構成</span><span class="sxs-lookup"><span data-stu-id="60c01-142">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

