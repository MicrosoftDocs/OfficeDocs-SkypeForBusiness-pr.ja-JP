---
title: 'Lync Server 2013: tblEnumAttribute'
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
ms.openlocfilehash: 73ac5a7cf26c97b31daf5785a90fac102c50e480
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="4c3b4-102">Lync Server 2013 の tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="4c3b4-102">tblEnumAttribute in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c3b4-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4c3b4-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4c3b4-104">tblEnumAttribute は、ノードテーブルで使用される Visibility 属性と Behavior 属性を含む、ハードコーディングされた表です。</span><span class="sxs-lookup"><span data-stu-id="4c3b4-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="4c3b4-105">行</span><span class="sxs-lookup"><span data-stu-id="4c3b4-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c3b4-106">列</span><span class="sxs-lookup"><span data-stu-id="4c3b4-106">Column</span></span></th>
<th><span data-ttu-id="4c3b4-107">型</span><span class="sxs-lookup"><span data-stu-id="4c3b4-107">Type</span></span></th>
<th><span data-ttu-id="4c3b4-108">説明</span><span class="sxs-lookup"><span data-stu-id="4c3b4-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c3b4-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="4c3b4-109">attributeID</span></span></p></td>
<td><p><span data-ttu-id="4c3b4-110">smallint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="4c3b4-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="4c3b4-111">属性の ID です。</span><span class="sxs-lookup"><span data-stu-id="4c3b4-111">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c3b4-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="4c3b4-112">attributeName</span></span></p></td>
<td><p><span data-ttu-id="4c3b4-113">nvarchar (256)、null ではない</span><span class="sxs-lookup"><span data-stu-id="4c3b4-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="4c3b4-114">属性の名前。</span><span class="sxs-lookup"><span data-stu-id="4c3b4-114">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="4c3b4-115">キー</span><span class="sxs-lookup"><span data-stu-id="4c3b4-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c3b4-116">列</span><span class="sxs-lookup"><span data-stu-id="4c3b4-116">Column</span></span></th>
<th><span data-ttu-id="4c3b4-117">説明</span><span class="sxs-lookup"><span data-stu-id="4c3b4-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c3b4-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="4c3b4-118">attributeID</span></span></p></td>
<td><p><span data-ttu-id="4c3b4-119">主キー。</span><span class="sxs-lookup"><span data-stu-id="4c3b4-119">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="4c3b4-120">テーブルの値</span><span class="sxs-lookup"><span data-stu-id="4c3b4-120">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c3b4-121">attributeID</span><span class="sxs-lookup"><span data-stu-id="4c3b4-121">attributeID</span></span></th>
<th><span data-ttu-id="4c3b4-122">attributeName</span><span class="sxs-lookup"><span data-stu-id="4c3b4-122">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c3b4-123">1</span><span class="sxs-lookup"><span data-stu-id="4c3b4-123">1</span></span></p></td>
<td><p><span data-ttu-id="4c3b4-124">明確化.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-124">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c3b4-125">両面</span><span class="sxs-lookup"><span data-stu-id="4c3b4-125">2</span></span></p></td>
<td><p><span data-ttu-id="4c3b4-126">状況.</span><span class="sxs-lookup"><span data-stu-id="4c3b4-126">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="4c3b4-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c3b4-127">See Also</span></span>


[<span data-ttu-id="4c3b4-128">Lync Server 2013 の tblNode</span><span class="sxs-lookup"><span data-stu-id="4c3b4-128">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

