---
title: 'Lync Server 2013: tblSkippedAffiliations'
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
ms.openlocfilehash: 31997276c95fb3908ab33d0a21017833f10fddcc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="a96d5-102">Lync Server 2013 の tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="a96d5-102">tblSkippedAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a96d5-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="a96d5-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="a96d5-104">tblSkippedAffiliations には、読み取ることができなかった所属が含まれています (通常は、Active Directory ドメインサービスのアクセスエラーが原因です)。</span><span class="sxs-lookup"><span data-stu-id="a96d5-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="a96d5-105">Columns</span><span class="sxs-lookup"><span data-stu-id="a96d5-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a96d5-106">列</span><span class="sxs-lookup"><span data-stu-id="a96d5-106">Column</span></span></th>
<th><span data-ttu-id="a96d5-107">種類</span><span class="sxs-lookup"><span data-stu-id="a96d5-107">Type</span></span></th>
<th><span data-ttu-id="a96d5-108">説明</span><span class="sxs-lookup"><span data-stu-id="a96d5-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a96d5-109">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="a96d5-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="a96d5-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="a96d5-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a96d5-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="a96d5-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a96d5-112">影響の説明</span><span class="sxs-lookup"><span data-stu-id="a96d5-112">affDescription</span></span></p></td>
<td><p><span data-ttu-id="a96d5-113">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a96d5-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="a96d5-114">所属を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="a96d5-114">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="a96d5-115">形式: guid: {0} uri: {1} &gt; id:{2}</span><span class="sxs-lookup"><span data-stu-id="a96d5-115">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a96d5-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="a96d5-116">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="a96d5-117">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="a96d5-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="a96d5-p101">この行を更新したプリンシパルの ID。これらのエントリのソースは Active Directory の同期だけなので、常に 1 (システム ユーザー) です。</span><span class="sxs-lookup"><span data-stu-id="a96d5-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="a96d5-120">Keys</span><span class="sxs-lookup"><span data-stu-id="a96d5-120">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a96d5-121">列 (複数可)</span><span class="sxs-lookup"><span data-stu-id="a96d5-121">Column(s)</span></span></th>
<th><span data-ttu-id="a96d5-122">説明</span><span class="sxs-lookup"><span data-stu-id="a96d5-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a96d5-123">&lt;prinID、影響の説明&gt;</span><span class="sxs-lookup"><span data-stu-id="a96d5-123">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="a96d5-124">主キー。</span><span class="sxs-lookup"><span data-stu-id="a96d5-124">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a96d5-125">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="a96d5-125">prinID</span></span></p></td>
<td><p><span data-ttu-id="a96d5-126">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="a96d5-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

