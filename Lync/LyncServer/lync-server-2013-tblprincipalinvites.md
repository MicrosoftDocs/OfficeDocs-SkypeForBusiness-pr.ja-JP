---
title: 'Lync Server 2013: そして tblprincipalinvites'
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
ms.openlocfilehash: a4316e86d29013587b2302d18a840a4a1859f9ad
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="63823-102">Lync Server 2013 のそして tblprincipalinvites</span><span class="sxs-lookup"><span data-stu-id="63823-102">tblPrincipalInvites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63823-103">_**トピックの最終更新日:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="63823-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="63823-104">tblPrincipalInvites には、自動招待が有効になっているすべてのノードのプロビジョニングされた全ユーザーの招待が含まれます。</span><span class="sxs-lookup"><span data-stu-id="63823-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="63823-105">Columns</span><span class="sxs-lookup"><span data-stu-id="63823-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63823-106">列</span><span class="sxs-lookup"><span data-stu-id="63823-106">Column</span></span></th>
<th><span data-ttu-id="63823-107">種類</span><span class="sxs-lookup"><span data-stu-id="63823-107">Type</span></span></th>
<th><span data-ttu-id="63823-108">説明</span><span class="sxs-lookup"><span data-stu-id="63823-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63823-109">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="63823-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="63823-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="63823-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="63823-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="63823-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63823-112">invID</span><span class="sxs-lookup"><span data-stu-id="63823-112">invID</span></span></p></td>
<td><p><span data-ttu-id="63823-113">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="63823-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="63823-114">tblLastInviteId テーブルから生成された (プリンシパル ID ごとの) 一意のシーケンシャル番号。</span><span class="sxs-lookup"><span data-stu-id="63823-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63823-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="63823-115">nodeID</span></span></p></td>
<td><p><span data-ttu-id="63823-116">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="63823-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="63823-117">ノード ID (チャット ルームのみ)。</span><span class="sxs-lookup"><span data-stu-id="63823-117">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63823-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="63823-118">createdOn</span></span></p></td>
<td><p><span data-ttu-id="63823-119">NULL でない datetime</span><span class="sxs-lookup"><span data-stu-id="63823-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="63823-120">作成の時刻。</span><span class="sxs-lookup"><span data-stu-id="63823-120">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="63823-121">Keys</span><span class="sxs-lookup"><span data-stu-id="63823-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63823-122">列</span><span class="sxs-lookup"><span data-stu-id="63823-122">Column</span></span></th>
<th><span data-ttu-id="63823-123">説明</span><span class="sxs-lookup"><span data-stu-id="63823-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63823-124">&lt;prinID, nodeID&gt;</span><span class="sxs-lookup"><span data-stu-id="63823-124">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="63823-125">主キー。</span><span class="sxs-lookup"><span data-stu-id="63823-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63823-126">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="63823-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="63823-127">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="63823-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63823-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="63823-128">nodeID</span></span></p></td>
<td><p><span data-ttu-id="63823-129">tblNode.nodeID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="63823-129">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

