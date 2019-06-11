---
title: 'Lync Server 2013: tblPrincipalInvites'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48184141
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1081dbec8575eac0cc2aca7fc434b5801668f447
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="d8b4a-102">Lync Server 2013 の tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="d8b4a-102">tblPrincipalInvites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8b4a-103">_**最終更新日:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="d8b4a-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="d8b4a-104">tblPrincipalInvites には、自動招待を含むすべてのノードのプロビジョニングされたすべてのユーザーの招待が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d8b4a-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="d8b4a-105">行</span><span class="sxs-lookup"><span data-stu-id="d8b4a-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8b4a-106">列</span><span class="sxs-lookup"><span data-stu-id="d8b4a-106">Column</span></span></th>
<th><span data-ttu-id="d8b4a-107">型</span><span class="sxs-lookup"><span data-stu-id="d8b4a-107">Type</span></span></th>
<th><span data-ttu-id="d8b4a-108">説明</span><span class="sxs-lookup"><span data-stu-id="d8b4a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8b4a-109">prinID</span><span class="sxs-lookup"><span data-stu-id="d8b4a-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="d8b4a-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="d8b4a-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d8b4a-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="d8b4a-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b4a-112">invID</span><span class="sxs-lookup"><span data-stu-id="d8b4a-112">invID</span></span></p></td>
<td><p><span data-ttu-id="d8b4a-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="d8b4a-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d8b4a-114">TblLastInviteId テーブルから生成された一意の連続番号 (プリンシパル ID ごと)。</span><span class="sxs-lookup"><span data-stu-id="d8b4a-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b4a-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="d8b4a-115">nodeID</span></span></p></td>
<td><p><span data-ttu-id="d8b4a-116">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="d8b4a-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d8b4a-117">ノード ID (チャットルームのみ)。</span><span class="sxs-lookup"><span data-stu-id="d8b4a-117">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b4a-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="d8b4a-118">createdOn</span></span></p></td>
<td><p><span data-ttu-id="d8b4a-119">datetime。 null ではありません</span><span class="sxs-lookup"><span data-stu-id="d8b4a-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="d8b4a-120">作成時刻。</span><span class="sxs-lookup"><span data-stu-id="d8b4a-120">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="d8b4a-121">機能</span><span class="sxs-lookup"><span data-stu-id="d8b4a-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8b4a-122">列</span><span class="sxs-lookup"><span data-stu-id="d8b4a-122">Column</span></span></th>
<th><span data-ttu-id="d8b4a-123">説明</span><span class="sxs-lookup"><span data-stu-id="d8b4a-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8b4a-124">&lt;prinID、nodeID&gt;</span><span class="sxs-lookup"><span data-stu-id="d8b4a-124">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="d8b4a-125">主キー。</span><span class="sxs-lookup"><span data-stu-id="d8b4a-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8b4a-126">prinID</span><span class="sxs-lookup"><span data-stu-id="d8b4a-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="d8b4a-127">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="d8b4a-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8b4a-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="d8b4a-128">nodeID</span></span></p></td>
<td><p><span data-ttu-id="d8b4a-129">TblNode テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="d8b4a-129">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

