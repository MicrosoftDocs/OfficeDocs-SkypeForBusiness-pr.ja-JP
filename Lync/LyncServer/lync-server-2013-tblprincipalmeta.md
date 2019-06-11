---
title: 'Lync Server 2013: tblPrincipalMeta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b9b067b9d04ecb32a3e43dbbd1f8435c00fa0c0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="8b0d5-102">Lync Server 2013 の tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="8b0d5-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b0d5-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="8b0d5-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="8b0d5-104">tblPrincipalMeta には、Active Directory ドメインサービスから更新する必要があるプリンシパルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8b0d5-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="8b0d5-105">行</span><span class="sxs-lookup"><span data-stu-id="8b0d5-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b0d5-106">列</span><span class="sxs-lookup"><span data-stu-id="8b0d5-106">Column</span></span></th>
<th><span data-ttu-id="8b0d5-107">型</span><span class="sxs-lookup"><span data-stu-id="8b0d5-107">Type</span></span></th>
<th><span data-ttu-id="8b0d5-108">説明</span><span class="sxs-lookup"><span data-stu-id="8b0d5-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b0d5-109">prinID</span><span class="sxs-lookup"><span data-stu-id="8b0d5-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="8b0d5-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="8b0d5-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="8b0d5-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="8b0d5-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b0d5-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="8b0d5-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="8b0d5-113">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="8b0d5-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="8b0d5-114">プリンシパルの所属を更新する必要がある場合は True。</span><span class="sxs-lookup"><span data-stu-id="8b0d5-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b0d5-115">Prin属性のダーティ</span><span class="sxs-lookup"><span data-stu-id="8b0d5-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="8b0d5-116">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="8b0d5-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="8b0d5-117">プリンシパル属性を更新する必要がある場合は True。</span><span class="sxs-lookup"><span data-stu-id="8b0d5-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b0d5-118">プリントが削除されました</span><span class="sxs-lookup"><span data-stu-id="8b0d5-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="8b0d5-119">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="8b0d5-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="8b0d5-120">プリンシパルが削除された場合は True。</span><span class="sxs-lookup"><span data-stu-id="8b0d5-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b0d5-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="8b0d5-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="8b0d5-122">int</span><span class="sxs-lookup"><span data-stu-id="8b0d5-122">int</span></span></p></td>
<td><p><span data-ttu-id="8b0d5-123">これまでに発生した、AD DS からプリンシパルを更新しようとした回数。</span><span class="sxs-lookup"><span data-stu-id="8b0d5-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b0d5-124">最終試用</span><span class="sxs-lookup"><span data-stu-id="8b0d5-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="8b0d5-125">datetime</span><span class="sxs-lookup"><span data-stu-id="8b0d5-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="8b0d5-126">プリンシパルを最新の状態に更新しようとしたときのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="8b0d5-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="8b0d5-127">更新をまだ実行していない場合は、null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8b0d5-127">Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b0d5-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="8b0d5-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="8b0d5-129">datetime</span><span class="sxs-lookup"><span data-stu-id="8b0d5-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="8b0d5-130">スケジュールされている次回の更新のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="8b0d5-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="8b0d5-131">それ以降の更新がスケジュールされていない場合は、null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8b0d5-131">Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="8b0d5-132">機能</span><span class="sxs-lookup"><span data-stu-id="8b0d5-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b0d5-133">列</span><span class="sxs-lookup"><span data-stu-id="8b0d5-133">Column</span></span></th>
<th><span data-ttu-id="8b0d5-134">説明</span><span class="sxs-lookup"><span data-stu-id="8b0d5-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b0d5-135">prinID</span><span class="sxs-lookup"><span data-stu-id="8b0d5-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="8b0d5-136">主キー。</span><span class="sxs-lookup"><span data-stu-id="8b0d5-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b0d5-137">prinID</span><span class="sxs-lookup"><span data-stu-id="8b0d5-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="8b0d5-138">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="8b0d5-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

