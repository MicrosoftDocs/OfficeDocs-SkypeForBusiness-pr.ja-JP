---
title: 'Lync Server 2013: FileTransfers テーブル'
description: 'Lync Server 2013: FileTransfers テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccde45fa3743a809499273676d567846ef292ecc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573363"
---
# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="346af-103">Lync Server 2013 の FileTransfers テーブル</span><span class="sxs-lookup"><span data-stu-id="346af-103">FileTransfers table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="346af-104">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="346af-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="346af-105">各レコードは、1 つのファイル転送セッションを表します。</span><span class="sxs-lookup"><span data-stu-id="346af-105">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="346af-106">Column</span><span class="sxs-lookup"><span data-stu-id="346af-106">Column</span></span></th>
<th><span data-ttu-id="346af-107">データ型</span><span class="sxs-lookup"><span data-stu-id="346af-107">Data Type</span></span></th>
<th><span data-ttu-id="346af-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="346af-108">Key/Index</span></span></th>
<th><span data-ttu-id="346af-109">詳細</span><span class="sxs-lookup"><span data-stu-id="346af-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="346af-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="346af-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="346af-111">日付型</span><span class="sxs-lookup"><span data-stu-id="346af-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="346af-112">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="346af-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="346af-113">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="346af-113">Time of session request.</span></span> <span data-ttu-id="346af-114">セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="346af-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="346af-115">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="346af-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="346af-116"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="346af-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="346af-117">int</span><span class="sxs-lookup"><span data-stu-id="346af-117">int</span></span></p></td>
<td><p><span data-ttu-id="346af-118">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="346af-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="346af-119">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="346af-119">ID number to identify the session.</span></span> <span data-ttu-id="346af-120">セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="346af-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="346af-121">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="346af-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="346af-122"><strong>File Name</strong></span><span class="sxs-lookup"><span data-stu-id="346af-122"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="346af-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="346af-123">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="346af-124">ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="346af-124">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="346af-125"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="346af-125"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="346af-126">識別子</span><span class="sxs-lookup"><span data-stu-id="346af-126">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="346af-127">同じファイル名を含むファイル転送を区別するための一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="346af-127">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="346af-128"><strong>クッキー</strong></span><span class="sxs-lookup"><span data-stu-id="346af-128"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="346af-129">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="346af-129">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="346af-130">Primary</span><span class="sxs-lookup"><span data-stu-id="346af-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="346af-131">すべてのフォローアップ メッセージをこれに関連付けられたものとして識別するために使用します。</span><span class="sxs-lookup"><span data-stu-id="346af-131">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="346af-132"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="346af-132"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="346af-133">若干</span><span class="sxs-lookup"><span data-stu-id="346af-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="346af-p103">TRUE または NULL。TRUE の場合は、Reject と Cancel が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="346af-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="346af-136"><strong>拒否する</strong></span><span class="sxs-lookup"><span data-stu-id="346af-136"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="346af-137">若干</span><span class="sxs-lookup"><span data-stu-id="346af-137">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="346af-p104">TRUE または NULL。TRUE の場合は、Accept と Cancel が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="346af-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="346af-140"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="346af-140"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="346af-141">若干</span><span class="sxs-lookup"><span data-stu-id="346af-141">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="346af-p105">TRUE または NULL。TRUE の場合は、Accept と Reject が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="346af-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

