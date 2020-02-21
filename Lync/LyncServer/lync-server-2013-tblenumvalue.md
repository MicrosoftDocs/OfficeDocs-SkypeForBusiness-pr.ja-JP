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
ms.openlocfilehash: 4166e25375c7ddd631b1ee7944ac703f21c9ba80
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="302a4-102">Lync Server 2013 の tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="302a4-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="302a4-103">_**トピックの最終更新日:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="302a4-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="302a4-104">tblEnumValue は、ノード テーブルで使われる属性の Visibility (表示設定) 値と Behavior (動作) 値を含む、ハードコードされたテーブルです。</span><span class="sxs-lookup"><span data-stu-id="302a4-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="302a4-105">Columns</span><span class="sxs-lookup"><span data-stu-id="302a4-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="302a4-106">列</span><span class="sxs-lookup"><span data-stu-id="302a4-106">Column</span></span></th>
<th><span data-ttu-id="302a4-107">種類</span><span class="sxs-lookup"><span data-stu-id="302a4-107">Type</span></span></th>
<th><span data-ttu-id="302a4-108">説明</span><span class="sxs-lookup"><span data-stu-id="302a4-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="302a4-109">valueID</span><span class="sxs-lookup"><span data-stu-id="302a4-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="302a4-110">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="302a4-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="302a4-111">値の ID。</span><span class="sxs-lookup"><span data-stu-id="302a4-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="302a4-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="302a4-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="302a4-113">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="302a4-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="302a4-114">属性の ID。</span><span class="sxs-lookup"><span data-stu-id="302a4-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="302a4-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="302a4-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="302a4-116">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="302a4-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="302a4-117">値の名前。</span><span class="sxs-lookup"><span data-stu-id="302a4-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="302a4-118">Keys</span><span class="sxs-lookup"><span data-stu-id="302a4-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="302a4-119">列</span><span class="sxs-lookup"><span data-stu-id="302a4-119">Column</span></span></th>
<th><span data-ttu-id="302a4-120">説明</span><span class="sxs-lookup"><span data-stu-id="302a4-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="302a4-121">valueID</span><span class="sxs-lookup"><span data-stu-id="302a4-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="302a4-122">主キー。</span><span class="sxs-lookup"><span data-stu-id="302a4-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="302a4-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="302a4-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="302a4-124">tblEnumAttribute.attributeID テーブルを参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="302a4-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="302a4-125">テーブル値</span><span class="sxs-lookup"><span data-stu-id="302a4-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="302a4-126">valueID</span><span class="sxs-lookup"><span data-stu-id="302a4-126">valueID</span></span></th>
<th><span data-ttu-id="302a4-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="302a4-127">attributeID</span></span></th>
<th><span data-ttu-id="302a4-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="302a4-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="302a4-129">pbm-2</span><span class="sxs-lookup"><span data-stu-id="302a4-129">2</span></span></p></td>
<td><p><span data-ttu-id="302a4-130">1-d</span><span class="sxs-lookup"><span data-stu-id="302a4-130">1</span></span></p></td>
<td><p><span data-ttu-id="302a4-131">機密性</span><span class="sxs-lookup"><span data-stu-id="302a4-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="302a4-132">1/3</span><span class="sxs-lookup"><span data-stu-id="302a4-132">3</span></span></p></td>
<td><p><span data-ttu-id="302a4-133">1-d</span><span class="sxs-lookup"><span data-stu-id="302a4-133">1</span></span></p></td>
<td><p><span data-ttu-id="302a4-134">scope</span><span class="sxs-lookup"><span data-stu-id="302a4-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="302a4-135">2/4</span><span class="sxs-lookup"><span data-stu-id="302a4-135">4</span></span></p></td>
<td><p><span data-ttu-id="302a4-136">pbm-2</span><span class="sxs-lookup"><span data-stu-id="302a4-136">2</span></span></p></td>
<td><p><span data-ttu-id="302a4-137">ノーマル</span><span class="sxs-lookup"><span data-stu-id="302a4-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="302a4-138">5</span><span class="sxs-lookup"><span data-stu-id="302a4-138">5</span></span></p></td>
<td><p><span data-ttu-id="302a4-139">pbm-2</span><span class="sxs-lookup"><span data-stu-id="302a4-139">2</span></span></p></td>
<td><p><span data-ttu-id="302a4-140">大会議室</span><span class="sxs-lookup"><span data-stu-id="302a4-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="302a4-141">6 </span><span class="sxs-lookup"><span data-stu-id="302a4-141">6</span></span></p></td>
<td><p><span data-ttu-id="302a4-142">1-d</span><span class="sxs-lookup"><span data-stu-id="302a4-142">1</span></span></p></td>
<td><p><span data-ttu-id="302a4-143">開か</span><span class="sxs-lookup"><span data-stu-id="302a4-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="302a4-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="302a4-144">See Also</span></span>


[<span data-ttu-id="302a4-145">Lync Server 2013 の tblNode</span><span class="sxs-lookup"><span data-stu-id="302a4-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

