---
title: 'Lync Server 2013: 場所テーブル'
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
ms.openlocfilehash: d93300acda297a026af03070680825899a608d86
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="14d7b-102">Lync Server 2013 の場所テーブル</span><span class="sxs-lookup"><span data-stu-id="14d7b-102">Locations table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14d7b-103">_**トピックの最終更新日:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="14d7b-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="14d7b-104">それぞれのレコードは、E9-1-1 通話など、緊急通話における 1 つの場所の参照を表します。</span><span class="sxs-lookup"><span data-stu-id="14d7b-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14d7b-105">列</span><span class="sxs-lookup"><span data-stu-id="14d7b-105">Column</span></span></th>
<th><span data-ttu-id="14d7b-106">データ型</span><span class="sxs-lookup"><span data-stu-id="14d7b-106">Data Type</span></span></th>
<th><span data-ttu-id="14d7b-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="14d7b-107">Key/Index</span></span></th>
<th><span data-ttu-id="14d7b-108">詳細</span><span class="sxs-lookup"><span data-stu-id="14d7b-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14d7b-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="14d7b-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="14d7b-110">日付型</span><span class="sxs-lookup"><span data-stu-id="14d7b-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="14d7b-111">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="14d7b-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="14d7b-112">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="14d7b-112">Time of session request.</span></span> <span data-ttu-id="14d7b-113">セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="14d7b-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="14d7b-114">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14d7b-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14d7b-115"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="14d7b-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="14d7b-116">int</span><span class="sxs-lookup"><span data-stu-id="14d7b-116">int</span></span></p></td>
<td><p><span data-ttu-id="14d7b-117">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="14d7b-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="14d7b-118">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="14d7b-118">ID number to identify the session.</span></span> <span data-ttu-id="14d7b-119">セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="14d7b-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="14d7b-120">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14d7b-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14d7b-121"><strong>場所</strong></span><span class="sxs-lookup"><span data-stu-id="14d7b-121"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="14d7b-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="14d7b-122">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="14d7b-123">緊急通話の場所。</span><span class="sxs-lookup"><span data-stu-id="14d7b-123">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

