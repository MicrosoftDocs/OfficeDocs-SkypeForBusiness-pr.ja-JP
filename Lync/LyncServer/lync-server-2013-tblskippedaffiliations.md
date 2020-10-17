---
title: 'Lync Server 2013: tblSkippedAffiliations'
description: 'Lync Server 2013: tblSkippedAffiliations。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48183373
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31746cee7302d34a1d19b3059ca1da6beab9345d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563803"
---
# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="243da-103">Lync Server 2013 の tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="243da-103">tblSkippedAffiliations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="243da-104">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="243da-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="243da-105">tblSkippedAffiliations には、読み取ることができなかった所属が含まれています (通常は、Active Directory ドメインサービスのアクセスエラーが原因です)。</span><span class="sxs-lookup"><span data-stu-id="243da-105">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="243da-106">段組み</span><span class="sxs-lookup"><span data-stu-id="243da-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="243da-107">Column</span><span class="sxs-lookup"><span data-stu-id="243da-107">Column</span></span></th>
<th><span data-ttu-id="243da-108">種類</span><span class="sxs-lookup"><span data-stu-id="243da-108">Type</span></span></th>
<th><span data-ttu-id="243da-109">説明</span><span class="sxs-lookup"><span data-stu-id="243da-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="243da-110">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="243da-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="243da-111">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="243da-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="243da-112">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="243da-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="243da-113">影響の説明</span><span class="sxs-lookup"><span data-stu-id="243da-113">affDescription</span></span></p></td>
<td><p><span data-ttu-id="243da-114">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="243da-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="243da-115">所属を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="243da-115">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="243da-116">形式: guid: {0} uri: {1} &gt; id:{2}</span><span class="sxs-lookup"><span data-stu-id="243da-116">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="243da-117">updatedBy</span><span class="sxs-lookup"><span data-stu-id="243da-117">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="243da-118">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="243da-118">int, not null</span></span></p></td>
<td><p><span data-ttu-id="243da-p101">この行を更新したプリンシパルの ID。これらのエントリのソースは Active Directory の同期だけなので、常に 1 (システム ユーザー) です。</span><span class="sxs-lookup"><span data-stu-id="243da-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="243da-121">Keys</span><span class="sxs-lookup"><span data-stu-id="243da-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="243da-122">列 (複数可)</span><span class="sxs-lookup"><span data-stu-id="243da-122">Column(s)</span></span></th>
<th><span data-ttu-id="243da-123">説明</span><span class="sxs-lookup"><span data-stu-id="243da-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="243da-124">&lt;prinID、影響の説明&gt;</span><span class="sxs-lookup"><span data-stu-id="243da-124">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="243da-125">主キー。</span><span class="sxs-lookup"><span data-stu-id="243da-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="243da-126">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="243da-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="243da-127">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="243da-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

