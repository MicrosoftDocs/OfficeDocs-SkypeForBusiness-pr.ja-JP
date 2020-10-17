---
title: 'Lync Server 2013: tblPrincipalAffiliations'
description: 'Lync Server 2013: tblPrincipalAffiliations。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01c373147a58300e64f22e60e989a777c59b2653
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547483"
---
# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="2942b-103">Lync Server 2013 の tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="2942b-103">tblPrincipalAffiliations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2942b-104">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2942b-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2942b-105">tblPrincipalAffiliations には、active directory ドメインサービスセキュリティグループ、Active Directory コンテナー、ドメインなどの場所でのメンバーシップを記述するプリンシパルの所属が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2942b-105">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="2942b-106">段組み</span><span class="sxs-lookup"><span data-stu-id="2942b-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2942b-107">Column</span><span class="sxs-lookup"><span data-stu-id="2942b-107">Column</span></span></th>
<th><span data-ttu-id="2942b-108">種類</span><span class="sxs-lookup"><span data-stu-id="2942b-108">Type</span></span></th>
<th><span data-ttu-id="2942b-109">説明</span><span class="sxs-lookup"><span data-stu-id="2942b-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2942b-110">principalID</span><span class="sxs-lookup"><span data-stu-id="2942b-110">principalID</span></span></p></td>
<td><p><span data-ttu-id="2942b-111">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="2942b-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2942b-112">所属プリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="2942b-112">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2942b-113">affiliationID</span><span class="sxs-lookup"><span data-stu-id="2942b-113">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="2942b-114">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="2942b-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2942b-p101">所属を表すプリンシパルの ID。各プリンシパル (system-user-types 除く) には自己所属も含まれます。</span><span class="sxs-lookup"><span data-stu-id="2942b-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2942b-117">index</span><span class="sxs-lookup"><span data-stu-id="2942b-117">index</span></span></p></td>
<td><p><span data-ttu-id="2942b-118">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="2942b-118">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2942b-119">順.</span><span class="sxs-lookup"><span data-stu-id="2942b-119">Index.</span></span> <span data-ttu-id="2942b-120">自己所属の値は-1 で、その他の所属については、各 principalID、affiliationId バケット内で1から順に増加し &lt; &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="2942b-120">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2942b-121">updatedBy</span><span class="sxs-lookup"><span data-stu-id="2942b-121">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="2942b-122">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="2942b-122">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2942b-p103">最新の更新を実行したプリンシパル。通常は、Active Directory の同期を意味する 1 です。</span><span class="sxs-lookup"><span data-stu-id="2942b-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="2942b-125">Keys</span><span class="sxs-lookup"><span data-stu-id="2942b-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2942b-126">段組み</span><span class="sxs-lookup"><span data-stu-id="2942b-126">Columns</span></span></th>
<th><span data-ttu-id="2942b-127">説明</span><span class="sxs-lookup"><span data-stu-id="2942b-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2942b-128">&lt;principalID、index、affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="2942b-128">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="2942b-129">主キー。</span><span class="sxs-lookup"><span data-stu-id="2942b-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2942b-130">principalID</span><span class="sxs-lookup"><span data-stu-id="2942b-130">principalID</span></span></p></td>
<td><p><span data-ttu-id="2942b-131">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="2942b-131">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2942b-132">affiliationID</span><span class="sxs-lookup"><span data-stu-id="2942b-132">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="2942b-133">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="2942b-133">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

