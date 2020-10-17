---
title: 'Lync Server 2013: Location-Based ルーティングの構成'
description: 'Lync Server 2013: Location-Based ルーティングの構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 080c2a3a82a8714fc35ce882b0c6cb1630552f27
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570883"
---
# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="41dda-103">Lync Server 2013 での Location-Based ルーティングの構成</span><span class="sxs-lookup"><span data-stu-id="41dda-103">Configuring Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41dda-104">_**トピックの最終更新日:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="41dda-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="41dda-105">Lync Server 2013 CU1、Location-Based ルーティングはエンタープライズ Voip の機能です。</span><span class="sxs-lookup"><span data-stu-id="41dda-105">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="41dda-106">Location-Based ルーティングは、Lync Server 2013 CU1 が通話をルーティングする方法を制御する通話管理機能です。</span><span class="sxs-lookup"><span data-stu-id="41dda-106">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="41dda-107">Lync の発信者の場所に基づいて通話を PBX または PSTN の宛先にルーティングできるかどうかに関する制限を適用します。</span><span class="sxs-lookup"><span data-stu-id="41dda-107">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="41dda-108">Location-Based ルーティングは、発信者のネットワークの場所に基づいて通話承認ルールを PSTN 通話に適用します。</span><span class="sxs-lookup"><span data-stu-id="41dda-108">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="41dda-109">発信者の場所は、発信者が接続されているネットワークサブネットに関連付けられているネットワークサイトに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="41dda-109">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="41dda-110">Location-Based ルーティングを構成するには、最初にエンタープライズ Voip を展開してから、ネットワーク地域、サイト、およびサブネットを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41dda-110">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="41dda-111">これにより Location-Based ルーティングを有効にするための基盤が設定されます。</span><span class="sxs-lookup"><span data-stu-id="41dda-111">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="41dda-112">Location-Based ルーティングを展開する前に、まずエンタープライズ Voip を展開し、ネットワーク地域、サイトを構成し、ネットワークサブネットをネットワークサイトに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="41dda-112">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="41dda-113">完了したら、Location-Based ルーティングを構成できます。</span><span class="sxs-lookup"><span data-stu-id="41dda-113">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="41dda-114">ネットワーク地域、サイト、およびサブネットを構成する手順については、「 [Lync Server 2013 での高度なエンタープライズ voip 機能の展開](lync-server-2013-deploying-advanced-enterprise-voice-features.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41dda-114">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="41dda-115">このセクションでは、次の例を使用して Location-Based ルーティングを構成する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="41dda-115">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="41dda-116">![エンタープライズ Voip の場所に基づくルーティングの例](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "エンタープライズ Voip の場所に基づくルーティングの例")</span><span class="sxs-lookup"><span data-stu-id="41dda-116">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="41dda-117">次の表は、この例で定義されているユーザーを表しています。</span><span class="sxs-lookup"><span data-stu-id="41dda-117">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41dda-118">エンドポイントの種類</span><span class="sxs-lookup"><span data-stu-id="41dda-118">Endpoint type</span></span></th>
<th><span data-ttu-id="41dda-119">場所</span><span class="sxs-lookup"><span data-stu-id="41dda-119">Location</span></span></th>
<th><span data-ttu-id="41dda-120">ユーザー</span><span class="sxs-lookup"><span data-stu-id="41dda-120">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41dda-121">Lync</span><span class="sxs-lookup"><span data-stu-id="41dda-121">Lync</span></span></p></td>
<td><p><span data-ttu-id="41dda-122">ニューデリー企業オフィス</span><span class="sxs-lookup"><span data-stu-id="41dda-122">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="41dda-123">「DEL-LYNC-1, DEL-LYNC-2, DEL-3」</span><span class="sxs-lookup"><span data-stu-id="41dda-123">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41dda-124">Lync</span><span class="sxs-lookup"><span data-stu-id="41dda-124">Lync</span></span></p></td>
<td><p><span data-ttu-id="41dda-125">Hyderabad 企業オフィス</span><span class="sxs-lookup"><span data-stu-id="41dda-125">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="41dda-126">HYD-1、HYD、HYD (LYNC-3)</span><span class="sxs-lookup"><span data-stu-id="41dda-126">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41dda-127">Lync</span><span class="sxs-lookup"><span data-stu-id="41dda-127">Lync</span></span></p></td>
<td><p><span data-ttu-id="41dda-128">不明 (つまりホテル)</span><span class="sxs-lookup"><span data-stu-id="41dda-128">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="41dda-129">UNK-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="41dda-129">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41dda-130">PBX</span><span class="sxs-lookup"><span data-stu-id="41dda-130">PBX</span></span></p></td>
<td><p><span data-ttu-id="41dda-131">ニューデリー企業オフィス</span><span class="sxs-lookup"><span data-stu-id="41dda-131">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="41dda-132">DEL-PBX-1、DEL-PBX-2</span><span class="sxs-lookup"><span data-stu-id="41dda-132">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41dda-133">PBX</span><span class="sxs-lookup"><span data-stu-id="41dda-133">PBX</span></span></p></td>
<td><p><span data-ttu-id="41dda-134">Hyderabad 企業オフィス</span><span class="sxs-lookup"><span data-stu-id="41dda-134">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="41dda-135">HYD-1、HYD (PBX)</span><span class="sxs-lookup"><span data-stu-id="41dda-135">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41dda-136">PSTN</span><span class="sxs-lookup"><span data-stu-id="41dda-136">PSTN</span></span></p></td>
<td><p><span data-ttu-id="41dda-137">不明</span><span class="sxs-lookup"><span data-stu-id="41dda-137">Unknown</span></span></p></td>
<td><p><span data-ttu-id="41dda-138">PSTN-1、PSTN-2、PSTN-3</span><span class="sxs-lookup"><span data-stu-id="41dda-138">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="41dda-139">次の表は、この環境例で示されているシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="41dda-139">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41dda-140">System</span><span class="sxs-lookup"><span data-stu-id="41dda-140">System</span></span></th>
<th><span data-ttu-id="41dda-141">場所</span><span class="sxs-lookup"><span data-stu-id="41dda-141">Location</span></span></th>
<th><span data-ttu-id="41dda-142">名前</span><span class="sxs-lookup"><span data-stu-id="41dda-142">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41dda-143">Lync Server 2013 CU1 プール</span><span class="sxs-lookup"><span data-stu-id="41dda-143">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="41dda-144">任意</span><span class="sxs-lookup"><span data-stu-id="41dda-144">any</span></span></p></td>
<td><p><span data-ttu-id="41dda-145">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="41dda-145">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41dda-146">Lync Server 2013 CU1、仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="41dda-146">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="41dda-147">任意</span><span class="sxs-lookup"><span data-stu-id="41dda-147">any</span></span></p></td>
<td><p><span data-ttu-id="41dda-148">PL1</span><span class="sxs-lookup"><span data-stu-id="41dda-148">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41dda-149">PSTN ゲートウェイ1</span><span class="sxs-lookup"><span data-stu-id="41dda-149">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="41dda-150">デリー</span><span class="sxs-lookup"><span data-stu-id="41dda-150">Delhi</span></span></p></td>
<td><p><span data-ttu-id="41dda-151">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="41dda-151">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41dda-152">PSTN ゲートウェイ2</span><span class="sxs-lookup"><span data-stu-id="41dda-152">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="41dda-153">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="41dda-153">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="41dda-154">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="41dda-154">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41dda-155">PBX 1</span><span class="sxs-lookup"><span data-stu-id="41dda-155">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="41dda-156">デリー</span><span class="sxs-lookup"><span data-stu-id="41dda-156">Delhi</span></span></p></td>
<td><p><span data-ttu-id="41dda-157">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="41dda-157">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41dda-158">PBX 2</span><span class="sxs-lookup"><span data-stu-id="41dda-158">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="41dda-159">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="41dda-159">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="41dda-160">赤-PBX</span><span class="sxs-lookup"><span data-stu-id="41dda-160">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="41dda-161">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="41dda-161">In This Section</span></span>

  - [<span data-ttu-id="41dda-162">Lync Server 2013 でのエンタープライズ Voip の構成</span><span class="sxs-lookup"><span data-stu-id="41dda-162">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="41dda-163">Lync Server 2013 でのネットワーク地域、サイト、およびサブネットの展開</span><span class="sxs-lookup"><span data-stu-id="41dda-163">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="41dda-164">Lync Server 2013 での Location-Based ルーティングの有効化</span><span class="sxs-lookup"><span data-stu-id="41dda-164">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="41dda-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="41dda-165">See Also</span></span>


[<span data-ttu-id="41dda-166">Lync Server 2013 での高度なエンタープライズ Voip 機能の展開</span><span class="sxs-lookup"><span data-stu-id="41dda-166">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

