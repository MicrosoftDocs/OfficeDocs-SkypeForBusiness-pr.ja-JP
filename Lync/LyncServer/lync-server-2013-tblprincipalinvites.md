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
ms.openlocfilehash: cd93043a9120a6de5a0f1da6ad3af64a2a6d38f7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523724"
---
# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="cad6c-102">Lync Server 2013 のそして tblprincipalinvites</span><span class="sxs-lookup"><span data-stu-id="cad6c-102">tblPrincipalInvites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cad6c-103">_**トピックの最終更新日:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="cad6c-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="cad6c-104">tblPrincipalInvites には、自動招待が有効になっているすべてのノードのプロビジョニングされた全ユーザーの招待が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cad6c-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="cad6c-105">段組み</span><span class="sxs-lookup"><span data-stu-id="cad6c-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cad6c-106">Column</span><span class="sxs-lookup"><span data-stu-id="cad6c-106">Column</span></span></th>
<th><span data-ttu-id="cad6c-107">種類</span><span class="sxs-lookup"><span data-stu-id="cad6c-107">Type</span></span></th>
<th><span data-ttu-id="cad6c-108">説明</span><span class="sxs-lookup"><span data-stu-id="cad6c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cad6c-109">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="cad6c-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="cad6c-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="cad6c-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="cad6c-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="cad6c-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cad6c-112">invID</span><span class="sxs-lookup"><span data-stu-id="cad6c-112">invID</span></span></p></td>
<td><p><span data-ttu-id="cad6c-113">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="cad6c-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="cad6c-114">tblLastInviteId テーブルから生成された (プリンシパル ID ごとの) 一意のシーケンシャル番号。</span><span class="sxs-lookup"><span data-stu-id="cad6c-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cad6c-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="cad6c-115">nodeID</span></span></p></td>
<td><p><span data-ttu-id="cad6c-116">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="cad6c-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="cad6c-117">ノード ID (チャット ルームのみ)。</span><span class="sxs-lookup"><span data-stu-id="cad6c-117">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cad6c-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="cad6c-118">createdOn</span></span></p></td>
<td><p><span data-ttu-id="cad6c-119">NULL でない datetime</span><span class="sxs-lookup"><span data-stu-id="cad6c-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="cad6c-120">作成の時刻。</span><span class="sxs-lookup"><span data-stu-id="cad6c-120">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="cad6c-121">Keys</span><span class="sxs-lookup"><span data-stu-id="cad6c-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cad6c-122">列</span><span class="sxs-lookup"><span data-stu-id="cad6c-122">Column</span></span></th>
<th><span data-ttu-id="cad6c-123">説明</span><span class="sxs-lookup"><span data-stu-id="cad6c-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cad6c-124">&lt;prinID, nodeID&gt;</span><span class="sxs-lookup"><span data-stu-id="cad6c-124">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="cad6c-125">主キー。</span><span class="sxs-lookup"><span data-stu-id="cad6c-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cad6c-126">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="cad6c-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="cad6c-127">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="cad6c-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cad6c-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="cad6c-128">nodeID</span></span></p></td>
<td><p><span data-ttu-id="cad6c-129">tblNode.nodeID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="cad6c-129">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

