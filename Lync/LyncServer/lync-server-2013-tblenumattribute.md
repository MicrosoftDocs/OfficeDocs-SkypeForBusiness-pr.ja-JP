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
ms.openlocfilehash: 67bce18c46b4286afe287ab04a76b71e73b7a5a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="dc6b7-102">Lync Server 2013 の tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="dc6b7-102">tblEnumAttribute in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc6b7-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="dc6b7-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="dc6b7-104">tblEnumAttribute は、Node テーブルで使用される表示および動作属性を含むハードコードされたテーブルです。</span><span class="sxs-lookup"><span data-stu-id="dc6b7-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="dc6b7-105">Columns</span><span class="sxs-lookup"><span data-stu-id="dc6b7-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc6b7-106">列</span><span class="sxs-lookup"><span data-stu-id="dc6b7-106">Column</span></span></th>
<th><span data-ttu-id="dc6b7-107">種類</span><span class="sxs-lookup"><span data-stu-id="dc6b7-107">Type</span></span></th>
<th><span data-ttu-id="dc6b7-108">説明</span><span class="sxs-lookup"><span data-stu-id="dc6b7-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc6b7-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="dc6b7-109">attributeID</span></span></p></td>
<td><p><span data-ttu-id="dc6b7-110">NULL でない smallint</span><span class="sxs-lookup"><span data-stu-id="dc6b7-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="dc6b7-111">属性の ID。</span><span class="sxs-lookup"><span data-stu-id="dc6b7-111">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc6b7-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="dc6b7-112">attributeName</span></span></p></td>
<td><p><span data-ttu-id="dc6b7-113">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="dc6b7-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="dc6b7-114">属性の名前。</span><span class="sxs-lookup"><span data-stu-id="dc6b7-114">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="dc6b7-115">キー</span><span class="sxs-lookup"><span data-stu-id="dc6b7-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc6b7-116">列</span><span class="sxs-lookup"><span data-stu-id="dc6b7-116">Column</span></span></th>
<th><span data-ttu-id="dc6b7-117">説明</span><span class="sxs-lookup"><span data-stu-id="dc6b7-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc6b7-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="dc6b7-118">attributeID</span></span></p></td>
<td><p><span data-ttu-id="dc6b7-119">主キー。</span><span class="sxs-lookup"><span data-stu-id="dc6b7-119">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="dc6b7-120">テーブル値</span><span class="sxs-lookup"><span data-stu-id="dc6b7-120">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc6b7-121">attributeID</span><span class="sxs-lookup"><span data-stu-id="dc6b7-121">attributeID</span></span></th>
<th><span data-ttu-id="dc6b7-122">attributeName</span><span class="sxs-lookup"><span data-stu-id="dc6b7-122">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc6b7-123">1-d</span><span class="sxs-lookup"><span data-stu-id="dc6b7-123">1</span></span></p></td>
<td><p><span data-ttu-id="dc6b7-124">表示.</span><span class="sxs-lookup"><span data-stu-id="dc6b7-124">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc6b7-125">pbm-2</span><span class="sxs-lookup"><span data-stu-id="dc6b7-125">2</span></span></p></td>
<td><p><span data-ttu-id="dc6b7-126">Behavior.</span><span class="sxs-lookup"><span data-stu-id="dc6b7-126">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="dc6b7-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc6b7-127">See Also</span></span>


[<span data-ttu-id="dc6b7-128">Lync Server 2013 の tblNode</span><span class="sxs-lookup"><span data-stu-id="dc6b7-128">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

