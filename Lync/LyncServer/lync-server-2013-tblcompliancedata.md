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
ms.openlocfilehash: 48516f307a084d30fde06a03548119e0ada34d6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a><span data-ttu-id="5fdc1-102">Lync Server 2013 の tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="5fdc1-102">tblComplianceData in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fdc1-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5fdc1-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5fdc1-104">tblComplianceData には、コンプライアンスアダプターでまだ処理されていないコンプライアンスイベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5fdc1-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>

### <a name="columns"></a><span data-ttu-id="5fdc1-105">行</span><span class="sxs-lookup"><span data-stu-id="5fdc1-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5fdc1-106">列</span><span class="sxs-lookup"><span data-stu-id="5fdc1-106">Column</span></span></th>
<th><span data-ttu-id="5fdc1-107">型</span><span class="sxs-lookup"><span data-stu-id="5fdc1-107">Type</span></span></th>
<th><span data-ttu-id="5fdc1-108">説明</span><span class="sxs-lookup"><span data-stu-id="5fdc1-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fdc1-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="5fdc1-109">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="5fdc1-110">bigint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="5fdc1-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="5fdc1-111">イベント ID。</span><span class="sxs-lookup"><span data-stu-id="5fdc1-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fdc1-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="5fdc1-112">entryDate</span></span></p></td>
<td><p><span data-ttu-id="5fdc1-113">smalldatetime、null ではない</span><span class="sxs-lookup"><span data-stu-id="5fdc1-113">smalldatetime, not null</span></span></p></td>
<td><p><span data-ttu-id="5fdc1-114">挿入の時刻 (その場合は、cmplType = 9 の場合は、その場合はプレースホルダーのみのエントリであるため)。</span><span class="sxs-lookup"><span data-stu-id="5fdc1-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fdc1-115">cmplType 種類</span><span class="sxs-lookup"><span data-stu-id="5fdc1-115">cmplType</span></span></p></td>
<td><p><span data-ttu-id="5fdc1-116">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="5fdc1-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5fdc1-117">コンプライアンスイベントの種類:</span><span class="sxs-lookup"><span data-stu-id="5fdc1-117">Type of compliance event:</span></span></p>
<ul>
<li><p><span data-ttu-id="5fdc1-118">1: チャット</span><span class="sxs-lookup"><span data-stu-id="5fdc1-118">1: Chat</span></span></p></li>
<li><p><span data-ttu-id="5fdc1-119">2: backchat</span><span class="sxs-lookup"><span data-stu-id="5fdc1-119">2: Backchat</span></span></p></li>
<li><p><span data-ttu-id="5fdc1-120">3: ファイルのダウンロード</span><span class="sxs-lookup"><span data-stu-id="5fdc1-120">3: File download</span></span></p></li>
<li><p><span data-ttu-id="5fdc1-121">4: ファイルのアップロード</span><span class="sxs-lookup"><span data-stu-id="5fdc1-121">4: File upload</span></span></p></li>
<li><p><span data-ttu-id="5fdc1-122">9: 暫定ファイル送信</span><span class="sxs-lookup"><span data-stu-id="5fdc1-122">9: Provisional file transfer</span></span></p></li>
<li><p><span data-ttu-id="5fdc1-123">10: チャットの削除 (置換あり)</span><span class="sxs-lookup"><span data-stu-id="5fdc1-123">10: Chat deletion (with replace)</span></span></p></li>
<li><p><span data-ttu-id="5fdc1-124">11: チャットの削除</span><span class="sxs-lookup"><span data-stu-id="5fdc1-124">11: Chat purging</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fdc1-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="5fdc1-125">cmplTime</span></span></p></td>
<td><p><span data-ttu-id="5fdc1-126">bigint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="5fdc1-126">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="5fdc1-127">イベントのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="5fdc1-127">Time stamp for the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fdc1-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="5fdc1-128">cmplChannelUri</span></span></p></td>
<td><p><span data-ttu-id="5fdc1-129">nvarchar (255)、null ではない</span><span class="sxs-lookup"><span data-stu-id="5fdc1-129">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="5fdc1-130">チャネルの Uniform Resource Identifier (URI)。</span><span class="sxs-lookup"><span data-stu-id="5fdc1-130">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fdc1-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="5fdc1-131">cmplChatID</span></span></p></td>
<td><p><span data-ttu-id="5fdc1-132">bigint</span><span class="sxs-lookup"><span data-stu-id="5fdc1-132">bigint</span></span></p></td>
<td><p><span data-ttu-id="5fdc1-133">チャット ID (chatId テーブルに対応する tblChat)。</span><span class="sxs-lookup"><span data-stu-id="5fdc1-133">Chat ID (corresponding to tblChat.chatId table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fdc1-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="5fdc1-134">cmplUserID</span></span></p></td>
<td><p><span data-ttu-id="5fdc1-135">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="5fdc1-135">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5fdc1-136">ポスターのプリンシパル ID (tblPrincipal ID テーブルに対応)</span><span class="sxs-lookup"><span data-stu-id="5fdc1-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fdc1-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="5fdc1-137">cmplUserUri</span></span></p></td>
<td><p><span data-ttu-id="5fdc1-138">nvarchar (255)、null ではない</span><span class="sxs-lookup"><span data-stu-id="5fdc1-138">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="5fdc1-139">ユーザー URI。</span><span class="sxs-lookup"><span data-stu-id="5fdc1-139">User URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fdc1-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="5fdc1-140">cmplMessage</span></span></p></td>
<td><p><span data-ttu-id="5fdc1-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="5fdc1-141">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="5fdc1-142">メッセージ (エンコードは、cmplType 型によって異なります)。</span><span class="sxs-lookup"><span data-stu-id="5fdc1-142">Message (encoding depends on cmplType).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="5fdc1-143">キー</span><span class="sxs-lookup"><span data-stu-id="5fdc1-143">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5fdc1-144">列</span><span class="sxs-lookup"><span data-stu-id="5fdc1-144">Column</span></span></th>
<th><span data-ttu-id="5fdc1-145">説明</span><span class="sxs-lookup"><span data-stu-id="5fdc1-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fdc1-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="5fdc1-146">cmplEventID</span></span></p></td>
<td><p><span data-ttu-id="5fdc1-147">主キー。</span><span class="sxs-lookup"><span data-stu-id="5fdc1-147">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

