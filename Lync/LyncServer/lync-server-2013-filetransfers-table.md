---
title: 'Lync Server 2013: FileTransfers テーブル'
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
ms.openlocfilehash: 33dbfdc6d7b0c8317b0f6ec56f837023398c0696
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="fc55c-102">Lync Server 2013 の FileTransfers テーブル</span><span class="sxs-lookup"><span data-stu-id="fc55c-102">FileTransfers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc55c-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="fc55c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="fc55c-104">各レコードは、1 つのファイル転送セッションを表します。</span><span class="sxs-lookup"><span data-stu-id="fc55c-104">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fc55c-105">列</span><span class="sxs-lookup"><span data-stu-id="fc55c-105">Column</span></span></th>
<th><span data-ttu-id="fc55c-106">データ型</span><span class="sxs-lookup"><span data-stu-id="fc55c-106">Data Type</span></span></th>
<th><span data-ttu-id="fc55c-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="fc55c-107">Key/Index</span></span></th>
<th><span data-ttu-id="fc55c-108">詳細</span><span class="sxs-lookup"><span data-stu-id="fc55c-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc55c-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="fc55c-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fc55c-110">日付型</span><span class="sxs-lookup"><span data-stu-id="fc55c-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="fc55c-111">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="fc55c-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="fc55c-112">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="fc55c-112">Time of session request.</span></span> <span data-ttu-id="fc55c-113">セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="fc55c-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="fc55c-114">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc55c-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc55c-115"><strong>Sessionidseq と</strong></span><span class="sxs-lookup"><span data-stu-id="fc55c-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fc55c-116">int</span><span class="sxs-lookup"><span data-stu-id="fc55c-116">int</span></span></p></td>
<td><p><span data-ttu-id="fc55c-117">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="fc55c-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="fc55c-118">セッションを識別するための ID 番号。</span><span class="sxs-lookup"><span data-stu-id="fc55c-118">ID number to identify the session.</span></span> <span data-ttu-id="fc55c-119">セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。</span><span class="sxs-lookup"><span data-stu-id="fc55c-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="fc55c-120">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc55c-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc55c-121"><strong>File Name</strong></span><span class="sxs-lookup"><span data-stu-id="fc55c-121"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="fc55c-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fc55c-122">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fc55c-123">ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="fc55c-123">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc55c-124"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="fc55c-124"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="fc55c-125">識別子</span><span class="sxs-lookup"><span data-stu-id="fc55c-125">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fc55c-126">同じファイル名を含むファイル転送を区別するための一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="fc55c-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc55c-127"><strong>クッキー</strong></span><span class="sxs-lookup"><span data-stu-id="fc55c-127"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="fc55c-128">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="fc55c-128">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="fc55c-129">Primary</span><span class="sxs-lookup"><span data-stu-id="fc55c-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="fc55c-130">すべてのフォローアップ メッセージをこれに関連付けられたものとして識別するために使用します。</span><span class="sxs-lookup"><span data-stu-id="fc55c-130">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc55c-131"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="fc55c-131"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="fc55c-132">若干</span><span class="sxs-lookup"><span data-stu-id="fc55c-132">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fc55c-p103">TRUE または NULL。TRUE の場合は、Reject と Cancel が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="fc55c-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc55c-135"><strong>拒否する</strong></span><span class="sxs-lookup"><span data-stu-id="fc55c-135"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="fc55c-136">若干</span><span class="sxs-lookup"><span data-stu-id="fc55c-136">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fc55c-p104">TRUE または NULL。TRUE の場合は、Accept と Cancel が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="fc55c-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc55c-139"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="fc55c-139"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="fc55c-140">若干</span><span class="sxs-lookup"><span data-stu-id="fc55c-140">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fc55c-p105">TRUE または NULL。TRUE の場合は、Accept と Reject が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="fc55c-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

