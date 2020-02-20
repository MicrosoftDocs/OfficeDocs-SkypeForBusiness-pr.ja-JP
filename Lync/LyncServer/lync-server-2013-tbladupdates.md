---
title: 'Lync Server 2013: tblADUpdates'
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
ms.openlocfilehash: ee3f0d881e26c3d26773b1b59feca3d1d02665dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="c8cb9-102">Lync Server 2013 の tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="c8cb9-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8cb9-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="c8cb9-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="c8cb9-104">tblADUpdates には、以降の Active Directory 同期手順でまだ処理されていない Active Directory ドメインサービスの変更が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c8cb9-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="c8cb9-105">Columns</span><span class="sxs-lookup"><span data-stu-id="c8cb9-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8cb9-106">列</span><span class="sxs-lookup"><span data-stu-id="c8cb9-106">Column</span></span></th>
<th><span data-ttu-id="c8cb9-107">種類</span><span class="sxs-lookup"><span data-stu-id="c8cb9-107">Type</span></span></th>
<th><span data-ttu-id="c8cb9-108">説明</span><span class="sxs-lookup"><span data-stu-id="c8cb9-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8cb9-109">Principal.pringuid</span><span class="sxs-lookup"><span data-stu-id="c8cb9-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="c8cb9-110">NULL でない GUID</span><span class="sxs-lookup"><span data-stu-id="c8cb9-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="c8cb9-111">変更したオブジェクトのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="c8cb9-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8cb9-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="c8cb9-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="c8cb9-113">NULL でない nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="c8cb9-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="c8cb9-114">オブジェクトの識別名。</span><span class="sxs-lookup"><span data-stu-id="c8cb9-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8cb9-115">Prinattributes 変更</span><span class="sxs-lookup"><span data-stu-id="c8cb9-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="c8cb9-116">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="c8cb9-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="c8cb9-117">オブジェクトの属性が 1 つ以上変更された場合は True。</span><span class="sxs-lookup"><span data-stu-id="c8cb9-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8cb9-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="c8cb9-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="c8cb9-119">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="c8cb9-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="c8cb9-120">メンバーシップが変更された場合は True。</span><span class="sxs-lookup"><span data-stu-id="c8cb9-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8cb9-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="c8cb9-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="c8cb9-122">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="c8cb9-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="c8cb9-123">不使用。</span><span class="sxs-lookup"><span data-stu-id="c8cb9-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8cb9-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="c8cb9-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="c8cb9-125">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="c8cb9-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="c8cb9-126">オブジェクトが削除された場合は True。</span><span class="sxs-lookup"><span data-stu-id="c8cb9-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8cb9-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="c8cb9-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="c8cb9-128">NULL でない datetime</span><span class="sxs-lookup"><span data-stu-id="c8cb9-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="c8cb9-129">行が挿入された時点のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="c8cb9-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

