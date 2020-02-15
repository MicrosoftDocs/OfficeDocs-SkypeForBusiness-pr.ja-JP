---
title: 'Lync Server 2013: tblPrincipalMeta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a3571cd93ae5d69fa4a432035284b9a752287b1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="87e2f-102">Lync Server 2013 の tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="87e2f-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87e2f-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="87e2f-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="87e2f-104">tblPrincipalMeta には、Active Directory ドメインサービスから更新する必要があるプリンシパルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="87e2f-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="87e2f-105">Columns</span><span class="sxs-lookup"><span data-stu-id="87e2f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87e2f-106">列</span><span class="sxs-lookup"><span data-stu-id="87e2f-106">Column</span></span></th>
<th><span data-ttu-id="87e2f-107">種類</span><span class="sxs-lookup"><span data-stu-id="87e2f-107">Type</span></span></th>
<th><span data-ttu-id="87e2f-108">説明</span><span class="sxs-lookup"><span data-stu-id="87e2f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87e2f-109">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="87e2f-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="87e2f-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="87e2f-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="87e2f-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="87e2f-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87e2f-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="87e2f-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="87e2f-113">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="87e2f-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="87e2f-114">プリンシパルの所属を最新の情報に更新する必要がある場合は True。</span><span class="sxs-lookup"><span data-stu-id="87e2f-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87e2f-115">Prinattributes ダーティ</span><span class="sxs-lookup"><span data-stu-id="87e2f-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="87e2f-116">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="87e2f-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="87e2f-117">プリンシパル属性を最新の情報に更新する必要がある場合は True。</span><span class="sxs-lookup"><span data-stu-id="87e2f-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87e2f-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="87e2f-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="87e2f-119">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="87e2f-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="87e2f-120">プリンシパルが削除されている場合は True。</span><span class="sxs-lookup"><span data-stu-id="87e2f-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87e2f-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="87e2f-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="87e2f-122">int</span><span class="sxs-lookup"><span data-stu-id="87e2f-122">int</span></span></p></td>
<td><p><span data-ttu-id="87e2f-123">それまでに行われた AD DS からプリンシパルを更新する試行の数。</span><span class="sxs-lookup"><span data-stu-id="87e2f-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87e2f-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="87e2f-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="87e2f-125">日付型</span><span class="sxs-lookup"><span data-stu-id="87e2f-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="87e2f-p101">プリンシパルを最新の情報に更新する最新の試行からのタイム スタンプ。最新の情報への更新をまだ試みていない場合は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="87e2f-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87e2f-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="87e2f-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="87e2f-129">日付型</span><span class="sxs-lookup"><span data-stu-id="87e2f-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="87e2f-p102">次にスケジュールされている最新の情報への更新のタイム スタンプ。最新の情報への更新がスケジュールされていない場合は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="87e2f-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="87e2f-132">Keys</span><span class="sxs-lookup"><span data-stu-id="87e2f-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87e2f-133">列</span><span class="sxs-lookup"><span data-stu-id="87e2f-133">Column</span></span></th>
<th><span data-ttu-id="87e2f-134">説明</span><span class="sxs-lookup"><span data-stu-id="87e2f-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87e2f-135">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="87e2f-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="87e2f-136">主キー。</span><span class="sxs-lookup"><span data-stu-id="87e2f-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87e2f-137">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="87e2f-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="87e2f-138">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="87e2f-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

