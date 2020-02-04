---
title: 'Lync Server 2013: フェールオーバー ルートの構成'
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
ms.openlocfilehash: 22ebdf359a8cdf5f20ada8740a589b0181c3cc93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="91a81-102">Lync Server 2013 でのフェールオーバー ルートの構成</span><span class="sxs-lookup"><span data-stu-id="91a81-102">Configuring a failover route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91a81-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="91a81-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="91a81-p101">次の例では、Dallas-GW1 がメンテナンスで停止したり、利用できなくなったりしたときに使用するフェールオーバー ルートの定義方法を示します。必要な構成の変更を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="91a81-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="91a81-p102">表 1. ユーザー ポリシー</span><span class="sxs-lookup"><span data-stu-id="91a81-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91a81-108">ユーザー ポリシー</span><span class="sxs-lookup"><span data-stu-id="91a81-108">User policy</span></span></th>
<th><span data-ttu-id="91a81-109">電話使用法</span><span class="sxs-lookup"><span data-stu-id="91a81-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91a81-110">Default Calling Policy</span><span class="sxs-lookup"><span data-stu-id="91a81-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="91a81-111">Local</span><span class="sxs-lookup"><span data-stu-id="91a81-111">Local</span></span></p>
<p><span data-ttu-id="91a81-112">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="91a81-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91a81-113">Redmond Local Policy</span><span class="sxs-lookup"><span data-stu-id="91a81-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="91a81-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="91a81-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91a81-115">Dallas Calling Policy</span><span class="sxs-lookup"><span data-stu-id="91a81-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="91a81-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="91a81-116">DallasUsers</span></span></p>
<p><span data-ttu-id="91a81-117">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="91a81-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="91a81-p103">表 2. ルート</span><span class="sxs-lookup"><span data-stu-id="91a81-p103">Table 2. Routes</span></span>

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
<th><span data-ttu-id="91a81-120">ルート名</span><span class="sxs-lookup"><span data-stu-id="91a81-120">Route name</span></span></th>
<th><span data-ttu-id="91a81-121">番号のパターン</span><span class="sxs-lookup"><span data-stu-id="91a81-121">Number pattern</span></span></th>
<th><span data-ttu-id="91a81-122">電話使用法</span><span class="sxs-lookup"><span data-stu-id="91a81-122">Phone usage</span></span></th>
<th><span data-ttu-id="91a81-123">トランク</span><span class="sxs-lookup"><span data-stu-id="91a81-123">Trunk</span></span></th>
<th><span data-ttu-id="91a81-124">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="91a81-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91a81-125">Redmond Local Route</span><span class="sxs-lookup"><span data-stu-id="91a81-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="91a81-126">^\+1 (425 | 206 | 253) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="91a81-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="91a81-127">Local</span><span class="sxs-lookup"><span data-stu-id="91a81-127">Local</span></span></p>
<p><span data-ttu-id="91a81-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="91a81-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="91a81-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="91a81-129">Trunk1</span></span></p>
<p><span data-ttu-id="91a81-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="91a81-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="91a81-131">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="91a81-131">Red-GW1</span></span></p>
<p><span data-ttu-id="91a81-132">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="91a81-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91a81-133">Dallas Local Route</span><span class="sxs-lookup"><span data-stu-id="91a81-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="91a81-134">^\+1 (972 | 214 | 469) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="91a81-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="91a81-135">Local</span><span class="sxs-lookup"><span data-stu-id="91a81-135">Local</span></span></p></td>
<td><p><span data-ttu-id="91a81-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="91a81-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="91a81-137">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="91a81-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91a81-138">Universal Route</span><span class="sxs-lookup"><span data-stu-id="91a81-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="91a81-139">^\+?(\d \*) $</span><span class="sxs-lookup"><span data-stu-id="91a81-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="91a81-140">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="91a81-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="91a81-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="91a81-141">Trunk1</span></span></p>
<p><span data-ttu-id="91a81-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="91a81-142">Trunk2</span></span></p>
<p><span data-ttu-id="91a81-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="91a81-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="91a81-144">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="91a81-144">Red-GW1</span></span></p>
<p><span data-ttu-id="91a81-145">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="91a81-145">Red-GW2</span></span></p>
<p><span data-ttu-id="91a81-146">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="91a81-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91a81-147">Dallas Users Route</span><span class="sxs-lookup"><span data-stu-id="91a81-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="91a81-148">^\+?(\d \*) $</span><span class="sxs-lookup"><span data-stu-id="91a81-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="91a81-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="91a81-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="91a81-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="91a81-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="91a81-151">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="91a81-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="91a81-p104">表 1 では、Dallas Calling Policy の電話使用法 DallasUsers の後に、電話使用法 GlobalPSTNHopoff が追加されます。この結果、電話使用法 DallasUsers に対応したルートが使用できない場合に、Dallas Calling Policy の通話で電話使用法 GlobalPSTNHopoff 用に構成されたルートが使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="91a81-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

