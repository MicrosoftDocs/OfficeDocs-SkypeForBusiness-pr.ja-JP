---
title: 'Lync Server 2013: フェールオーバールートの構成'
description: 'Lync Server 2013: フェールオーバールートの構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7cfc45276931685a2d42103b1b7f1d5015dcd7e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560493"
---
# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="44e60-103">Lync Server 2013 でのフェールオーバールートの構成</span><span class="sxs-lookup"><span data-stu-id="44e60-103">Configuring a failover route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44e60-104">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="44e60-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="44e60-p101">次の例では、Dallas-GW1 がメンテナンスで停止したり、利用できなくなったりしたときに使用するフェールオーバー ルートの定義方法を示します。必要な構成の変更を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="44e60-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="44e60-p102">表 1. ユーザー ポリシー</span><span class="sxs-lookup"><span data-stu-id="44e60-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44e60-109">ユーザー ポリシー</span><span class="sxs-lookup"><span data-stu-id="44e60-109">User policy</span></span></th>
<th><span data-ttu-id="44e60-110">電話使用法</span><span class="sxs-lookup"><span data-stu-id="44e60-110">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44e60-111">Default Calling Policy</span><span class="sxs-lookup"><span data-stu-id="44e60-111">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="44e60-112">ローカル</span><span class="sxs-lookup"><span data-stu-id="44e60-112">Local</span></span></p>
<p><span data-ttu-id="44e60-113">法 globalpstnhopoff</span><span class="sxs-lookup"><span data-stu-id="44e60-113">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e60-114">Redmond Local Policy</span><span class="sxs-lookup"><span data-stu-id="44e60-114">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="44e60-115">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="44e60-115">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e60-116">Dallas Calling Policy</span><span class="sxs-lookup"><span data-stu-id="44e60-116">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="44e60-117">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="44e60-117">DallasUsers</span></span></p>
<p><span data-ttu-id="44e60-118">法 globalpstnhopoff</span><span class="sxs-lookup"><span data-stu-id="44e60-118">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="44e60-p103">表 2. ルート</span><span class="sxs-lookup"><span data-stu-id="44e60-p103">Table 2. Routes</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44e60-121">ルート名</span><span class="sxs-lookup"><span data-stu-id="44e60-121">Route name</span></span></th>
<th><span data-ttu-id="44e60-122">番号のパターン</span><span class="sxs-lookup"><span data-stu-id="44e60-122">Number pattern</span></span></th>
<th><span data-ttu-id="44e60-123">電話使用法</span><span class="sxs-lookup"><span data-stu-id="44e60-123">Phone usage</span></span></th>
<th><span data-ttu-id="44e60-124">樹幹</span><span class="sxs-lookup"><span data-stu-id="44e60-124">Trunk</span></span></th>
<th><span data-ttu-id="44e60-125">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="44e60-125">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44e60-126">Redmond Local Route</span><span class="sxs-lookup"><span data-stu-id="44e60-126">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="44e60-127">^\+1 (425 | 206 | 253) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="44e60-127">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="44e60-128">ローカル</span><span class="sxs-lookup"><span data-stu-id="44e60-128">Local</span></span></p>
<p><span data-ttu-id="44e60-129">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="44e60-129">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="44e60-130">Trunk1</span><span class="sxs-lookup"><span data-stu-id="44e60-130">Trunk1</span></span></p>
<p><span data-ttu-id="44e60-131">Trunk2</span><span class="sxs-lookup"><span data-stu-id="44e60-131">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="44e60-132">赤-GW1</span><span class="sxs-lookup"><span data-stu-id="44e60-132">Red-GW1</span></span></p>
<p><span data-ttu-id="44e60-133">赤-GW2</span><span class="sxs-lookup"><span data-stu-id="44e60-133">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e60-134">Dallas Local Route</span><span class="sxs-lookup"><span data-stu-id="44e60-134">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="44e60-135">^\+1 (972 | 214 | 469) (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="44e60-135">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="44e60-136">ローカル</span><span class="sxs-lookup"><span data-stu-id="44e60-136">Local</span></span></p></td>
<td><p><span data-ttu-id="44e60-137">Trunk3</span><span class="sxs-lookup"><span data-stu-id="44e60-137">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="44e60-138">ダラス-GW1</span><span class="sxs-lookup"><span data-stu-id="44e60-138">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44e60-139">Universal Route</span><span class="sxs-lookup"><span data-stu-id="44e60-139">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="44e60-140">^\+?(\d \*) $</span><span class="sxs-lookup"><span data-stu-id="44e60-140">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="44e60-141">法 globalpstnhopoff</span><span class="sxs-lookup"><span data-stu-id="44e60-141">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="44e60-142">Trunk1</span><span class="sxs-lookup"><span data-stu-id="44e60-142">Trunk1</span></span></p>
<p><span data-ttu-id="44e60-143">Trunk2</span><span class="sxs-lookup"><span data-stu-id="44e60-143">Trunk2</span></span></p>
<p><span data-ttu-id="44e60-144">Trunk3</span><span class="sxs-lookup"><span data-stu-id="44e60-144">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="44e60-145">赤-GW1</span><span class="sxs-lookup"><span data-stu-id="44e60-145">Red-GW1</span></span></p>
<p><span data-ttu-id="44e60-146">赤-GW2</span><span class="sxs-lookup"><span data-stu-id="44e60-146">Red-GW2</span></span></p>
<p><span data-ttu-id="44e60-147">ダラス-GW1</span><span class="sxs-lookup"><span data-stu-id="44e60-147">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44e60-148">Dallas Users Route</span><span class="sxs-lookup"><span data-stu-id="44e60-148">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="44e60-149">^\+?(\d \*) $</span><span class="sxs-lookup"><span data-stu-id="44e60-149">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="44e60-150">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="44e60-150">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="44e60-151">Trunk3</span><span class="sxs-lookup"><span data-stu-id="44e60-151">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="44e60-152">ダラス-GW1</span><span class="sxs-lookup"><span data-stu-id="44e60-152">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="44e60-p104">表 1 では、Dallas Calling Policy の電話使用法 DallasUsers の後に、電話使用法 GlobalPSTNHopoff が追加されます。これにより、電話使用法 DallasUsers に対応したルートが使用できない場合に、Dallas Calling Policy の通話で電話使用法 GlobalPSTNHopoff 用に構成されたルートが使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="44e60-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

