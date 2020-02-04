---
title: 'Lync Server 2013: tblPrincipalRole'
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
ms.openlocfilehash: de125c0f314bd0ba72b9bbd463201b12d3e19eea
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="09c9c-102">Lync Server 2013 の tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="09c9c-102">tblPrincipalRole in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09c9c-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="09c9c-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="09c9c-104">tblPrincipalRole には、ノードに割り当てられている明示的な役割が含まれます。</span><span class="sxs-lookup"><span data-stu-id="09c9c-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="09c9c-105">行</span><span class="sxs-lookup"><span data-stu-id="09c9c-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09c9c-106">列</span><span class="sxs-lookup"><span data-stu-id="09c9c-106">Column</span></span></th>
<th><span data-ttu-id="09c9c-107">型</span><span class="sxs-lookup"><span data-stu-id="09c9c-107">Type</span></span></th>
<th><span data-ttu-id="09c9c-108">説明</span><span class="sxs-lookup"><span data-stu-id="09c9c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09c9c-109">Prinrolid</span><span class="sxs-lookup"><span data-stu-id="09c9c-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="09c9c-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="09c9c-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="09c9c-111">役割が適用されるノード ID。</span><span class="sxs-lookup"><span data-stu-id="09c9c-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09c9c-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="09c9c-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="09c9c-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="09c9c-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="09c9c-114">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="09c9c-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09c9c-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="09c9c-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="09c9c-116">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="09c9c-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="09c9c-117">役割の種類の ID (tblRoleType から)。</span><span class="sxs-lookup"><span data-stu-id="09c9c-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09c9c-118">prinroleupdat</span><span class="sxs-lookup"><span data-stu-id="09c9c-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="09c9c-119">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="09c9c-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="09c9c-120">このエントリを最後に更新したプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="09c9c-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="09c9c-121">機能</span><span class="sxs-lookup"><span data-stu-id="09c9c-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09c9c-122">列</span><span class="sxs-lookup"><span data-stu-id="09c9c-122">Column</span></span></th>
<th><span data-ttu-id="09c9c-123">説明</span><span class="sxs-lookup"><span data-stu-id="09c9c-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09c9c-124">&lt;Prinroldeid、prinRolePrinID、prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="09c9c-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="09c9c-125">主キー。</span><span class="sxs-lookup"><span data-stu-id="09c9c-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09c9c-126">Prinrolid</span><span class="sxs-lookup"><span data-stu-id="09c9c-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="09c9c-127">TblNode テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="09c9c-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09c9c-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="09c9c-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="09c9c-129">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="09c9c-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09c9c-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="09c9c-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="09c9c-131">TblRoleType の Typeid テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="09c9c-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

