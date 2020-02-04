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
ms.openlocfilehash: de8a3e69c670c273bcdd91ac5895c0b1f0b15d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a><span data-ttu-id="204e4-102">Lync Server 2013 の FileTransfers テーブル</span><span class="sxs-lookup"><span data-stu-id="204e4-102">FileTransfers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="204e4-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="204e4-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="204e4-104">各レコードは、1つのファイル転送セッションを表します。</span><span class="sxs-lookup"><span data-stu-id="204e4-104">Each record represents one file transfer session.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="204e4-105">列</span><span class="sxs-lookup"><span data-stu-id="204e4-105">Column</span></span></th>
<th><span data-ttu-id="204e4-106">データ型</span><span class="sxs-lookup"><span data-stu-id="204e4-106">Data Type</span></span></th>
<th><span data-ttu-id="204e4-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="204e4-107">Key/Index</span></span></th>
<th><span data-ttu-id="204e4-108">詳細</span><span class="sxs-lookup"><span data-stu-id="204e4-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="204e4-109"><strong>セッション Id</strong></span><span class="sxs-lookup"><span data-stu-id="204e4-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="204e4-110">datetime</span><span class="sxs-lookup"><span data-stu-id="204e4-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="204e4-111">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="204e4-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="204e4-112">セッション要求の時刻。</span><span class="sxs-lookup"><span data-stu-id="204e4-112">Time of session request.</span></span> <span data-ttu-id="204e4-113">セッションを一意に識別するために<strong>Sessionidseq</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="204e4-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="204e4-114">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="204e4-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="204e4-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="204e4-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="204e4-116">int</span><span class="sxs-lookup"><span data-stu-id="204e4-116">int</span></span></p></td>
<td><p><span data-ttu-id="204e4-117">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="204e4-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="204e4-118">セッションを識別する ID 番号。</span><span class="sxs-lookup"><span data-stu-id="204e4-118">ID number to identify the session.</span></span> <span data-ttu-id="204e4-119">セッションを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="204e4-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="204e4-120">詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="204e4-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="204e4-121"><strong>ファイル名</strong></span><span class="sxs-lookup"><span data-stu-id="204e4-121"><strong>File Name</strong></span></span></p></td>
<td><p><span data-ttu-id="204e4-122">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="204e4-122">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="204e4-123">ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="204e4-123">Name of the file.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="204e4-124"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="204e4-124"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="204e4-125">長さ</span><span class="sxs-lookup"><span data-stu-id="204e4-125">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="204e4-126">同じファイル名を含むファイル転送を区別する一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="204e4-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="204e4-127"><strong>クッキー</strong></span><span class="sxs-lookup"><span data-stu-id="204e4-127"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="204e4-128">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="204e4-128">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="204e4-129">Primary</span><span class="sxs-lookup"><span data-stu-id="204e4-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="204e4-130">すべてのフォローアップメッセージをこのメールに関連付けられているものとして識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="204e4-130">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="204e4-131"><strong>受諾</strong></span><span class="sxs-lookup"><span data-stu-id="204e4-131"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="204e4-132">bit</span><span class="sxs-lookup"><span data-stu-id="204e4-132">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="204e4-133">TRUE または NULL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="204e4-133">Can be TRUE or NULL.</span></span> <span data-ttu-id="204e4-134">TRUE の場合は、拒否とキャンセルは NULL になります。</span><span class="sxs-lookup"><span data-stu-id="204e4-134">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="204e4-135"><strong>拒否</strong></span><span class="sxs-lookup"><span data-stu-id="204e4-135"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="204e4-136">bit</span><span class="sxs-lookup"><span data-stu-id="204e4-136">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="204e4-137">TRUE または NULL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="204e4-137">Can be TRUE or NULL.</span></span> <span data-ttu-id="204e4-138">TRUE の場合は、Accept と Cancel は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="204e4-138">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="204e4-139"><strong>キャンセル</strong></span><span class="sxs-lookup"><span data-stu-id="204e4-139"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="204e4-140">bit</span><span class="sxs-lookup"><span data-stu-id="204e4-140">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="204e4-141">TRUE または NULL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="204e4-141">Can be TRUE or NULL.</span></span> <span data-ttu-id="204e4-142">TRUE の場合は、Accept と Reject は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="204e4-142">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

