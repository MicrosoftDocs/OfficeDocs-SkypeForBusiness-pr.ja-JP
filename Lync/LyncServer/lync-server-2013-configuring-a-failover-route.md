---
title: 'Lync Server 2013: フェールオーバールートの構成'
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
ms.openlocfilehash: b012b1bbab693e9a95a64d1fb3150723523cb53d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="ebcf6-102">Lync Server 2013 でのフェールオーバールートの構成</span><span class="sxs-lookup"><span data-stu-id="ebcf6-102">Configuring a failover route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebcf6-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ebcf6-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ebcf6-p101">次の例では、Dallas-GW1 がメンテナンスで停止したり、利用できなくなったりしたときに使用するフェールオーバー ルートの定義方法を示します。必要な構成の変更を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="ebcf6-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="ebcf6-p102">表 1. ユーザー ポリシー</span><span class="sxs-lookup"><span data-stu-id="ebcf6-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ebcf6-108">ユーザー ポリシー</span><span class="sxs-lookup"><span data-stu-id="ebcf6-108">User policy</span></span></th>
<th><span data-ttu-id="ebcf6-109">電話使用法</span><span class="sxs-lookup"><span data-stu-id="ebcf6-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ebcf6-110">Default Calling Policy</span><span class="sxs-lookup"><span data-stu-id="ebcf6-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="ebcf6-111">ローカル</span><span class="sxs-lookup"><span data-stu-id="ebcf6-111">Local</span></span></p>
<p><span data-ttu-id="ebcf6-112">法 globalpstnhopoff</span><span class="sxs-lookup"><span data-stu-id="ebcf6-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebcf6-113">Redmond Local Policy</span><span class="sxs-lookup"><span data-stu-id="ebcf6-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="ebcf6-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="ebcf6-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebcf6-115">Dallas Calling Policy</span><span class="sxs-lookup"><span data-stu-id="ebcf6-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="ebcf6-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="ebcf6-116">DallasUsers</span></span></p>
<p><span data-ttu-id="ebcf6-117">法 globalpstnhopoff</span><span class="sxs-lookup"><span data-stu-id="ebcf6-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="ebcf6-p103">表 2. ルート</span><span class="sxs-lookup"><span data-stu-id="ebcf6-p103">Table 2. Routes</span></span>

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
<th><span data-ttu-id="ebcf6-120">ルート名</span><span class="sxs-lookup"><span data-stu-id="ebcf6-120">Route name</span></span></th>
<th><span data-ttu-id="ebcf6-121">番号のパターン</span><span class="sxs-lookup"><span data-stu-id="ebcf6-121">Number pattern</span></span></th>
<th><span data-ttu-id="ebcf6-122">電話使用法</span><span class="sxs-lookup"><span data-stu-id="ebcf6-122">Phone usage</span></span></th>
<th><span data-ttu-id="ebcf6-123">樹幹</span><span class="sxs-lookup"><span data-stu-id="ebcf6-123">Trunk</span></span></th>
<th><span data-ttu-id="ebcf6-124">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="ebcf6-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ebcf6-125">Redmond Local Route</span><span class="sxs-lookup"><span data-stu-id="ebcf6-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="ebcf6-126">^\+1 (425 | 206 | 253) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="ebcf6-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="ebcf6-127">ローカル</span><span class="sxs-lookup"><span data-stu-id="ebcf6-127">Local</span></span></p>
<p><span data-ttu-id="ebcf6-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="ebcf6-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="ebcf6-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="ebcf6-129">Trunk1</span></span></p>
<p><span data-ttu-id="ebcf6-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="ebcf6-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="ebcf6-131">赤-GW1</span><span class="sxs-lookup"><span data-stu-id="ebcf6-131">Red-GW1</span></span></p>
<p><span data-ttu-id="ebcf6-132">赤-GW2</span><span class="sxs-lookup"><span data-stu-id="ebcf6-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebcf6-133">Dallas Local Route</span><span class="sxs-lookup"><span data-stu-id="ebcf6-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="ebcf6-134">^\+1 (972 | 214 | 469) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="ebcf6-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="ebcf6-135">ローカル</span><span class="sxs-lookup"><span data-stu-id="ebcf6-135">Local</span></span></p></td>
<td><p><span data-ttu-id="ebcf6-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="ebcf6-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="ebcf6-137">ダラス-GW1</span><span class="sxs-lookup"><span data-stu-id="ebcf6-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebcf6-138">Universal Route</span><span class="sxs-lookup"><span data-stu-id="ebcf6-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="ebcf6-139">^\+?(\d \*) $</span><span class="sxs-lookup"><span data-stu-id="ebcf6-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="ebcf6-140">法 globalpstnhopoff</span><span class="sxs-lookup"><span data-stu-id="ebcf6-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="ebcf6-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="ebcf6-141">Trunk1</span></span></p>
<p><span data-ttu-id="ebcf6-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="ebcf6-142">Trunk2</span></span></p>
<p><span data-ttu-id="ebcf6-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="ebcf6-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="ebcf6-144">赤-GW1</span><span class="sxs-lookup"><span data-stu-id="ebcf6-144">Red-GW1</span></span></p>
<p><span data-ttu-id="ebcf6-145">赤-GW2</span><span class="sxs-lookup"><span data-stu-id="ebcf6-145">Red-GW2</span></span></p>
<p><span data-ttu-id="ebcf6-146">ダラス-GW1</span><span class="sxs-lookup"><span data-stu-id="ebcf6-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebcf6-147">Dallas Users Route</span><span class="sxs-lookup"><span data-stu-id="ebcf6-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="ebcf6-148">^\+?(\d \*) $</span><span class="sxs-lookup"><span data-stu-id="ebcf6-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="ebcf6-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="ebcf6-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="ebcf6-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="ebcf6-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="ebcf6-151">ダラス-GW1</span><span class="sxs-lookup"><span data-stu-id="ebcf6-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ebcf6-p104">表 1 では、Dallas Calling Policy の電話使用法 DallasUsers の後に、電話使用法 GlobalPSTNHopoff が追加されます。これにより、電話使用法 DallasUsers に対応したルートが使用できない場合に、Dallas Calling Policy の通話で電話使用法 GlobalPSTNHopoff 用に構成されたルートが使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ebcf6-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

