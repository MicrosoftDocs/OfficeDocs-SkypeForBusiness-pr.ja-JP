---
title: 'Lync Server 2013: tblPrincipalMembers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMembers
ms:assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615022(v=OCS.15)
ms:contentKeyID: 48184965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4098b3ea8c9a5dda2cdee7d05f71b940ffcb0325
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523634"
---
# <a name="tblprincipalmembers-in-lync-server-2013"></a><span data-ttu-id="fd4f5-102">Lync Server 2013 の tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="fd4f5-102">tblPrincipalMembers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd4f5-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="fd4f5-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="fd4f5-104">tblPrincipalMembers には、プリンシパル メンバーシップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-104">tblPrincipalMembers contains principal memberships.</span></span>

### <a name="columns"></a><span data-ttu-id="fd4f5-105">段組み</span><span class="sxs-lookup"><span data-stu-id="fd4f5-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd4f5-106">Column</span><span class="sxs-lookup"><span data-stu-id="fd4f5-106">Column</span></span></th>
<th><span data-ttu-id="fd4f5-107">種類</span><span class="sxs-lookup"><span data-stu-id="fd4f5-107">Type</span></span></th>
<th><span data-ttu-id="fd4f5-108">説明</span><span class="sxs-lookup"><span data-stu-id="fd4f5-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd4f5-109">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="fd4f5-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="fd4f5-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="fd4f5-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fd4f5-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd4f5-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="fd4f5-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="fd4f5-113">NULL でない nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="fd4f5-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="fd4f5-p101">メンバーの識別名。メンバーは (tblPrincipal テーブル内の) プリンシパルでなくてもかまいません。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-p101">Distinguished name of a member. A member does not have to be a principal (in tblPrincipal table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="fd4f5-116">Keys</span><span class="sxs-lookup"><span data-stu-id="fd4f5-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd4f5-117">列</span><span class="sxs-lookup"><span data-stu-id="fd4f5-117">Column</span></span></th>
<th><span data-ttu-id="fd4f5-118">説明</span><span class="sxs-lookup"><span data-stu-id="fd4f5-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd4f5-119">&lt;prinID、memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="fd4f5-119">&lt;prinID, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="fd4f5-120">主キー。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-120">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd4f5-121">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="fd4f5-121">prinID</span></span></p></td>
<td><p><span data-ttu-id="fd4f5-122">tblPrincipal.prinID の検索に使用する外部キー。</span><span class="sxs-lookup"><span data-stu-id="fd4f5-122">Foreign key with lookup in tblPrincipal.prinID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

