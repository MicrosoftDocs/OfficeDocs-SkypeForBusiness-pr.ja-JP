---
title: 'Lync Server 2013: tblSkippedAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48183373
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06269ede55a46757f78595d7573f3cd77414d1d5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="655d6-102">Lync Server 2013 の tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="655d6-102">tblSkippedAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="655d6-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="655d6-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="655d6-104">tblSkippedAffiliations には、読み取ることができなかった所属先が含まれています (通常は Active Directory ドメインサービスアクセスエラーが原因です)。</span><span class="sxs-lookup"><span data-stu-id="655d6-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="655d6-105">行</span><span class="sxs-lookup"><span data-stu-id="655d6-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="655d6-106">列</span><span class="sxs-lookup"><span data-stu-id="655d6-106">Column</span></span></th>
<th><span data-ttu-id="655d6-107">型</span><span class="sxs-lookup"><span data-stu-id="655d6-107">Type</span></span></th>
<th><span data-ttu-id="655d6-108">説明</span><span class="sxs-lookup"><span data-stu-id="655d6-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="655d6-109">prinID</span><span class="sxs-lookup"><span data-stu-id="655d6-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="655d6-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="655d6-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="655d6-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="655d6-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="655d6-112">影響の説明</span><span class="sxs-lookup"><span data-stu-id="655d6-112">affDescription</span></span></p></td>
<td><p><span data-ttu-id="655d6-113">nvarchar (256)、null ではない</span><span class="sxs-lookup"><span data-stu-id="655d6-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="655d6-114">所属を識別する文字列。</span><span class="sxs-lookup"><span data-stu-id="655d6-114">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="655d6-115">形式は次のとおりです{0} : guid {1} &gt; : uri: id:{2}</span><span class="sxs-lookup"><span data-stu-id="655d6-115">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="655d6-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="655d6-116">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="655d6-117">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="655d6-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="655d6-118">この行を更新したプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="655d6-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="655d6-119">Active Directory 同期がこれらのエントリの唯一のソースであるため、常に 1 (システムユーザー) になります。</span><span class="sxs-lookup"><span data-stu-id="655d6-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="655d6-120">機能</span><span class="sxs-lookup"><span data-stu-id="655d6-120">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="655d6-121">列</span><span class="sxs-lookup"><span data-stu-id="655d6-121">Column(s)</span></span></th>
<th><span data-ttu-id="655d6-122">説明</span><span class="sxs-lookup"><span data-stu-id="655d6-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="655d6-123">&lt;prinID、の影響の説明&gt;</span><span class="sxs-lookup"><span data-stu-id="655d6-123">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="655d6-124">主キー。</span><span class="sxs-lookup"><span data-stu-id="655d6-124">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="655d6-125">prinID</span><span class="sxs-lookup"><span data-stu-id="655d6-125">prinID</span></span></p></td>
<td><p><span data-ttu-id="655d6-126">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="655d6-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

