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
ms.openlocfilehash: ad3ef2afaa162219d140a4eaef204dc6e1e2ab02
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="cd7a0-102">Lync Server 2013 の tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="cd7a0-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd7a0-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="cd7a0-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="cd7a0-104">tblADUpdates には、以降の Active Directory 同期手順でまだ処理されていない Active Directory ドメインサービスの変更が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd7a0-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="cd7a0-105">Columns</span><span class="sxs-lookup"><span data-stu-id="cd7a0-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd7a0-106">列</span><span class="sxs-lookup"><span data-stu-id="cd7a0-106">Column</span></span></th>
<th><span data-ttu-id="cd7a0-107">種類</span><span class="sxs-lookup"><span data-stu-id="cd7a0-107">Type</span></span></th>
<th><span data-ttu-id="cd7a0-108">説明</span><span class="sxs-lookup"><span data-stu-id="cd7a0-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd7a0-109">Principal.pringuid</span><span class="sxs-lookup"><span data-stu-id="cd7a0-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="cd7a0-110">NULL でない GUID</span><span class="sxs-lookup"><span data-stu-id="cd7a0-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="cd7a0-111">変更したオブジェクトのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="cd7a0-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd7a0-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="cd7a0-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="cd7a0-113">NULL でない nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="cd7a0-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="cd7a0-114">オブジェクトの識別名。</span><span class="sxs-lookup"><span data-stu-id="cd7a0-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd7a0-115">Prinattributes 変更</span><span class="sxs-lookup"><span data-stu-id="cd7a0-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="cd7a0-116">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="cd7a0-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="cd7a0-117">オブジェクトの属性が 1 つ以上変更された場合は True。</span><span class="sxs-lookup"><span data-stu-id="cd7a0-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd7a0-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="cd7a0-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="cd7a0-119">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="cd7a0-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="cd7a0-120">メンバーシップが変更された場合は True。</span><span class="sxs-lookup"><span data-stu-id="cd7a0-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd7a0-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="cd7a0-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="cd7a0-122">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="cd7a0-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="cd7a0-123">不使用。</span><span class="sxs-lookup"><span data-stu-id="cd7a0-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd7a0-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="cd7a0-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="cd7a0-125">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="cd7a0-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="cd7a0-126">オブジェクトが削除された場合は True。</span><span class="sxs-lookup"><span data-stu-id="cd7a0-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd7a0-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="cd7a0-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="cd7a0-128">NULL でない datetime</span><span class="sxs-lookup"><span data-stu-id="cd7a0-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="cd7a0-129">行が挿入された時点のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="cd7a0-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

