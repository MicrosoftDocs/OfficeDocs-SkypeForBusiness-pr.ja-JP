---
title: 'Lync Server 2013: そして tblprincipalinvites'
description: 'Lync Server 2013: そして tblprincipalinvites。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48184141
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d30d741864ed2a3cfbec8329215be33c21b3b262
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564673"
---
# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="43679-103">Lync Server 2013 のそして tblprincipalinvites</span><span class="sxs-lookup"><span data-stu-id="43679-103">tblPrincipalInvites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43679-104">_**トピックの最終更新日:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="43679-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="43679-105">tblPrincipalInvites には、自動招待が有効になっているすべてのノードのプロビジョニングされた全ユーザーの招待が含まれます。</span><span class="sxs-lookup"><span data-stu-id="43679-105">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="43679-106">段組み</span><span class="sxs-lookup"><span data-stu-id="43679-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43679-107">Column</span><span class="sxs-lookup"><span data-stu-id="43679-107">Column</span></span></th>
<th><span data-ttu-id="43679-108">種類</span><span class="sxs-lookup"><span data-stu-id="43679-108">Type</span></span></th>
<th><span data-ttu-id="43679-109">説明</span><span class="sxs-lookup"><span data-stu-id="43679-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43679-110">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="43679-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="43679-111">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="43679-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="43679-112">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="43679-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43679-113">invID</span><span class="sxs-lookup"><span data-stu-id="43679-113">invID</span></span></p></td>
<td><p><span data-ttu-id="43679-114">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="43679-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="43679-115">tblLastInviteId テーブルから生成された (プリンシパル ID ごとの) 一意のシーケンシャル番号。</span><span class="sxs-lookup"><span data-stu-id="43679-115">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43679-116">nodeID</span><span class="sxs-lookup"><span data-stu-id="43679-116">nodeID</span></span></p></td>
<td><p><span data-ttu-id="43679-117">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="43679-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="43679-118">ノード ID (チャット ルームのみ)。</span><span class="sxs-lookup"><span data-stu-id="43679-118">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43679-119">createdOn</span><span class="sxs-lookup"><span data-stu-id="43679-119">createdOn</span></span></p></td>
<td><p><span data-ttu-id="43679-120">NULL でない datetime</span><span class="sxs-lookup"><span data-stu-id="43679-120">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="43679-121">作成の時刻。</span><span class="sxs-lookup"><span data-stu-id="43679-121">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="43679-122">Keys</span><span class="sxs-lookup"><span data-stu-id="43679-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43679-123">列</span><span class="sxs-lookup"><span data-stu-id="43679-123">Column</span></span></th>
<th><span data-ttu-id="43679-124">説明</span><span class="sxs-lookup"><span data-stu-id="43679-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43679-125">&lt;prinID, nodeID&gt;</span><span class="sxs-lookup"><span data-stu-id="43679-125">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="43679-126">主キー。</span><span class="sxs-lookup"><span data-stu-id="43679-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43679-127">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="43679-127">prinID</span></span></p></td>
<td><p><span data-ttu-id="43679-128">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="43679-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43679-129">nodeID</span><span class="sxs-lookup"><span data-stu-id="43679-129">nodeID</span></span></p></td>
<td><p><span data-ttu-id="43679-130">tblNode.nodeID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="43679-130">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

