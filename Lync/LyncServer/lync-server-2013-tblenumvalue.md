---
title: 'Lync Server 2013: tblEnumValue'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1758daf16575491960415647e4c9bc4b43920d26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="da030-102">Lync Server 2013 の tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="da030-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da030-103">_**最終更新日:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="da030-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="da030-104">tblEnumValue は、ノードテーブルで使用されている属性の可視性と動作の値を含む、ハードコーディングされた表です。</span><span class="sxs-lookup"><span data-stu-id="da030-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="da030-105">行</span><span class="sxs-lookup"><span data-stu-id="da030-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da030-106">列</span><span class="sxs-lookup"><span data-stu-id="da030-106">Column</span></span></th>
<th><span data-ttu-id="da030-107">型</span><span class="sxs-lookup"><span data-stu-id="da030-107">Type</span></span></th>
<th><span data-ttu-id="da030-108">説明</span><span class="sxs-lookup"><span data-stu-id="da030-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da030-109">valueID</span><span class="sxs-lookup"><span data-stu-id="da030-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="da030-110">smallint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="da030-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="da030-111">値の ID です。</span><span class="sxs-lookup"><span data-stu-id="da030-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da030-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="da030-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="da030-113">smallint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="da030-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="da030-114">属性の ID です。</span><span class="sxs-lookup"><span data-stu-id="da030-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da030-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="da030-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="da030-116">nvarchar (256)、null ではない</span><span class="sxs-lookup"><span data-stu-id="da030-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="da030-117">値の名前。</span><span class="sxs-lookup"><span data-stu-id="da030-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="da030-118">機能</span><span class="sxs-lookup"><span data-stu-id="da030-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da030-119">列</span><span class="sxs-lookup"><span data-stu-id="da030-119">Column</span></span></th>
<th><span data-ttu-id="da030-120">説明</span><span class="sxs-lookup"><span data-stu-id="da030-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da030-121">valueID</span><span class="sxs-lookup"><span data-stu-id="da030-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="da030-122">主キー。</span><span class="sxs-lookup"><span data-stu-id="da030-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da030-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="da030-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="da030-124">TblEnumAttribute テーブルで参照する外部キー</span><span class="sxs-lookup"><span data-stu-id="da030-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="da030-125">テーブルの値</span><span class="sxs-lookup"><span data-stu-id="da030-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da030-126">valueID</span><span class="sxs-lookup"><span data-stu-id="da030-126">valueID</span></span></th>
<th><span data-ttu-id="da030-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="da030-127">attributeID</span></span></th>
<th><span data-ttu-id="da030-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="da030-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da030-129">2</span><span class="sxs-lookup"><span data-stu-id="da030-129">2</span></span></p></td>
<td><p><span data-ttu-id="da030-130">1</span><span class="sxs-lookup"><span data-stu-id="da030-130">1</span></span></p></td>
<td><p><span data-ttu-id="da030-131">private</span><span class="sxs-lookup"><span data-stu-id="da030-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da030-132">3</span><span class="sxs-lookup"><span data-stu-id="da030-132">3</span></span></p></td>
<td><p><span data-ttu-id="da030-133">1</span><span class="sxs-lookup"><span data-stu-id="da030-133">1</span></span></p></td>
<td><p><span data-ttu-id="da030-134">種類</span><span class="sxs-lookup"><span data-stu-id="da030-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da030-135">4</span><span class="sxs-lookup"><span data-stu-id="da030-135">4</span></span></p></td>
<td><p><span data-ttu-id="da030-136">2</span><span class="sxs-lookup"><span data-stu-id="da030-136">2</span></span></p></td>
<td><p><span data-ttu-id="da030-137">標準</span><span class="sxs-lookup"><span data-stu-id="da030-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da030-138">5</span><span class="sxs-lookup"><span data-stu-id="da030-138">5</span></span></p></td>
<td><p><span data-ttu-id="da030-139">2</span><span class="sxs-lookup"><span data-stu-id="da030-139">2</span></span></p></td>
<td><p><span data-ttu-id="da030-140">大</span><span class="sxs-lookup"><span data-stu-id="da030-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da030-141">6</span><span class="sxs-lookup"><span data-stu-id="da030-141">6</span></span></p></td>
<td><p><span data-ttu-id="da030-142">1</span><span class="sxs-lookup"><span data-stu-id="da030-142">1</span></span></p></td>
<td><p><span data-ttu-id="da030-143">開こう</span><span class="sxs-lookup"><span data-stu-id="da030-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="da030-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="da030-144">See Also</span></span>


[<span data-ttu-id="da030-145">Lync Server 2013 の tblNode</span><span class="sxs-lookup"><span data-stu-id="da030-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

