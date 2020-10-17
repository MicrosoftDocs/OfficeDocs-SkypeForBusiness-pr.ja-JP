---
title: 'Lync Server 2013: tblEnumAttribute'
description: 'Lync Server 2013: tblEnumAttribute。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumAttribute
ms:assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558617(v=OCS.15)
ms:contentKeyID: 48183523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca979a68e758ad47b691ac704f24c68c1841938a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571393"
---
# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="81736-103">Lync Server 2013 の tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="81736-103">tblEnumAttribute in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81736-104">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="81736-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="81736-105">tblEnumAttribute は、Node テーブルで使用される表示および動作属性を含むハードコードされたテーブルです。</span><span class="sxs-lookup"><span data-stu-id="81736-105">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="81736-106">段組み</span><span class="sxs-lookup"><span data-stu-id="81736-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81736-107">Column</span><span class="sxs-lookup"><span data-stu-id="81736-107">Column</span></span></th>
<th><span data-ttu-id="81736-108">種類</span><span class="sxs-lookup"><span data-stu-id="81736-108">Type</span></span></th>
<th><span data-ttu-id="81736-109">説明</span><span class="sxs-lookup"><span data-stu-id="81736-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81736-110">attributeID</span><span class="sxs-lookup"><span data-stu-id="81736-110">attributeID</span></span></p></td>
<td><p><span data-ttu-id="81736-111">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="81736-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="81736-112">属性の ID。</span><span class="sxs-lookup"><span data-stu-id="81736-112">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81736-113">attributeName</span><span class="sxs-lookup"><span data-stu-id="81736-113">attributeName</span></span></p></td>
<td><p><span data-ttu-id="81736-114">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="81736-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="81736-115">属性の名前。</span><span class="sxs-lookup"><span data-stu-id="81736-115">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="81736-116">キー</span><span class="sxs-lookup"><span data-stu-id="81736-116">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81736-117">列</span><span class="sxs-lookup"><span data-stu-id="81736-117">Column</span></span></th>
<th><span data-ttu-id="81736-118">説明</span><span class="sxs-lookup"><span data-stu-id="81736-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81736-119">attributeID</span><span class="sxs-lookup"><span data-stu-id="81736-119">attributeID</span></span></p></td>
<td><p><span data-ttu-id="81736-120">主キー。</span><span class="sxs-lookup"><span data-stu-id="81736-120">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="81736-121">テーブル値</span><span class="sxs-lookup"><span data-stu-id="81736-121">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="81736-122">attributeID</span><span class="sxs-lookup"><span data-stu-id="81736-122">attributeID</span></span></th>
<th><span data-ttu-id="81736-123">attributeName</span><span class="sxs-lookup"><span data-stu-id="81736-123">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81736-124">1-d</span><span class="sxs-lookup"><span data-stu-id="81736-124">1</span></span></p></td>
<td><p><span data-ttu-id="81736-125">表示.</span><span class="sxs-lookup"><span data-stu-id="81736-125">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81736-126">pbm-2</span><span class="sxs-lookup"><span data-stu-id="81736-126">2</span></span></p></td>
<td><p><span data-ttu-id="81736-127">Behavior.</span><span class="sxs-lookup"><span data-stu-id="81736-127">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="81736-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="81736-128">See Also</span></span>


[<span data-ttu-id="81736-129">Lync Server 2013 の tblNode</span><span class="sxs-lookup"><span data-stu-id="81736-129">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

