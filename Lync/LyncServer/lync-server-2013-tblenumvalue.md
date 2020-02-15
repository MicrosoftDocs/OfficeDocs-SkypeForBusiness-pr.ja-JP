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
ms.openlocfilehash: d182a3689ae38d4117b45d6590bb2ccd08c0a8b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="9ce5b-102">Lync Server 2013 の tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="9ce5b-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ce5b-103">_**トピックの最終更新日:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="9ce5b-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="9ce5b-104">tblEnumValue は、ノード テーブルで使われる属性の Visibility (表示設定) 値と Behavior (動作) 値を含む、ハードコードされたテーブルです。</span><span class="sxs-lookup"><span data-stu-id="9ce5b-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="9ce5b-105">Columns</span><span class="sxs-lookup"><span data-stu-id="9ce5b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ce5b-106">列</span><span class="sxs-lookup"><span data-stu-id="9ce5b-106">Column</span></span></th>
<th><span data-ttu-id="9ce5b-107">種類</span><span class="sxs-lookup"><span data-stu-id="9ce5b-107">Type</span></span></th>
<th><span data-ttu-id="9ce5b-108">説明</span><span class="sxs-lookup"><span data-stu-id="9ce5b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ce5b-109">valueID</span><span class="sxs-lookup"><span data-stu-id="9ce5b-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="9ce5b-110">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="9ce5b-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="9ce5b-111">値の ID。</span><span class="sxs-lookup"><span data-stu-id="9ce5b-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce5b-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="9ce5b-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="9ce5b-113">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="9ce5b-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="9ce5b-114">属性の ID。</span><span class="sxs-lookup"><span data-stu-id="9ce5b-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce5b-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="9ce5b-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="9ce5b-116">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9ce5b-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="9ce5b-117">値の名前。</span><span class="sxs-lookup"><span data-stu-id="9ce5b-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="9ce5b-118">Keys</span><span class="sxs-lookup"><span data-stu-id="9ce5b-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ce5b-119">列</span><span class="sxs-lookup"><span data-stu-id="9ce5b-119">Column</span></span></th>
<th><span data-ttu-id="9ce5b-120">説明</span><span class="sxs-lookup"><span data-stu-id="9ce5b-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ce5b-121">valueID</span><span class="sxs-lookup"><span data-stu-id="9ce5b-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="9ce5b-122">主キー。</span><span class="sxs-lookup"><span data-stu-id="9ce5b-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce5b-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="9ce5b-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="9ce5b-124">tblEnumAttribute.attributeID テーブルを参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="9ce5b-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="9ce5b-125">テーブル値</span><span class="sxs-lookup"><span data-stu-id="9ce5b-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ce5b-126">valueID</span><span class="sxs-lookup"><span data-stu-id="9ce5b-126">valueID</span></span></th>
<th><span data-ttu-id="9ce5b-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="9ce5b-127">attributeID</span></span></th>
<th><span data-ttu-id="9ce5b-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="9ce5b-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ce5b-129">2 </span><span class="sxs-lookup"><span data-stu-id="9ce5b-129">2</span></span></p></td>
<td><p><span data-ttu-id="9ce5b-130">1 </span><span class="sxs-lookup"><span data-stu-id="9ce5b-130">1</span></span></p></td>
<td><p><span data-ttu-id="9ce5b-131">機密性</span><span class="sxs-lookup"><span data-stu-id="9ce5b-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce5b-132">3 </span><span class="sxs-lookup"><span data-stu-id="9ce5b-132">3</span></span></p></td>
<td><p><span data-ttu-id="9ce5b-133">1 </span><span class="sxs-lookup"><span data-stu-id="9ce5b-133">1</span></span></p></td>
<td><p><span data-ttu-id="9ce5b-134">scope</span><span class="sxs-lookup"><span data-stu-id="9ce5b-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce5b-135">4 </span><span class="sxs-lookup"><span data-stu-id="9ce5b-135">4</span></span></p></td>
<td><p><span data-ttu-id="9ce5b-136">2 </span><span class="sxs-lookup"><span data-stu-id="9ce5b-136">2</span></span></p></td>
<td><p><span data-ttu-id="9ce5b-137">ノーマル</span><span class="sxs-lookup"><span data-stu-id="9ce5b-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ce5b-138">5 </span><span class="sxs-lookup"><span data-stu-id="9ce5b-138">5</span></span></p></td>
<td><p><span data-ttu-id="9ce5b-139">2 </span><span class="sxs-lookup"><span data-stu-id="9ce5b-139">2</span></span></p></td>
<td><p><span data-ttu-id="9ce5b-140">大会議室</span><span class="sxs-lookup"><span data-stu-id="9ce5b-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ce5b-141">6 </span><span class="sxs-lookup"><span data-stu-id="9ce5b-141">6</span></span></p></td>
<td><p><span data-ttu-id="9ce5b-142">1 </span><span class="sxs-lookup"><span data-stu-id="9ce5b-142">1</span></span></p></td>
<td><p><span data-ttu-id="9ce5b-143">開か</span><span class="sxs-lookup"><span data-stu-id="9ce5b-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="9ce5b-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ce5b-144">See Also</span></span>


[<span data-ttu-id="9ce5b-145">Lync Server 2013 の tblNode</span><span class="sxs-lookup"><span data-stu-id="9ce5b-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

