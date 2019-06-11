---
title: 'Lync Server 2013: tblScopePrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ece5ae542060835aefa05edb6e08b766293e2ac1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="34877-102">Lync Server 2013 の tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="34877-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34877-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="34877-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="34877-104">tblScopePrincipal には、ノードに割り当てられたスコープが含まれます。</span><span class="sxs-lookup"><span data-stu-id="34877-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="34877-105">行</span><span class="sxs-lookup"><span data-stu-id="34877-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34877-106">列</span><span class="sxs-lookup"><span data-stu-id="34877-106">Column</span></span></th>
<th><span data-ttu-id="34877-107">型</span><span class="sxs-lookup"><span data-stu-id="34877-107">Type</span></span></th>
<th><span data-ttu-id="34877-108">説明</span><span class="sxs-lookup"><span data-stu-id="34877-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34877-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="34877-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="34877-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="34877-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="34877-111">スコープが適用されるノード ID。</span><span class="sxs-lookup"><span data-stu-id="34877-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34877-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="34877-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="34877-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="34877-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="34877-114">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="34877-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34877-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="34877-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="34877-116">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="34877-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="34877-117">スコープの型が拒否された場合は True。許可する場合は False。</span><span class="sxs-lookup"><span data-stu-id="34877-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34877-118">スコープ</span><span class="sxs-lookup"><span data-stu-id="34877-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="34877-119">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="34877-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="34877-120">このエントリを最後に更新したプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="34877-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="34877-121">機能</span><span class="sxs-lookup"><span data-stu-id="34877-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34877-122">列</span><span class="sxs-lookup"><span data-stu-id="34877-122">Column</span></span></th>
<th><span data-ttu-id="34877-123">説明</span><span class="sxs-lookup"><span data-stu-id="34877-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34877-124">&lt;scopeNodeID、scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="34877-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="34877-125">主キー。</span><span class="sxs-lookup"><span data-stu-id="34877-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34877-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="34877-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="34877-127">TblNode テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="34877-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34877-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="34877-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="34877-129">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="34877-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

