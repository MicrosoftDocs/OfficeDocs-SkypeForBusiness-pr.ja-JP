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
ms.openlocfilehash: 17477c647d2e5dd5918225486c43b93a29509fb2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="6944c-102">Lync Server 2013 でのフェールオーバールートの構成</span><span class="sxs-lookup"><span data-stu-id="6944c-102">Configuring a failover route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6944c-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="6944c-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="6944c-p101">次の例では、Dallas-GW1 がメンテナンスで停止したり、利用できなくなったりしたときに使用するフェールオーバー ルートの定義方法を示します。必要な構成の変更を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="6944c-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="6944c-p102">表 1. ユーザー ポリシー</span><span class="sxs-lookup"><span data-stu-id="6944c-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6944c-108">ユーザー ポリシー</span><span class="sxs-lookup"><span data-stu-id="6944c-108">User policy</span></span></th>
<th><span data-ttu-id="6944c-109">電話使用法</span><span class="sxs-lookup"><span data-stu-id="6944c-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6944c-110">Default Calling Policy</span><span class="sxs-lookup"><span data-stu-id="6944c-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="6944c-111">ローカル</span><span class="sxs-lookup"><span data-stu-id="6944c-111">Local</span></span></p>
<p><span data-ttu-id="6944c-112">法 globalpstnhopoff</span><span class="sxs-lookup"><span data-stu-id="6944c-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6944c-113">Redmond Local Policy</span><span class="sxs-lookup"><span data-stu-id="6944c-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="6944c-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="6944c-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6944c-115">Dallas Calling Policy</span><span class="sxs-lookup"><span data-stu-id="6944c-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="6944c-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="6944c-116">DallasUsers</span></span></p>
<p><span data-ttu-id="6944c-117">法 globalpstnhopoff</span><span class="sxs-lookup"><span data-stu-id="6944c-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="6944c-p103">表 2. ルート</span><span class="sxs-lookup"><span data-stu-id="6944c-p103">Table 2. Routes</span></span>

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
<th><span data-ttu-id="6944c-120">ルート名</span><span class="sxs-lookup"><span data-stu-id="6944c-120">Route name</span></span></th>
<th><span data-ttu-id="6944c-121">番号のパターン</span><span class="sxs-lookup"><span data-stu-id="6944c-121">Number pattern</span></span></th>
<th><span data-ttu-id="6944c-122">電話使用法</span><span class="sxs-lookup"><span data-stu-id="6944c-122">Phone usage</span></span></th>
<th><span data-ttu-id="6944c-123">樹幹</span><span class="sxs-lookup"><span data-stu-id="6944c-123">Trunk</span></span></th>
<th><span data-ttu-id="6944c-124">ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="6944c-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6944c-125">Redmond Local Route</span><span class="sxs-lookup"><span data-stu-id="6944c-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="6944c-126">^\+1 (425 | 206 | 253) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="6944c-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="6944c-127">ローカル</span><span class="sxs-lookup"><span data-stu-id="6944c-127">Local</span></span></p>
<p><span data-ttu-id="6944c-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="6944c-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="6944c-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="6944c-129">Trunk1</span></span></p>
<p><span data-ttu-id="6944c-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="6944c-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="6944c-131">赤-GW1</span><span class="sxs-lookup"><span data-stu-id="6944c-131">Red-GW1</span></span></p>
<p><span data-ttu-id="6944c-132">赤-GW2</span><span class="sxs-lookup"><span data-stu-id="6944c-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6944c-133">Dallas Local Route</span><span class="sxs-lookup"><span data-stu-id="6944c-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="6944c-134">^\+1 (972 | 214 | 469) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="6944c-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="6944c-135">ローカル</span><span class="sxs-lookup"><span data-stu-id="6944c-135">Local</span></span></p></td>
<td><p><span data-ttu-id="6944c-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="6944c-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="6944c-137">ダラス-GW1</span><span class="sxs-lookup"><span data-stu-id="6944c-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6944c-138">Universal Route</span><span class="sxs-lookup"><span data-stu-id="6944c-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="6944c-139">^\+?(\d \*) $</span><span class="sxs-lookup"><span data-stu-id="6944c-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="6944c-140">法 globalpstnhopoff</span><span class="sxs-lookup"><span data-stu-id="6944c-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="6944c-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="6944c-141">Trunk1</span></span></p>
<p><span data-ttu-id="6944c-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="6944c-142">Trunk2</span></span></p>
<p><span data-ttu-id="6944c-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="6944c-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="6944c-144">赤-GW1</span><span class="sxs-lookup"><span data-stu-id="6944c-144">Red-GW1</span></span></p>
<p><span data-ttu-id="6944c-145">赤-GW2</span><span class="sxs-lookup"><span data-stu-id="6944c-145">Red-GW2</span></span></p>
<p><span data-ttu-id="6944c-146">ダラス-GW1</span><span class="sxs-lookup"><span data-stu-id="6944c-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6944c-147">Dallas Users Route</span><span class="sxs-lookup"><span data-stu-id="6944c-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="6944c-148">^\+?(\d \*) $</span><span class="sxs-lookup"><span data-stu-id="6944c-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="6944c-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="6944c-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="6944c-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="6944c-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="6944c-151">ダラス-GW1</span><span class="sxs-lookup"><span data-stu-id="6944c-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6944c-p104">表 1 では、Dallas Calling Policy の電話使用法 DallasUsers の後に、電話使用法 GlobalPSTNHopoff が追加されます。これにより、電話使用法 DallasUsers に対応したルートが使用できない場合に、Dallas Calling Policy の通話で電話使用法 GlobalPSTNHopoff 用に構成されたルートが使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6944c-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

