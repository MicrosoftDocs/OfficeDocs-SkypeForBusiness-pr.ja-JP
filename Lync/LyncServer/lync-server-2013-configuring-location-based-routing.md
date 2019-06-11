---
title: 'Lync Server 2013: 場所に基づくルーティングの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a682f6b550f982f929a83bc8c2f430e89b9452fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="d452b-102">Lync Server 2013 の場所に基づくルーティングの構成</span><span class="sxs-lookup"><span data-stu-id="d452b-102">Configuring Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d452b-103">_**最終更新日:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="d452b-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="d452b-104">Lync Server 2013 CU1、場所に基づくルーティングはエンタープライズ Voip の機能です。</span><span class="sxs-lookup"><span data-stu-id="d452b-104">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="d452b-105">位置情報に基づくルーティングは、Lync Server 2013 CU1 による通話のルーティング方法を制御する通話管理機能です。</span><span class="sxs-lookup"><span data-stu-id="d452b-105">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="d452b-106">Lync の発信者の所在地に基づいて、通話を PBX または PSTN にルーティングできるかどうかに関する制限を適用します。</span><span class="sxs-lookup"><span data-stu-id="d452b-106">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="d452b-107">位置情報に基づくルーティングは、呼び出し元のネットワークの場所に基づいて、着信の承認規則を PSTN 通話に適用します。</span><span class="sxs-lookup"><span data-stu-id="d452b-107">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="d452b-108">発信者の場所は、発信者が接続されているネットワークサブネットに関連付けられたネットワークサイトに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="d452b-108">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="d452b-109">場所に基づくルーティングを構成するには、最初にエンタープライズボイスを展開してから、ネットワークのリージョン、サイト、サブネットを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d452b-109">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="d452b-110">これにより、位置に基づくルーティングを有効にするための基盤が設定されます。</span><span class="sxs-lookup"><span data-stu-id="d452b-110">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="d452b-111">位置情報に基づくルーティングを展開する前に、まずエンタープライズ Voip を展開し、ネットワークの地域、サイトを構成し、ネットワークのサブネットをネットワークサイトに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="d452b-111">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="d452b-112">完了したら、位置ベースのルーティングを構成できます。</span><span class="sxs-lookup"><span data-stu-id="d452b-112">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="d452b-113">ネットワークの地域、サイト、サブネットを構成する手順については、「 [Lync Server 2013 での高度なエンタープライズ voip 機能の展開](lync-server-2013-deploying-advanced-enterprise-voice-features.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d452b-113">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="d452b-114">このセクションでは、図に示すように、次の例を使用して位置情報に基づくルーティングを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d452b-114">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="d452b-115">![エンタープライズ voip の位置情報に基づくルーティングの例](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "エンタープライズ voip の位置情報に基づくルーティングの例")</span><span class="sxs-lookup"><span data-stu-id="d452b-115">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="d452b-116">次の表は、この例で定義されているユーザーを示しています。</span><span class="sxs-lookup"><span data-stu-id="d452b-116">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d452b-117">エンドポイントの種類</span><span class="sxs-lookup"><span data-stu-id="d452b-117">Endpoint type</span></span></th>
<th><span data-ttu-id="d452b-118">場所</span><span class="sxs-lookup"><span data-stu-id="d452b-118">Location</span></span></th>
<th><span data-ttu-id="d452b-119">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d452b-119">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d452b-120">Lync</span><span class="sxs-lookup"><span data-stu-id="d452b-120">Lync</span></span></p></td>
<td><p><span data-ttu-id="d452b-121">ニューデリーの会社オフィス</span><span class="sxs-lookup"><span data-stu-id="d452b-121">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="d452b-122">DEL-LYNC-1、DEL-LYNC-2、DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="d452b-122">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d452b-123">Lync</span><span class="sxs-lookup"><span data-stu-id="d452b-123">Lync</span></span></p></td>
<td><p><span data-ttu-id="d452b-124">Hyderabad 企業オフィス</span><span class="sxs-lookup"><span data-stu-id="d452b-124">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="d452b-125">HYD-1、HYD、LYNC-2、HYD、LYNC-3</span><span class="sxs-lookup"><span data-stu-id="d452b-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d452b-126">Lync</span><span class="sxs-lookup"><span data-stu-id="d452b-126">Lync</span></span></p></td>
<td><p><span data-ttu-id="d452b-127">不明 (例: ホテル)</span><span class="sxs-lookup"><span data-stu-id="d452b-127">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="d452b-128">UNK-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="d452b-128">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d452b-129">PBX</span><span class="sxs-lookup"><span data-stu-id="d452b-129">PBX</span></span></p></td>
<td><p><span data-ttu-id="d452b-130">ニューデリーの会社オフィス</span><span class="sxs-lookup"><span data-stu-id="d452b-130">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="d452b-131">DELETE-PBX-1、DEL-PBX-2</span><span class="sxs-lookup"><span data-stu-id="d452b-131">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d452b-132">PBX</span><span class="sxs-lookup"><span data-stu-id="d452b-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="d452b-133">Hyderabad 企業オフィス</span><span class="sxs-lookup"><span data-stu-id="d452b-133">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="d452b-134">HYD-1、HYD、PBX-2</span><span class="sxs-lookup"><span data-stu-id="d452b-134">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d452b-135">PSTN</span><span class="sxs-lookup"><span data-stu-id="d452b-135">PSTN</span></span></p></td>
<td><p><span data-ttu-id="d452b-136">未</span><span class="sxs-lookup"><span data-stu-id="d452b-136">Unknown</span></span></p></td>
<td><p><span data-ttu-id="d452b-137">PSTN-1、PSTN-2、PSTN-3</span><span class="sxs-lookup"><span data-stu-id="d452b-137">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="d452b-138">次の表は、この例の環境で示されているシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="d452b-138">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d452b-139">Bios</span><span class="sxs-lookup"><span data-stu-id="d452b-139">System</span></span></th>
<th><span data-ttu-id="d452b-140">場所</span><span class="sxs-lookup"><span data-stu-id="d452b-140">Location</span></span></th>
<th><span data-ttu-id="d452b-141">名前</span><span class="sxs-lookup"><span data-stu-id="d452b-141">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d452b-142">Lync Server 2013 CU1 プール</span><span class="sxs-lookup"><span data-stu-id="d452b-142">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="d452b-143">任意</span><span class="sxs-lookup"><span data-stu-id="d452b-143">any</span></span></p></td>
<td><p><span data-ttu-id="d452b-144">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="d452b-144">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d452b-145">Lync Server 2013 CU1、仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="d452b-145">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="d452b-146">任意</span><span class="sxs-lookup"><span data-stu-id="d452b-146">any</span></span></p></td>
<td><p><span data-ttu-id="d452b-147">MS-PL1</span><span class="sxs-lookup"><span data-stu-id="d452b-147">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d452b-148">PSTN ゲートウェイ1</span><span class="sxs-lookup"><span data-stu-id="d452b-148">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="d452b-149">Delhi</span><span class="sxs-lookup"><span data-stu-id="d452b-149">Delhi</span></span></p></td>
<td><p><span data-ttu-id="d452b-150">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="d452b-150">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d452b-151">PSTN ゲートウェイ2</span><span class="sxs-lookup"><span data-stu-id="d452b-151">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="d452b-152">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="d452b-152">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="d452b-153">HYD</span><span class="sxs-lookup"><span data-stu-id="d452b-153">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d452b-154">PBX 1</span><span class="sxs-lookup"><span data-stu-id="d452b-154">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="d452b-155">Delhi</span><span class="sxs-lookup"><span data-stu-id="d452b-155">Delhi</span></span></p></td>
<td><p><span data-ttu-id="d452b-156">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="d452b-156">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d452b-157">PBX 2</span><span class="sxs-lookup"><span data-stu-id="d452b-157">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="d452b-158">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="d452b-158">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="d452b-159">赤-PBX</span><span class="sxs-lookup"><span data-stu-id="d452b-159">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="d452b-160">このセクション中</span><span class="sxs-lookup"><span data-stu-id="d452b-160">In This Section</span></span>

  - [<span data-ttu-id="d452b-161">Lync Server 2013 でのエンタープライズ Voip の設定</span><span class="sxs-lookup"><span data-stu-id="d452b-161">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="d452b-162">Lync Server 2013 でのネットワークのリージョン、サイト、サブネットの展開</span><span class="sxs-lookup"><span data-stu-id="d452b-162">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="d452b-163">Lync Server 2013 で位置情報に基づくルーティングを有効にする</span><span class="sxs-lookup"><span data-stu-id="d452b-163">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d452b-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="d452b-164">See Also</span></span>


[<span data-ttu-id="d452b-165">Lync Server 2013 での高度なエンタープライズ Voip 機能の展開</span><span class="sxs-lookup"><span data-stu-id="d452b-165">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

