---
title: 'Lync Server 2013: tblScopePrincipal'
description: 'Lync Server 2013: tblScopePrincipal。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63315f8525e5c2f05fe54a0f9ed9e8a97b9e8bce
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555613"
---
# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="f826f-103">Lync Server 2013 の tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="f826f-103">tblScopePrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f826f-104">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f826f-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f826f-105">tblScopePrincipal には、ノードに割り当てられるスコープが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f826f-105">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="f826f-106">段組み</span><span class="sxs-lookup"><span data-stu-id="f826f-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f826f-107">Column</span><span class="sxs-lookup"><span data-stu-id="f826f-107">Column</span></span></th>
<th><span data-ttu-id="f826f-108">種類</span><span class="sxs-lookup"><span data-stu-id="f826f-108">Type</span></span></th>
<th><span data-ttu-id="f826f-109">説明</span><span class="sxs-lookup"><span data-stu-id="f826f-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f826f-110">Scopeprincipal.scopenodeid</span><span class="sxs-lookup"><span data-stu-id="f826f-110">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="f826f-111">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="f826f-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f826f-112">範囲の適用先ノード ID。</span><span class="sxs-lookup"><span data-stu-id="f826f-112">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f826f-113">Scopeprincipal.scopeprinid</span><span class="sxs-lookup"><span data-stu-id="f826f-113">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="f826f-114">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="f826f-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f826f-115">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="f826f-115">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f826f-116">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="f826f-116">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="f826f-117">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="f826f-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f826f-118">スコープの種類が [拒否] の場合は True、[許可] の場合は False。</span><span class="sxs-lookup"><span data-stu-id="f826f-118">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f826f-119">scopeupdat</span><span class="sxs-lookup"><span data-stu-id="f826f-119">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="f826f-120">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="f826f-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f826f-121">このエントリを最後に更新したプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="f826f-121">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="f826f-122">Keys</span><span class="sxs-lookup"><span data-stu-id="f826f-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f826f-123">列</span><span class="sxs-lookup"><span data-stu-id="f826f-123">Column</span></span></th>
<th><span data-ttu-id="f826f-124">説明</span><span class="sxs-lookup"><span data-stu-id="f826f-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f826f-125">&lt;Scopeprincipal.scopenodeid、scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="f826f-125">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="f826f-126">主キー。</span><span class="sxs-lookup"><span data-stu-id="f826f-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f826f-127">Scopeprincipal.scopenodeid</span><span class="sxs-lookup"><span data-stu-id="f826f-127">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="f826f-128">tblNode.nodeID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="f826f-128">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f826f-129">Scopeprincipal.scopeprinid</span><span class="sxs-lookup"><span data-stu-id="f826f-129">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="f826f-130">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="f826f-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

