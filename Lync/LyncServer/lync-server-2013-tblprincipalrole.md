---
title: 'Lync Server 2013: に tblprincipalrole'
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
ms.openlocfilehash: 685e8ae3e767e3dc237da1698fd593a9c56021c8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="77814-102">Lync Server 2013 のに tblprincipalrole</span><span class="sxs-lookup"><span data-stu-id="77814-102">tblPrincipalRole in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77814-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="77814-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="77814-104">に tblprincipalrole には、ノードに割り当てられた明示的な役割が含まれます。</span><span class="sxs-lookup"><span data-stu-id="77814-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="77814-105">Columns</span><span class="sxs-lookup"><span data-stu-id="77814-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="77814-106">列</span><span class="sxs-lookup"><span data-stu-id="77814-106">Column</span></span></th>
<th><span data-ttu-id="77814-107">種類</span><span class="sxs-lookup"><span data-stu-id="77814-107">Type</span></span></th>
<th><span data-ttu-id="77814-108">説明</span><span class="sxs-lookup"><span data-stu-id="77814-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77814-109">Principalrole.prinrolenodeid</span><span class="sxs-lookup"><span data-stu-id="77814-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="77814-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="77814-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="77814-111">役割の適用先のノード ID。</span><span class="sxs-lookup"><span data-stu-id="77814-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77814-112">Principalrole.prinroleprinid</span><span class="sxs-lookup"><span data-stu-id="77814-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="77814-113">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="77814-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="77814-114">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="77814-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77814-115">Principalrole.prinroletypeid</span><span class="sxs-lookup"><span data-stu-id="77814-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="77814-116">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="77814-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="77814-117">役割の種類の ID (tblRoleType)。</span><span class="sxs-lookup"><span data-stu-id="77814-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77814-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="77814-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="77814-119">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="77814-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="77814-120">このエントリを最後に更新したプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="77814-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="77814-121">Keys</span><span class="sxs-lookup"><span data-stu-id="77814-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="77814-122">列</span><span class="sxs-lookup"><span data-stu-id="77814-122">Column</span></span></th>
<th><span data-ttu-id="77814-123">説明</span><span class="sxs-lookup"><span data-stu-id="77814-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77814-124">&lt;prinRoleNodeID、prinRolePrinID、prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="77814-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="77814-125">主キー。</span><span class="sxs-lookup"><span data-stu-id="77814-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77814-126">Principalrole.prinrolenodeid</span><span class="sxs-lookup"><span data-stu-id="77814-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="77814-127">tblNode.nodeID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="77814-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77814-128">Principalrole.prinroleprinid</span><span class="sxs-lookup"><span data-stu-id="77814-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="77814-129">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="77814-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77814-130">Principalrole.prinroletypeid</span><span class="sxs-lookup"><span data-stu-id="77814-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="77814-131">TblRoleType テーブルに参照がある外部キー。</span><span class="sxs-lookup"><span data-stu-id="77814-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

