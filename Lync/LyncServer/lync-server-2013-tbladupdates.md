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
ms.openlocfilehash: 27fbbc6bb2fe68c2f4bfff91b999934069548d00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509484"
---
# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="3404e-102">Lync Server 2013 の tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="3404e-102">tblADUpdates in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3404e-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="3404e-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="3404e-104">tblADUpdates には、以降の Active Directory 同期手順でまだ処理されていない Active Directory ドメインサービスの変更が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3404e-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="3404e-105">段組み</span><span class="sxs-lookup"><span data-stu-id="3404e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3404e-106">Column</span><span class="sxs-lookup"><span data-stu-id="3404e-106">Column</span></span></th>
<th><span data-ttu-id="3404e-107">種類</span><span class="sxs-lookup"><span data-stu-id="3404e-107">Type</span></span></th>
<th><span data-ttu-id="3404e-108">説明</span><span class="sxs-lookup"><span data-stu-id="3404e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3404e-109">Principal.pringuid</span><span class="sxs-lookup"><span data-stu-id="3404e-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="3404e-110">NULL でない GUID</span><span class="sxs-lookup"><span data-stu-id="3404e-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="3404e-111">変更したオブジェクトのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="3404e-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3404e-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="3404e-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="3404e-113">NULL でない nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="3404e-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="3404e-114">オブジェクトの識別名。</span><span class="sxs-lookup"><span data-stu-id="3404e-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3404e-115">Prinattributes 変更</span><span class="sxs-lookup"><span data-stu-id="3404e-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="3404e-116">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="3404e-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="3404e-117">オブジェクトの属性が 1 つ以上変更された場合は True。</span><span class="sxs-lookup"><span data-stu-id="3404e-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3404e-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="3404e-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="3404e-119">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="3404e-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="3404e-120">メンバーシップが変更された場合は True。</span><span class="sxs-lookup"><span data-stu-id="3404e-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3404e-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="3404e-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="3404e-122">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="3404e-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="3404e-123">不使用。</span><span class="sxs-lookup"><span data-stu-id="3404e-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3404e-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="3404e-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="3404e-125">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="3404e-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="3404e-126">オブジェクトが削除された場合は True。</span><span class="sxs-lookup"><span data-stu-id="3404e-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3404e-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="3404e-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="3404e-128">NULL でない datetime</span><span class="sxs-lookup"><span data-stu-id="3404e-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="3404e-129">行が挿入された時点のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="3404e-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

