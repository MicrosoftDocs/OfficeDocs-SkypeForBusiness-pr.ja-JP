---
title: 'Lync Server 2013: tblScopePrincipal'
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
ms.openlocfilehash: 17f6fad436234764bb1e081813a155472981172a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="9f465-102">Lync Server 2013 の tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="9f465-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f465-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="9f465-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="9f465-104">tblScopePrincipal には、ノードに割り当てられるスコープが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9f465-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="9f465-105">Columns</span><span class="sxs-lookup"><span data-stu-id="9f465-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f465-106">列</span><span class="sxs-lookup"><span data-stu-id="9f465-106">Column</span></span></th>
<th><span data-ttu-id="9f465-107">種類</span><span class="sxs-lookup"><span data-stu-id="9f465-107">Type</span></span></th>
<th><span data-ttu-id="9f465-108">説明</span><span class="sxs-lookup"><span data-stu-id="9f465-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f465-109">Scopeprincipal.scopenodeid</span><span class="sxs-lookup"><span data-stu-id="9f465-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="9f465-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="9f465-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9f465-111">範囲の適用先ノード ID。</span><span class="sxs-lookup"><span data-stu-id="9f465-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f465-112">Scopeprincipal.scopeprinid</span><span class="sxs-lookup"><span data-stu-id="9f465-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="9f465-113">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="9f465-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9f465-114">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="9f465-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f465-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="9f465-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="9f465-116">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="9f465-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="9f465-117">スコープの種類が [拒否] の場合は True、[許可] の場合は False。</span><span class="sxs-lookup"><span data-stu-id="9f465-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f465-118">scopeupdat</span><span class="sxs-lookup"><span data-stu-id="9f465-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="9f465-119">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="9f465-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9f465-120">このエントリを最後に更新したプリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="9f465-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="9f465-121">Keys</span><span class="sxs-lookup"><span data-stu-id="9f465-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f465-122">列</span><span class="sxs-lookup"><span data-stu-id="9f465-122">Column</span></span></th>
<th><span data-ttu-id="9f465-123">説明</span><span class="sxs-lookup"><span data-stu-id="9f465-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f465-124">&lt;Scopeprincipal.scopenodeid、scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="9f465-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="9f465-125">主キー。</span><span class="sxs-lookup"><span data-stu-id="9f465-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f465-126">Scopeprincipal.scopenodeid</span><span class="sxs-lookup"><span data-stu-id="9f465-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="9f465-127">tblNode.nodeID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="9f465-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f465-128">Scopeprincipal.scopeprinid</span><span class="sxs-lookup"><span data-stu-id="9f465-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="9f465-129">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="9f465-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

