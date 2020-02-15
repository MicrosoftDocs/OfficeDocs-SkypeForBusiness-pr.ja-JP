---
title: 'Lync Server 2013: tblComplianceData'
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
ms.openlocfilehash: 03f5a65b11c610849c5b9d031f24d236dcbcf332
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="cc78f-102">Lync Server 2013 の tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="cc78f-102">tblComplianceData in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc78f-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="cc78f-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="cc78f-104">tblComplianceData には、コンプライアンス アダプターによってまだ処理されていないコンプライアンス イベントが格納されます。</span><span class="sxs-lookup"><span data-stu-id="cc78f-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="cc78f-105">Columns</span><span class="sxs-lookup"><span data-stu-id="cc78f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc78f-106">列</span><span class="sxs-lookup"><span data-stu-id="cc78f-106">Column</span></span></th>
<th><span data-ttu-id="cc78f-107">種類</span><span class="sxs-lookup"><span data-stu-id="cc78f-107">Type</span></span></th>
<th><span data-ttu-id="cc78f-108">説明</span><span class="sxs-lookup"><span data-stu-id="cc78f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc78f-109">Tblcompliancedata.cmpleventid</span><span class="sxs-lookup"><span data-stu-id="cc78f-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="cc78f-110">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="cc78f-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="cc78f-111">イベント ID。</span><span class="sxs-lookup"><span data-stu-id="cc78f-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc78f-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="cc78f-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="cc78f-113">NULL でない smalldatetime</span><span class="sxs-lookup"><span data-stu-id="cc78f-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="cc78f-114">挿入の日時 (cmplType=9 の場合は、エントリが単なるプレースホルダーなので、遠い将来になる可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="cc78f-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc78f-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="cc78f-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="cc78f-116">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="cc78f-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="cc78f-117">コンプライアンス イベントの種類。</span><span class="sxs-lookup"><span data-stu-id="cc78f-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="cc78f-118">1: チャット</span><span class="sxs-lookup"><span data-stu-id="cc78f-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="cc78f-119">2: バックチャット</span><span class="sxs-lookup"><span data-stu-id="cc78f-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="cc78f-120">3: ファイル ダウンロード</span><span class="sxs-lookup"><span data-stu-id="cc78f-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="cc78f-121">4: ファイル アップロード</span><span class="sxs-lookup"><span data-stu-id="cc78f-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="cc78f-122">9: 暫定ファイル転送</span><span class="sxs-lookup"><span data-stu-id="cc78f-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="cc78f-123">10: (置き換えによる) チャットの削除</span><span class="sxs-lookup"><span data-stu-id="cc78f-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="cc78f-124">11: チャットの削除</span><span class="sxs-lookup"><span data-stu-id="cc78f-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc78f-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="cc78f-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="cc78f-126">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="cc78f-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="cc78f-127">イベントのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="cc78f-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc78f-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="cc78f-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="cc78f-129">NULL でない nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="cc78f-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="cc78f-130">チャネルの URI (Uniform Resource Identifier)。</span><span class="sxs-lookup"><span data-stu-id="cc78f-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc78f-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="cc78f-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="cc78f-132">bigint</span><span class="sxs-lookup"><span data-stu-id="cc78f-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="cc78f-133">チャット ID (tblChat.chatId テーブルに対応)。</span><span class="sxs-lookup"><span data-stu-id="cc78f-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc78f-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="cc78f-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="cc78f-135">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="cc78f-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="cc78f-136">ポスターのプリンシパル ID (tblPrincipal.prinID テーブルに対応)。</span><span class="sxs-lookup"><span data-stu-id="cc78f-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc78f-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="cc78f-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="cc78f-138">NULL でない nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="cc78f-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="cc78f-139">ユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="cc78f-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc78f-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="cc78f-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="cc78f-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="cc78f-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="cc78f-142">メッセージ (エンコードは cmplType に依存)。</span><span class="sxs-lookup"><span data-stu-id="cc78f-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="cc78f-143">キー</span><span class="sxs-lookup"><span data-stu-id="cc78f-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc78f-144">列</span><span class="sxs-lookup"><span data-stu-id="cc78f-144">Column</span></span></th>
<th><span data-ttu-id="cc78f-145">説明</span><span class="sxs-lookup"><span data-stu-id="cc78f-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc78f-146">Tblcompliancedata.cmpleventid</span><span class="sxs-lookup"><span data-stu-id="cc78f-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="cc78f-147">主キー。</span><span class="sxs-lookup"><span data-stu-id="cc78f-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

