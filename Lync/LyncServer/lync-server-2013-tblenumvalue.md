---
title: 'Lync Server 2013: tblEnumValue'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c09c5e911dcd63f50d8b15343075c5b3e05e631
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="4a179-102">Lync Server 2013 の tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="4a179-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a179-103">_**最終更新日:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="4a179-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="4a179-104">tblEnumValue は、ノードテーブルで使用されている属性の可視性と動作の値を含む、ハードコーディングされた表です。</span><span class="sxs-lookup"><span data-stu-id="4a179-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="4a179-105">行</span><span class="sxs-lookup"><span data-stu-id="4a179-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a179-106">列</span><span class="sxs-lookup"><span data-stu-id="4a179-106">Column</span></span></th>
<th><span data-ttu-id="4a179-107">型</span><span class="sxs-lookup"><span data-stu-id="4a179-107">Type</span></span></th>
<th><span data-ttu-id="4a179-108">説明</span><span class="sxs-lookup"><span data-stu-id="4a179-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a179-109">valueID</span><span class="sxs-lookup"><span data-stu-id="4a179-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="4a179-110">smallint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="4a179-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="4a179-111">値の ID です。</span><span class="sxs-lookup"><span data-stu-id="4a179-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a179-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="4a179-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="4a179-113">smallint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="4a179-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="4a179-114">属性の ID です。</span><span class="sxs-lookup"><span data-stu-id="4a179-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a179-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="4a179-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="4a179-116">nvarchar (256)、null ではない</span><span class="sxs-lookup"><span data-stu-id="4a179-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="4a179-117">値の名前。</span><span class="sxs-lookup"><span data-stu-id="4a179-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="4a179-118">機能</span><span class="sxs-lookup"><span data-stu-id="4a179-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a179-119">列</span><span class="sxs-lookup"><span data-stu-id="4a179-119">Column</span></span></th>
<th><span data-ttu-id="4a179-120">説明</span><span class="sxs-lookup"><span data-stu-id="4a179-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a179-121">valueID</span><span class="sxs-lookup"><span data-stu-id="4a179-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="4a179-122">主キー。</span><span class="sxs-lookup"><span data-stu-id="4a179-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a179-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="4a179-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="4a179-124">TblEnumAttribute テーブルで参照する外部キー</span><span class="sxs-lookup"><span data-stu-id="4a179-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="4a179-125">テーブルの値</span><span class="sxs-lookup"><span data-stu-id="4a179-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a179-126">valueID</span><span class="sxs-lookup"><span data-stu-id="4a179-126">valueID</span></span></th>
<th><span data-ttu-id="4a179-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="4a179-127">attributeID</span></span></th>
<th><span data-ttu-id="4a179-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="4a179-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a179-129">両面</span><span class="sxs-lookup"><span data-stu-id="4a179-129">2</span></span></p></td>
<td><p><span data-ttu-id="4a179-130">1</span><span class="sxs-lookup"><span data-stu-id="4a179-130">1</span></span></p></td>
<td><p><span data-ttu-id="4a179-131">private</span><span class="sxs-lookup"><span data-stu-id="4a179-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a179-132">3</span><span class="sxs-lookup"><span data-stu-id="4a179-132">3</span></span></p></td>
<td><p><span data-ttu-id="4a179-133">1</span><span class="sxs-lookup"><span data-stu-id="4a179-133">1</span></span></p></td>
<td><p><span data-ttu-id="4a179-134">種類</span><span class="sxs-lookup"><span data-stu-id="4a179-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a179-135">4</span><span class="sxs-lookup"><span data-stu-id="4a179-135">4</span></span></p></td>
<td><p><span data-ttu-id="4a179-136">両面</span><span class="sxs-lookup"><span data-stu-id="4a179-136">2</span></span></p></td>
<td><p><span data-ttu-id="4a179-137">標準</span><span class="sxs-lookup"><span data-stu-id="4a179-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a179-138">5</span><span class="sxs-lookup"><span data-stu-id="4a179-138">5</span></span></p></td>
<td><p><span data-ttu-id="4a179-139">両面</span><span class="sxs-lookup"><span data-stu-id="4a179-139">2</span></span></p></td>
<td><p><span data-ttu-id="4a179-140">大</span><span class="sxs-lookup"><span data-stu-id="4a179-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a179-141">6</span><span class="sxs-lookup"><span data-stu-id="4a179-141">6</span></span></p></td>
<td><p><span data-ttu-id="4a179-142">1</span><span class="sxs-lookup"><span data-stu-id="4a179-142">1</span></span></p></td>
<td><p><span data-ttu-id="4a179-143">開こう</span><span class="sxs-lookup"><span data-stu-id="4a179-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="4a179-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a179-144">See Also</span></span>


[<span data-ttu-id="4a179-145">Lync Server 2013 の tblNode</span><span class="sxs-lookup"><span data-stu-id="4a179-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

