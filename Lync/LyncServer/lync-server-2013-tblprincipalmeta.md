---
title: 'Lync Server 2013: tblPrincipalMeta'
description: 'Lync Server 2013: tblPrincipalMeta。'
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
ms.openlocfilehash: 899fd1e450dac52afa56c1ee1de86da82b2db309
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573643"
---
# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="ea95a-103">Lync Server 2013 の tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="ea95a-103">tblPrincipalMeta in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea95a-104">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="ea95a-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="ea95a-105">tblPrincipalMeta には、Active Directory ドメインサービスから更新する必要があるプリンシパルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ea95a-105">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="ea95a-106">段組み</span><span class="sxs-lookup"><span data-stu-id="ea95a-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea95a-107">Column</span><span class="sxs-lookup"><span data-stu-id="ea95a-107">Column</span></span></th>
<th><span data-ttu-id="ea95a-108">種類</span><span class="sxs-lookup"><span data-stu-id="ea95a-108">Type</span></span></th>
<th><span data-ttu-id="ea95a-109">説明</span><span class="sxs-lookup"><span data-stu-id="ea95a-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea95a-110">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="ea95a-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="ea95a-111">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="ea95a-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ea95a-112">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="ea95a-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea95a-113">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="ea95a-113">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="ea95a-114">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="ea95a-114">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ea95a-115">プリンシパルの所属を最新の情報に更新する必要がある場合は True。</span><span class="sxs-lookup"><span data-stu-id="ea95a-115">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea95a-116">Prinattributes ダーティ</span><span class="sxs-lookup"><span data-stu-id="ea95a-116">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="ea95a-117">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="ea95a-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ea95a-118">プリンシパル属性を最新の情報に更新する必要がある場合は True。</span><span class="sxs-lookup"><span data-stu-id="ea95a-118">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea95a-119">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="ea95a-119">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="ea95a-120">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="ea95a-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ea95a-121">プリンシパルが削除されている場合は True。</span><span class="sxs-lookup"><span data-stu-id="ea95a-121">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea95a-122">tryCount</span><span class="sxs-lookup"><span data-stu-id="ea95a-122">tryCount</span></span></p></td>
<td><p><span data-ttu-id="ea95a-123">int</span><span class="sxs-lookup"><span data-stu-id="ea95a-123">int</span></span></p></td>
<td><p><span data-ttu-id="ea95a-124">それまでに行われた AD DS からプリンシパルを更新する試行の数。</span><span class="sxs-lookup"><span data-stu-id="ea95a-124">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea95a-125">lastTry</span><span class="sxs-lookup"><span data-stu-id="ea95a-125">lastTry</span></span></p></td>
<td><p><span data-ttu-id="ea95a-126">日付型</span><span class="sxs-lookup"><span data-stu-id="ea95a-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="ea95a-p101">プリンシパルを最新の情報に更新する最新の試行からのタイム スタンプ。最新の情報への更新をまだ試みていない場合は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="ea95a-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea95a-129">nextTry</span><span class="sxs-lookup"><span data-stu-id="ea95a-129">nextTry</span></span></p></td>
<td><p><span data-ttu-id="ea95a-130">日付型</span><span class="sxs-lookup"><span data-stu-id="ea95a-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="ea95a-p102">次にスケジュールされている最新の情報への更新のタイム スタンプ。最新の情報への更新がスケジュールされていない場合は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="ea95a-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="ea95a-133">Keys</span><span class="sxs-lookup"><span data-stu-id="ea95a-133">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea95a-134">列</span><span class="sxs-lookup"><span data-stu-id="ea95a-134">Column</span></span></th>
<th><span data-ttu-id="ea95a-135">説明</span><span class="sxs-lookup"><span data-stu-id="ea95a-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea95a-136">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="ea95a-136">prinID</span></span></p></td>
<td><p><span data-ttu-id="ea95a-137">主キー。</span><span class="sxs-lookup"><span data-stu-id="ea95a-137">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea95a-138">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="ea95a-138">prinID</span></span></p></td>
<td><p><span data-ttu-id="ea95a-139">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="ea95a-139">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

