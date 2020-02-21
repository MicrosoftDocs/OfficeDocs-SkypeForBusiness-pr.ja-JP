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
ms.openlocfilehash: 04ad0fbdb9a4e3bb2e5962089fe1c30f960bdc91
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="4ecbd-102">Lync Server 2013 の tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="4ecbd-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ecbd-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="4ecbd-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="4ecbd-104">tblPrincipalMeta には、Active Directory ドメインサービスから更新する必要があるプリンシパルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4ecbd-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="4ecbd-105">Columns</span><span class="sxs-lookup"><span data-stu-id="4ecbd-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4ecbd-106">列</span><span class="sxs-lookup"><span data-stu-id="4ecbd-106">Column</span></span></th>
<th><span data-ttu-id="4ecbd-107">種類</span><span class="sxs-lookup"><span data-stu-id="4ecbd-107">Type</span></span></th>
<th><span data-ttu-id="4ecbd-108">説明</span><span class="sxs-lookup"><span data-stu-id="4ecbd-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ecbd-109">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="4ecbd-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="4ecbd-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="4ecbd-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4ecbd-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="4ecbd-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ecbd-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="4ecbd-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="4ecbd-113">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="4ecbd-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="4ecbd-114">プリンシパルの所属を最新の情報に更新する必要がある場合は True。</span><span class="sxs-lookup"><span data-stu-id="4ecbd-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ecbd-115">Prinattributes ダーティ</span><span class="sxs-lookup"><span data-stu-id="4ecbd-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="4ecbd-116">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="4ecbd-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="4ecbd-117">プリンシパル属性を最新の情報に更新する必要がある場合は True。</span><span class="sxs-lookup"><span data-stu-id="4ecbd-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ecbd-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="4ecbd-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="4ecbd-119">NULL でない bit</span><span class="sxs-lookup"><span data-stu-id="4ecbd-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="4ecbd-120">プリンシパルが削除されている場合は True。</span><span class="sxs-lookup"><span data-stu-id="4ecbd-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ecbd-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="4ecbd-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="4ecbd-122">int</span><span class="sxs-lookup"><span data-stu-id="4ecbd-122">int</span></span></p></td>
<td><p><span data-ttu-id="4ecbd-123">それまでに行われた AD DS からプリンシパルを更新する試行の数。</span><span class="sxs-lookup"><span data-stu-id="4ecbd-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ecbd-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="4ecbd-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="4ecbd-125">日付型</span><span class="sxs-lookup"><span data-stu-id="4ecbd-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="4ecbd-p101">プリンシパルを最新の情報に更新する最新の試行からのタイム スタンプ。最新の情報への更新をまだ試みていない場合は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="4ecbd-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4ecbd-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="4ecbd-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="4ecbd-129">日付型</span><span class="sxs-lookup"><span data-stu-id="4ecbd-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="4ecbd-p102">次にスケジュールされている最新の情報への更新のタイム スタンプ。最新の情報への更新がスケジュールされていない場合は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="4ecbd-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="4ecbd-132">Keys</span><span class="sxs-lookup"><span data-stu-id="4ecbd-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4ecbd-133">列</span><span class="sxs-lookup"><span data-stu-id="4ecbd-133">Column</span></span></th>
<th><span data-ttu-id="4ecbd-134">説明</span><span class="sxs-lookup"><span data-stu-id="4ecbd-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ecbd-135">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="4ecbd-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="4ecbd-136">主キー。</span><span class="sxs-lookup"><span data-stu-id="4ecbd-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ecbd-137">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="4ecbd-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="4ecbd-138">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="4ecbd-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

