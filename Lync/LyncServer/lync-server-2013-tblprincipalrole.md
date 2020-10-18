---
title: 'Lync Server 2013: に tblprincipalrole'
description: 'Lync Server 2013: に tblprincipalrole。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58ffda3136c254ee77f14d33dcb42af5d172c4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573633"
---
# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="50bd4-103">Lync Server 2013 のに tblprincipalrole</span><span class="sxs-lookup"><span data-stu-id="50bd4-103">tblPrincipalRole in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50bd4-104">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="50bd4-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="50bd4-105">に tblprincipalrole には、ノードに割り当てられた明示的な役割が含まれます。</span><span class="sxs-lookup"><span data-stu-id="50bd4-105">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="50bd4-106">段組み</span><span class="sxs-lookup"><span data-stu-id="50bd4-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50bd4-107">Column</span><span class="sxs-lookup"><span data-stu-id="50bd4-107">Column</span></span></th>
<th><span data-ttu-id="50bd4-108">種類</span><span class="sxs-lookup"><span data-stu-id="50bd4-108">Type</span></span></th>
<th><span data-ttu-id="50bd4-109">説明</span><span class="sxs-lookup"><span data-stu-id="50bd4-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50bd4-110">Principalrole.prinrolenodeid</span><span class="sxs-lookup"><span data-stu-id="50bd4-110">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="50bd4-111">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="50bd4-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="50bd4-112">役割の適用先のノード ID。</span><span class="sxs-lookup"><span data-stu-id="50bd4-112">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50bd4-113">Principalrole.prinroleprinid</span><span class="sxs-lookup"><span data-stu-id="50bd4-113">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="50bd4-114">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="50bd4-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="50bd4-115">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="50bd4-115">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50bd4-116">Principalrole.prinroletypeid</span><span class="sxs-lookup"><span data-stu-id="50bd4-116">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="50bd4-117">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="50bd4-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="50bd4-118">役割の種類の ID (tblRoleType)。</span><span class="sxs-lookup"><span data-stu-id="50bd4-118">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50bd4-119">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="50bd4-119">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="50bd4-120">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="50bd4-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="50bd4-121">このエントリを最後に更新したプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="50bd4-121">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="50bd4-122">Keys</span><span class="sxs-lookup"><span data-stu-id="50bd4-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50bd4-123">列</span><span class="sxs-lookup"><span data-stu-id="50bd4-123">Column</span></span></th>
<th><span data-ttu-id="50bd4-124">説明</span><span class="sxs-lookup"><span data-stu-id="50bd4-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50bd4-125">&lt;prinRoleNodeID、prinRolePrinID、prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="50bd4-125">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="50bd4-126">主キー。</span><span class="sxs-lookup"><span data-stu-id="50bd4-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50bd4-127">Principalrole.prinrolenodeid</span><span class="sxs-lookup"><span data-stu-id="50bd4-127">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="50bd4-128">tblNode.nodeID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="50bd4-128">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50bd4-129">Principalrole.prinroleprinid</span><span class="sxs-lookup"><span data-stu-id="50bd4-129">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="50bd4-130">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="50bd4-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50bd4-131">Principalrole.prinroletypeid</span><span class="sxs-lookup"><span data-stu-id="50bd4-131">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="50bd4-132">TblRoleType テーブルに参照がある外部キー。</span><span class="sxs-lookup"><span data-stu-id="50bd4-132">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

