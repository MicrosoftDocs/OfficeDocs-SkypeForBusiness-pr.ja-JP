---
title: 'Lync Server 2013: tblEnumValue'
description: 'Lync Server 2013: tblEnumValue。'
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
ms.openlocfilehash: 159f90bb96c367fcb3e11725a582a9993080d3fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571373"
---
# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="bc0cd-103">Lync Server 2013 の tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="bc0cd-103">tblEnumValue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc0cd-104">_**トピックの最終更新日:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="bc0cd-104">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="bc0cd-105">tblEnumValue は、ノード テーブルで使われる属性の Visibility (表示設定) 値と Behavior (動作) 値を含む、ハードコードされたテーブルです。</span><span class="sxs-lookup"><span data-stu-id="bc0cd-105">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="bc0cd-106">段組み</span><span class="sxs-lookup"><span data-stu-id="bc0cd-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc0cd-107">Column</span><span class="sxs-lookup"><span data-stu-id="bc0cd-107">Column</span></span></th>
<th><span data-ttu-id="bc0cd-108">種類</span><span class="sxs-lookup"><span data-stu-id="bc0cd-108">Type</span></span></th>
<th><span data-ttu-id="bc0cd-109">説明</span><span class="sxs-lookup"><span data-stu-id="bc0cd-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc0cd-110">valueID</span><span class="sxs-lookup"><span data-stu-id="bc0cd-110">valueID</span></span></p></td>
<td><p><span data-ttu-id="bc0cd-111">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="bc0cd-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="bc0cd-112">値の ID。</span><span class="sxs-lookup"><span data-stu-id="bc0cd-112">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc0cd-113">attributeID</span><span class="sxs-lookup"><span data-stu-id="bc0cd-113">attributeID</span></span></p></td>
<td><p><span data-ttu-id="bc0cd-114">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="bc0cd-114">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="bc0cd-115">属性の ID。</span><span class="sxs-lookup"><span data-stu-id="bc0cd-115">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc0cd-116">attributeValue</span><span class="sxs-lookup"><span data-stu-id="bc0cd-116">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="bc0cd-117">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bc0cd-117">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="bc0cd-118">値の名前。</span><span class="sxs-lookup"><span data-stu-id="bc0cd-118">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="bc0cd-119">Keys</span><span class="sxs-lookup"><span data-stu-id="bc0cd-119">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc0cd-120">列</span><span class="sxs-lookup"><span data-stu-id="bc0cd-120">Column</span></span></th>
<th><span data-ttu-id="bc0cd-121">説明</span><span class="sxs-lookup"><span data-stu-id="bc0cd-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc0cd-122">valueID</span><span class="sxs-lookup"><span data-stu-id="bc0cd-122">valueID</span></span></p></td>
<td><p><span data-ttu-id="bc0cd-123">主キー。</span><span class="sxs-lookup"><span data-stu-id="bc0cd-123">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc0cd-124">attributeID</span><span class="sxs-lookup"><span data-stu-id="bc0cd-124">attributeID</span></span></p></td>
<td><p><span data-ttu-id="bc0cd-125">tblEnumAttribute.attributeID テーブルを参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="bc0cd-125">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="bc0cd-126">テーブル値</span><span class="sxs-lookup"><span data-stu-id="bc0cd-126">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc0cd-127">valueID</span><span class="sxs-lookup"><span data-stu-id="bc0cd-127">valueID</span></span></th>
<th><span data-ttu-id="bc0cd-128">attributeID</span><span class="sxs-lookup"><span data-stu-id="bc0cd-128">attributeID</span></span></th>
<th><span data-ttu-id="bc0cd-129">attributeValue</span><span class="sxs-lookup"><span data-stu-id="bc0cd-129">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc0cd-130">pbm-2</span><span class="sxs-lookup"><span data-stu-id="bc0cd-130">2</span></span></p></td>
<td><p><span data-ttu-id="bc0cd-131">1-d</span><span class="sxs-lookup"><span data-stu-id="bc0cd-131">1</span></span></p></td>
<td><p><span data-ttu-id="bc0cd-132">機密性</span><span class="sxs-lookup"><span data-stu-id="bc0cd-132">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc0cd-133">1/3</span><span class="sxs-lookup"><span data-stu-id="bc0cd-133">3</span></span></p></td>
<td><p><span data-ttu-id="bc0cd-134">1-d</span><span class="sxs-lookup"><span data-stu-id="bc0cd-134">1</span></span></p></td>
<td><p><span data-ttu-id="bc0cd-135">scope</span><span class="sxs-lookup"><span data-stu-id="bc0cd-135">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc0cd-136">4 </span><span class="sxs-lookup"><span data-stu-id="bc0cd-136">4</span></span></p></td>
<td><p><span data-ttu-id="bc0cd-137">pbm-2</span><span class="sxs-lookup"><span data-stu-id="bc0cd-137">2</span></span></p></td>
<td><p><span data-ttu-id="bc0cd-138">ノーマル</span><span class="sxs-lookup"><span data-stu-id="bc0cd-138">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc0cd-139">5 </span><span class="sxs-lookup"><span data-stu-id="bc0cd-139">5</span></span></p></td>
<td><p><span data-ttu-id="bc0cd-140">pbm-2</span><span class="sxs-lookup"><span data-stu-id="bc0cd-140">2</span></span></p></td>
<td><p><span data-ttu-id="bc0cd-141">大会議室</span><span class="sxs-lookup"><span data-stu-id="bc0cd-141">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc0cd-142">6 </span><span class="sxs-lookup"><span data-stu-id="bc0cd-142">6</span></span></p></td>
<td><p><span data-ttu-id="bc0cd-143">1-d</span><span class="sxs-lookup"><span data-stu-id="bc0cd-143">1</span></span></p></td>
<td><p><span data-ttu-id="bc0cd-144">開か</span><span class="sxs-lookup"><span data-stu-id="bc0cd-144">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="bc0cd-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc0cd-145">See Also</span></span>


[<span data-ttu-id="bc0cd-146">Lync Server 2013 の tblNode</span><span class="sxs-lookup"><span data-stu-id="bc0cd-146">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

