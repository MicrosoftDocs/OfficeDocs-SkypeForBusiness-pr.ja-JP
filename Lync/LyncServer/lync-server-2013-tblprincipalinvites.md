---
title: 'Lync Server 2013: tblPrincipalInvites'
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
ms.openlocfilehash: 75d842772c8c0e02352eacf7f80711aa79c29461
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="9c516-102">Lync Server 2013 の tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="9c516-102">tblPrincipalInvites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c516-103">_**最終更新日:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="9c516-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="9c516-104">tblPrincipalInvites には、自動招待を含むすべてのノードのプロビジョニングされたすべてのユーザーの招待が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9c516-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="9c516-105">行</span><span class="sxs-lookup"><span data-stu-id="9c516-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c516-106">列</span><span class="sxs-lookup"><span data-stu-id="9c516-106">Column</span></span></th>
<th><span data-ttu-id="9c516-107">型</span><span class="sxs-lookup"><span data-stu-id="9c516-107">Type</span></span></th>
<th><span data-ttu-id="9c516-108">説明</span><span class="sxs-lookup"><span data-stu-id="9c516-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c516-109">prinID</span><span class="sxs-lookup"><span data-stu-id="9c516-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="9c516-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="9c516-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9c516-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="9c516-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c516-112">invID</span><span class="sxs-lookup"><span data-stu-id="9c516-112">invID</span></span></p></td>
<td><p><span data-ttu-id="9c516-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="9c516-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9c516-114">TblLastInviteId テーブルから生成された一意の連続番号 (プリンシパル ID ごと)。</span><span class="sxs-lookup"><span data-stu-id="9c516-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c516-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="9c516-115">nodeID</span></span></p></td>
<td><p><span data-ttu-id="9c516-116">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="9c516-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9c516-117">ノード ID (チャットルームのみ)。</span><span class="sxs-lookup"><span data-stu-id="9c516-117">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c516-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="9c516-118">createdOn</span></span></p></td>
<td><p><span data-ttu-id="9c516-119">datetime。 null ではありません</span><span class="sxs-lookup"><span data-stu-id="9c516-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="9c516-120">作成時刻。</span><span class="sxs-lookup"><span data-stu-id="9c516-120">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="9c516-121">機能</span><span class="sxs-lookup"><span data-stu-id="9c516-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c516-122">列</span><span class="sxs-lookup"><span data-stu-id="9c516-122">Column</span></span></th>
<th><span data-ttu-id="9c516-123">説明</span><span class="sxs-lookup"><span data-stu-id="9c516-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c516-124">&lt;prinID、nodeID&gt;</span><span class="sxs-lookup"><span data-stu-id="9c516-124">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="9c516-125">主キー。</span><span class="sxs-lookup"><span data-stu-id="9c516-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c516-126">prinID</span><span class="sxs-lookup"><span data-stu-id="9c516-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="9c516-127">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="9c516-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c516-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="9c516-128">nodeID</span></span></p></td>
<td><p><span data-ttu-id="9c516-129">TblNode テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="9c516-129">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

