---
title: 'Lync Server 2013: 場所テーブル'
description: 'Lync Server 2013: 場所テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Locations table
ms:assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398596(v=OCS.15)
ms:contentKeyID: 48184579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d07b6d3d3820f4efb3310adf0734a7e10c53e6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570583"
---
# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="ccfa7-103">Lync Server 2013 の場所テーブル</span><span class="sxs-lookup"><span data-stu-id="ccfa7-103">Locations table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccfa7-104">_**トピックの最終更新日:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="ccfa7-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="ccfa7-105">それぞれのレコードは、E9-1-1 通話など、緊急通話における 1 つの場所の参照を表します。</span><span class="sxs-lookup"><span data-stu-id="ccfa7-105">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ccfa7-106">Column</span><span class="sxs-lookup"><span data-stu-id="ccfa7-106">Column</span></span></th>
<th><span data-ttu-id="ccfa7-107">データ型</span><span class="sxs-lookup"><span data-stu-id="ccfa7-107">Data Type</span></span></th>
<th><span data-ttu-id="ccfa7-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="ccfa7-108">Key/Index</span></span></th>
<th><span data-ttu-id="ccfa7-109">詳細</span><span class="sxs-lookup"><span data-stu-id="ccfa7-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ccfa7-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ccfa7-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ccfa7-111">日付型</span><span class="sxs-lookup"><span data-stu-id="ccfa7-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ccfa7-112">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="ccfa7-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ccfa7-113">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="ccfa7-113">Time of session request.</span></span> <span data-ttu-id="ccfa7-114">セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="ccfa7-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ccfa7-115">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccfa7-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccfa7-116"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="ccfa7-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ccfa7-117">int</span><span class="sxs-lookup"><span data-stu-id="ccfa7-117">int</span></span></p></td>
<td><p><span data-ttu-id="ccfa7-118">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="ccfa7-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ccfa7-119">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="ccfa7-119">ID number to identify the session.</span></span> <span data-ttu-id="ccfa7-120">セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="ccfa7-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ccfa7-121">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccfa7-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccfa7-122"><strong>Location</strong></span><span class="sxs-lookup"><span data-stu-id="ccfa7-122"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="ccfa7-123">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="ccfa7-123">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ccfa7-124">緊急通話の場所。</span><span class="sxs-lookup"><span data-stu-id="ccfa7-124">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

