---
title: 'Lync Server 2013: tblComplianceData'
description: 'Lync Server 2013: tblComplianceData。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c597d67054303de2753182b37419f68051d3af8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568103"
---
# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="1f1ea-103">Lync Server 2013 の tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="1f1ea-103">tblComplianceData in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f1ea-104">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="1f1ea-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="1f1ea-105">tblComplianceData には、コンプライアンス アダプターによってまだ処理されていないコンプライアンス イベントが格納されます。</span><span class="sxs-lookup"><span data-stu-id="1f1ea-105">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="1f1ea-106">段組み</span><span class="sxs-lookup"><span data-stu-id="1f1ea-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f1ea-107">Column</span><span class="sxs-lookup"><span data-stu-id="1f1ea-107">Column</span></span></th>
<th><span data-ttu-id="1f1ea-108">種類</span><span class="sxs-lookup"><span data-stu-id="1f1ea-108">Type</span></span></th>
<th><span data-ttu-id="1f1ea-109">説明</span><span class="sxs-lookup"><span data-stu-id="1f1ea-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f1ea-110">Tblcompliancedata.cmpleventid</span><span class="sxs-lookup"><span data-stu-id="1f1ea-110">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="1f1ea-111">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="1f1ea-111">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="1f1ea-112">イベント ID。</span><span class="sxs-lookup"><span data-stu-id="1f1ea-112">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f1ea-113">entryDate</span><span class="sxs-lookup"><span data-stu-id="1f1ea-113">entryDate</span></span></p></td>
<td><p><span data-ttu-id="1f1ea-114">NULL でない smalldatetime</span><span class="sxs-lookup"><span data-stu-id="1f1ea-114">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="1f1ea-115">挿入の日時 (cmplType=9 の場合は、エントリが単なるプレースホルダーなので、遠い将来になる可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="1f1ea-115">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f1ea-116">cmplType</span><span class="sxs-lookup"><span data-stu-id="1f1ea-116">cmplType</span></span></p></td>
<td><p><span data-ttu-id="1f1ea-117">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="1f1ea-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1f1ea-118">コンプライアンス イベントの種類。</span><span class="sxs-lookup"><span data-stu-id="1f1ea-118">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="1f1ea-119">1: チャット</span><span class="sxs-lookup"><span data-stu-id="1f1ea-119">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="1f1ea-120">2: バックチャット</span><span class="sxs-lookup"><span data-stu-id="1f1ea-120">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="1f1ea-121">3: ファイル ダウンロード</span><span class="sxs-lookup"><span data-stu-id="1f1ea-121">3: File download</span></span></p></li>
<li><p><span data-ttu-id="1f1ea-122">4: ファイル アップロード</span><span class="sxs-lookup"><span data-stu-id="1f1ea-122">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="1f1ea-123">9: 暫定ファイル転送</span><span class="sxs-lookup"><span data-stu-id="1f1ea-123">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="1f1ea-124">10: (置き換えによる) チャットの削除</span><span class="sxs-lookup"><span data-stu-id="1f1ea-124">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="1f1ea-125">11: チャットの削除</span><span class="sxs-lookup"><span data-stu-id="1f1ea-125">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f1ea-126">cmplTime</span><span class="sxs-lookup"><span data-stu-id="1f1ea-126">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="1f1ea-127">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="1f1ea-127">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="1f1ea-128">イベントのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="1f1ea-128">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f1ea-129">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="1f1ea-129">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="1f1ea-130">NULL でない nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="1f1ea-130">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="1f1ea-131">チャネルの URI (Uniform Resource Identifier)。</span><span class="sxs-lookup"><span data-stu-id="1f1ea-131">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f1ea-132">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="1f1ea-132">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="1f1ea-133">bigint</span><span class="sxs-lookup"><span data-stu-id="1f1ea-133">bigint</span></span></p></td>
<td><p><span data-ttu-id="1f1ea-134">チャット ID (tblChat.chatId テーブルに対応)。</span><span class="sxs-lookup"><span data-stu-id="1f1ea-134">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f1ea-135">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="1f1ea-135">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="1f1ea-136">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="1f1ea-136">int, not null</span></span></p></td>
<td><p><span data-ttu-id="1f1ea-137">ポスターのプリンシパル ID (tblPrincipal.prinID テーブルに対応)。</span><span class="sxs-lookup"><span data-stu-id="1f1ea-137">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f1ea-138">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="1f1ea-138">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="1f1ea-139">NULL でない nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="1f1ea-139">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="1f1ea-140">ユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="1f1ea-140">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f1ea-141">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="1f1ea-141">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="1f1ea-142">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="1f1ea-142">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="1f1ea-143">メッセージ (エンコードは cmplType に依存)。</span><span class="sxs-lookup"><span data-stu-id="1f1ea-143">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="1f1ea-144">キー</span><span class="sxs-lookup"><span data-stu-id="1f1ea-144">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f1ea-145">列</span><span class="sxs-lookup"><span data-stu-id="1f1ea-145">Column</span></span></th>
<th><span data-ttu-id="1f1ea-146">説明</span><span class="sxs-lookup"><span data-stu-id="1f1ea-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f1ea-147">Tblcompliancedata.cmpleventid</span><span class="sxs-lookup"><span data-stu-id="1f1ea-147">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="1f1ea-148">主キー。</span><span class="sxs-lookup"><span data-stu-id="1f1ea-148">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

