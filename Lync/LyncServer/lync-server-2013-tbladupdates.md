---
title: 'Lync Server 2013: tblADUpdates'
description: 'Lync Server 2013: tblADUpdates。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ab4418a10eac283d0f39d09b1c1fe15a32b2e68
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573683"
---
# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="401d3-103">Lync Server 2013 の tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="401d3-103">tblADUpdates in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="401d3-104">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="401d3-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="401d3-105">tblADUpdates には、以降の Active Directory 同期手順でまだ処理されていない Active Directory ドメインサービスの変更が含まれています。</span><span class="sxs-lookup"><span data-stu-id="401d3-105">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="401d3-106">段組み</span><span class="sxs-lookup"><span data-stu-id="401d3-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="401d3-107">Column</span><span class="sxs-lookup"><span data-stu-id="401d3-107">Column</span></span></th>
<th><span data-ttu-id="401d3-108">種類</span><span class="sxs-lookup"><span data-stu-id="401d3-108">Type</span></span></th>
<th><span data-ttu-id="401d3-109">説明</span><span class="sxs-lookup"><span data-stu-id="401d3-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="401d3-110">Principal.pringuid</span><span class="sxs-lookup"><span data-stu-id="401d3-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="401d3-111">NULL でない GUID</span><span class="sxs-lookup"><span data-stu-id="401d3-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="401d3-112">変更したオブジェクトのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="401d3-112">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="401d3-113">prinADPath</span><span class="sxs-lookup"><span data-stu-id="401d3-113">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="401d3-114">NULL でない nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="401d3-114">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="401d3-115">オブジェクトの識別名。</span><span class="sxs-lookup"><span data-stu-id="401d3-115">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="401d3-116">Prinattributes 変更</span><span class="sxs-lookup"><span data-stu-id="401d3-116">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="401d3-117">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="401d3-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="401d3-118">オブジェクトの属性が 1 つ以上変更された場合は True。</span><span class="sxs-lookup"><span data-stu-id="401d3-118">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="401d3-119">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="401d3-119">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="401d3-120">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="401d3-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="401d3-121">メンバーシップが変更された場合は True。</span><span class="sxs-lookup"><span data-stu-id="401d3-121">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="401d3-122">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="401d3-122">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="401d3-123">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="401d3-123">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="401d3-124">不使用。</span><span class="sxs-lookup"><span data-stu-id="401d3-124">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="401d3-125">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="401d3-125">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="401d3-126">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="401d3-126">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="401d3-127">オブジェクトが削除された場合は True。</span><span class="sxs-lookup"><span data-stu-id="401d3-127">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="401d3-128">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="401d3-128">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="401d3-129">NULL でない datetime</span><span class="sxs-lookup"><span data-stu-id="401d3-129">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="401d3-130">行が挿入された時点のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="401d3-130">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

