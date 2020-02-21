---
title: 'Lync Server 2013: tblPrincipalAffiliations'
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
ms.openlocfilehash: 0a57e4a3c7a5fdcc1825c140cb6e26f8cede8dc1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="9a2d4-102">Lync Server 2013 の tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="9a2d4-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a2d4-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="9a2d4-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="9a2d4-104">tblPrincipalAffiliations には、active directory ドメインサービスセキュリティグループ、Active Directory コンテナー、ドメインなどの場所でのメンバーシップを記述するプリンシパルの所属が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9a2d4-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="9a2d4-105">Columns</span><span class="sxs-lookup"><span data-stu-id="9a2d4-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a2d4-106">列</span><span class="sxs-lookup"><span data-stu-id="9a2d4-106">Column</span></span></th>
<th><span data-ttu-id="9a2d4-107">種類</span><span class="sxs-lookup"><span data-stu-id="9a2d4-107">Type</span></span></th>
<th><span data-ttu-id="9a2d4-108">説明</span><span class="sxs-lookup"><span data-stu-id="9a2d4-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a2d4-109">principalID</span><span class="sxs-lookup"><span data-stu-id="9a2d4-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="9a2d4-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="9a2d4-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9a2d4-111">所属プリンシパルの ID。</span><span class="sxs-lookup"><span data-stu-id="9a2d4-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a2d4-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="9a2d4-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="9a2d4-113">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="9a2d4-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9a2d4-p101">所属を表すプリンシパルの ID。各プリンシパル (system-user-types 除く) には自己所属も含まれます。</span><span class="sxs-lookup"><span data-stu-id="9a2d4-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a2d4-116">index</span><span class="sxs-lookup"><span data-stu-id="9a2d4-116">index</span></span></p></td>
<td><p><span data-ttu-id="9a2d4-117">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="9a2d4-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9a2d4-118">順.</span><span class="sxs-lookup"><span data-stu-id="9a2d4-118">Index.</span></span> <span data-ttu-id="9a2d4-119">自己所属の値は-1 で、その他の所属については、各&lt;PrincipalID、affiliationId&gt;バケット内で1から順に増加します。</span><span class="sxs-lookup"><span data-stu-id="9a2d4-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a2d4-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="9a2d4-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="9a2d4-121">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="9a2d4-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9a2d4-p103">最新の更新を実行したプリンシパル。通常は、Active Directory の同期を意味する 1 です。</span><span class="sxs-lookup"><span data-stu-id="9a2d4-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="9a2d4-124">Keys</span><span class="sxs-lookup"><span data-stu-id="9a2d4-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a2d4-125">Columns</span><span class="sxs-lookup"><span data-stu-id="9a2d4-125">Columns</span></span></th>
<th><span data-ttu-id="9a2d4-126">説明</span><span class="sxs-lookup"><span data-stu-id="9a2d4-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a2d4-127">&lt;principalID、index、affiliationID&gt;</span><span class="sxs-lookup"><span data-stu-id="9a2d4-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="9a2d4-128">主キー。</span><span class="sxs-lookup"><span data-stu-id="9a2d4-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a2d4-129">principalID</span><span class="sxs-lookup"><span data-stu-id="9a2d4-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="9a2d4-130">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="9a2d4-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a2d4-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="9a2d4-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="9a2d4-132">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="9a2d4-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

