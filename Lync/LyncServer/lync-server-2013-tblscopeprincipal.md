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
ms.openlocfilehash: 72c6f15b2f0a219871436fe4451984abfddc947a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="4e13f-102">Lync Server 2013 の tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="4e13f-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e13f-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4e13f-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4e13f-104">tblScopePrincipal には、ノードに割り当てられたスコープが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4e13f-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="4e13f-105">行</span><span class="sxs-lookup"><span data-stu-id="4e13f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e13f-106">列</span><span class="sxs-lookup"><span data-stu-id="4e13f-106">Column</span></span></th>
<th><span data-ttu-id="4e13f-107">型</span><span class="sxs-lookup"><span data-stu-id="4e13f-107">Type</span></span></th>
<th><span data-ttu-id="4e13f-108">説明</span><span class="sxs-lookup"><span data-stu-id="4e13f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e13f-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="4e13f-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="4e13f-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="4e13f-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4e13f-111">スコープが適用されるノード ID。</span><span class="sxs-lookup"><span data-stu-id="4e13f-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e13f-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="4e13f-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="4e13f-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="4e13f-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4e13f-114">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="4e13f-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e13f-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="4e13f-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="4e13f-116">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="4e13f-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="4e13f-117">スコープの型が拒否された場合は True。許可する場合は False。</span><span class="sxs-lookup"><span data-stu-id="4e13f-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e13f-118">スコープ</span><span class="sxs-lookup"><span data-stu-id="4e13f-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="4e13f-119">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="4e13f-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4e13f-120">このエントリを最後に更新したプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="4e13f-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="4e13f-121">機能</span><span class="sxs-lookup"><span data-stu-id="4e13f-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e13f-122">列</span><span class="sxs-lookup"><span data-stu-id="4e13f-122">Column</span></span></th>
<th><span data-ttu-id="4e13f-123">説明</span><span class="sxs-lookup"><span data-stu-id="4e13f-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e13f-124">&lt;scopeNodeID、scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="4e13f-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="4e13f-125">主キー。</span><span class="sxs-lookup"><span data-stu-id="4e13f-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e13f-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="4e13f-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="4e13f-127">TblNode テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="4e13f-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e13f-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="4e13f-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="4e13f-129">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="4e13f-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

