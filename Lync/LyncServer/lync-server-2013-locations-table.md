---
title: 'Lync Server 2013: Locations テーブル'
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
ms.openlocfilehash: e2d16ffd08184a650f993d175239f5aff72b8b3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="8aa7d-102">Lync Server 2013 の Locations テーブル</span><span class="sxs-lookup"><span data-stu-id="8aa7d-102">Locations table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8aa7d-103">_**最終更新日:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="8aa7d-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="8aa7d-104">各レコードは、E9 通話のような緊急通話での1つの場所参照を表します。</span><span class="sxs-lookup"><span data-stu-id="8aa7d-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8aa7d-105">列</span><span class="sxs-lookup"><span data-stu-id="8aa7d-105">Column</span></span></th>
<th><span data-ttu-id="8aa7d-106">データ型</span><span class="sxs-lookup"><span data-stu-id="8aa7d-106">Data Type</span></span></th>
<th><span data-ttu-id="8aa7d-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="8aa7d-107">Key/Index</span></span></th>
<th><span data-ttu-id="8aa7d-108">詳細</span><span class="sxs-lookup"><span data-stu-id="8aa7d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8aa7d-109"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="8aa7d-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8aa7d-110">datetime</span><span class="sxs-lookup"><span data-stu-id="8aa7d-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="8aa7d-111">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="8aa7d-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8aa7d-112">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="8aa7d-112">Time of session request.</span></span> <span data-ttu-id="8aa7d-113">セッションを一意に識別するために<strong>Sessionidseq</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="8aa7d-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="8aa7d-114">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8aa7d-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8aa7d-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8aa7d-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8aa7d-116">int</span><span class="sxs-lookup"><span data-stu-id="8aa7d-116">int</span></span></p></td>
<td><p><span data-ttu-id="8aa7d-117">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="8aa7d-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8aa7d-118">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="8aa7d-118">ID number to identify the session.</span></span> <span data-ttu-id="8aa7d-119">セッションを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="8aa7d-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="8aa7d-120">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8aa7d-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8aa7d-121"><strong>場所</strong></span><span class="sxs-lookup"><span data-stu-id="8aa7d-121"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="8aa7d-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="8aa7d-122">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8aa7d-123">緊急通話の場所。</span><span class="sxs-lookup"><span data-stu-id="8aa7d-123">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

