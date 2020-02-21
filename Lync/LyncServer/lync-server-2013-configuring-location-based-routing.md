---
title: 'Lync Server 2013: 場所に基づくルーティングの構成'
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
ms.openlocfilehash: b88df8bf0b8362a09ea2e5b779b7fa9d789a0a48
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="8426b-102">Lync Server 2013 での場所に基づくルーティングの構成</span><span class="sxs-lookup"><span data-stu-id="8426b-102">Configuring Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8426b-103">_**トピックの最終更新日:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="8426b-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="8426b-104">Lync Server 2013 CU1、場所に基づくルーティングはエンタープライズ Voip の機能です。</span><span class="sxs-lookup"><span data-stu-id="8426b-104">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="8426b-105">場所に基づくルーティングは、通話が Lync Server 2013 CU1 によってルーティングされる方法を制御する通話管理機能です。</span><span class="sxs-lookup"><span data-stu-id="8426b-105">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="8426b-106">Lync の発信者の場所に基づいて通話を PBX または PSTN の宛先にルーティングできるかどうかに関する制限を適用します。</span><span class="sxs-lookup"><span data-stu-id="8426b-106">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="8426b-107">場所に基づくルーティングでは、発信者のネットワークの場所に基づいて通話の承認ルールが PSTN 通話に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8426b-107">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="8426b-108">発信者の場所は、発信者が接続されているネットワークサブネットに関連付けられているネットワークサイトに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="8426b-108">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="8426b-109">場所に基づくルーティングを構成するには、最初にエンタープライズ Voip を展開してから、ネットワーク地域、サイト、およびサブネットを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8426b-109">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="8426b-110">これにより、場所に基づくルーティングを有効にするための基盤が設定されます。</span><span class="sxs-lookup"><span data-stu-id="8426b-110">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="8426b-111">場所に基づくルーティングを展開する前に、まずエンタープライズ Voip を展開し、ネットワーク地域、サイトを構成して、ネットワークサブネットをネットワークサイトに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="8426b-111">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="8426b-112">完了したら、場所に基づくルーティングを構成できます。</span><span class="sxs-lookup"><span data-stu-id="8426b-112">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="8426b-113">ネットワーク地域、サイト、およびサブネットを構成する手順については、「 [Lync Server 2013 での高度なエンタープライズ voip 機能の展開](lync-server-2013-deploying-advanced-enterprise-voice-features.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8426b-113">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="8426b-114">このセクションでは、次の例を使用して、場所に基づくルーティングを構成する手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="8426b-114">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="8426b-115">![エンタープライズ Voip の場所に基づくルーティングの例](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "エンタープライズ Voip の場所に基づくルーティングの例")</span><span class="sxs-lookup"><span data-stu-id="8426b-115">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="8426b-116">次の表は、この例で定義されているユーザーを表しています。</span><span class="sxs-lookup"><span data-stu-id="8426b-116">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8426b-117">エンドポイントの種類</span><span class="sxs-lookup"><span data-stu-id="8426b-117">Endpoint type</span></span></th>
<th><span data-ttu-id="8426b-118">場所</span><span class="sxs-lookup"><span data-stu-id="8426b-118">Location</span></span></th>
<th><span data-ttu-id="8426b-119">ユーザー</span><span class="sxs-lookup"><span data-stu-id="8426b-119">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8426b-120">Lync</span><span class="sxs-lookup"><span data-stu-id="8426b-120">Lync</span></span></p></td>
<td><p><span data-ttu-id="8426b-121">ニューデリー企業オフィス</span><span class="sxs-lookup"><span data-stu-id="8426b-121">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="8426b-122">「DEL-LYNC-1, DEL-LYNC-2, DEL-3」</span><span class="sxs-lookup"><span data-stu-id="8426b-122">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8426b-123">Lync</span><span class="sxs-lookup"><span data-stu-id="8426b-123">Lync</span></span></p></td>
<td><p><span data-ttu-id="8426b-124">Hyderabad 企業オフィス</span><span class="sxs-lookup"><span data-stu-id="8426b-124">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="8426b-125">HYD-1、HYD、HYD (LYNC-3)</span><span class="sxs-lookup"><span data-stu-id="8426b-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8426b-126">Lync</span><span class="sxs-lookup"><span data-stu-id="8426b-126">Lync</span></span></p></td>
<td><p><span data-ttu-id="8426b-127">不明 (つまりホテル)</span><span class="sxs-lookup"><span data-stu-id="8426b-127">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="8426b-128">UNK-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="8426b-128">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8426b-129">PBX</span><span class="sxs-lookup"><span data-stu-id="8426b-129">PBX</span></span></p></td>
<td><p><span data-ttu-id="8426b-130">ニューデリー企業オフィス</span><span class="sxs-lookup"><span data-stu-id="8426b-130">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="8426b-131">DEL-PBX-1、DEL-PBX-2</span><span class="sxs-lookup"><span data-stu-id="8426b-131">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8426b-132">PBX</span><span class="sxs-lookup"><span data-stu-id="8426b-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="8426b-133">Hyderabad 企業オフィス</span><span class="sxs-lookup"><span data-stu-id="8426b-133">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="8426b-134">HYD-1、HYD (PBX)</span><span class="sxs-lookup"><span data-stu-id="8426b-134">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8426b-135">PSTN</span><span class="sxs-lookup"><span data-stu-id="8426b-135">PSTN</span></span></p></td>
<td><p><span data-ttu-id="8426b-136">不明</span><span class="sxs-lookup"><span data-stu-id="8426b-136">Unknown</span></span></p></td>
<td><p><span data-ttu-id="8426b-137">PSTN-1、PSTN-2、PSTN-3</span><span class="sxs-lookup"><span data-stu-id="8426b-137">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="8426b-138">次の表は、この環境例で示されているシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="8426b-138">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8426b-139">System</span><span class="sxs-lookup"><span data-stu-id="8426b-139">System</span></span></th>
<th><span data-ttu-id="8426b-140">場所</span><span class="sxs-lookup"><span data-stu-id="8426b-140">Location</span></span></th>
<th><span data-ttu-id="8426b-141">名前</span><span class="sxs-lookup"><span data-stu-id="8426b-141">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8426b-142">Lync Server 2013 CU1 プール</span><span class="sxs-lookup"><span data-stu-id="8426b-142">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="8426b-143">any</span><span class="sxs-lookup"><span data-stu-id="8426b-143">any</span></span></p></td>
<td><p><span data-ttu-id="8426b-144">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="8426b-144">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8426b-145">Lync Server 2013 CU1、仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="8426b-145">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="8426b-146">any</span><span class="sxs-lookup"><span data-stu-id="8426b-146">any</span></span></p></td>
<td><p><span data-ttu-id="8426b-147">PL1</span><span class="sxs-lookup"><span data-stu-id="8426b-147">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8426b-148">PSTN ゲートウェイ1</span><span class="sxs-lookup"><span data-stu-id="8426b-148">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="8426b-149">デリー</span><span class="sxs-lookup"><span data-stu-id="8426b-149">Delhi</span></span></p></td>
<td><p><span data-ttu-id="8426b-150">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="8426b-150">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8426b-151">PSTN ゲートウェイ2</span><span class="sxs-lookup"><span data-stu-id="8426b-151">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="8426b-152">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="8426b-152">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="8426b-153">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="8426b-153">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8426b-154">PBX 1</span><span class="sxs-lookup"><span data-stu-id="8426b-154">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="8426b-155">デリー</span><span class="sxs-lookup"><span data-stu-id="8426b-155">Delhi</span></span></p></td>
<td><p><span data-ttu-id="8426b-156">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="8426b-156">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8426b-157">PBX 2</span><span class="sxs-lookup"><span data-stu-id="8426b-157">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="8426b-158">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="8426b-158">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="8426b-159">赤-PBX</span><span class="sxs-lookup"><span data-stu-id="8426b-159">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="8426b-160">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8426b-160">In This Section</span></span>

  - [<span data-ttu-id="8426b-161">Lync Server 2013 でのエンタープライズ Voip の構成</span><span class="sxs-lookup"><span data-stu-id="8426b-161">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="8426b-162">Lync Server 2013 でのネットワーク地域、サイト、およびサブネットの展開</span><span class="sxs-lookup"><span data-stu-id="8426b-162">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="8426b-163">Lync Server 2013 での場所に基づくルーティングの有効化</span><span class="sxs-lookup"><span data-stu-id="8426b-163">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8426b-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="8426b-164">See Also</span></span>


[<span data-ttu-id="8426b-165">Lync Server 2013 での高度なエンタープライズ Voip 機能の展開</span><span class="sxs-lookup"><span data-stu-id="8426b-165">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

