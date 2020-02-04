---
title: 'Lync Server 2013: tblComplianceParticipant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 484948a01c82dc8ca256e3e50e484c94a9b81de4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="fc5de-102">Lync Server 2013 内の tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="fc5de-102">tblComplianceParticipant in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc5de-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="fc5de-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="fc5de-104">tblComplianceParticipant には、チャネルあたり、サーバーごとに現在の参加者が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fc5de-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="fc5de-105">行</span><span class="sxs-lookup"><span data-stu-id="fc5de-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fc5de-106">列</span><span class="sxs-lookup"><span data-stu-id="fc5de-106">Column</span></span></th>
<th><span data-ttu-id="fc5de-107">型</span><span class="sxs-lookup"><span data-stu-id="fc5de-107">Type</span></span></th>
<th><span data-ttu-id="fc5de-108">説明</span><span class="sxs-lookup"><span data-stu-id="fc5de-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc5de-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="fc5de-109">channelUri</span></span></p></td>
<td><p><span data-ttu-id="fc5de-110">nvarchar (255)、null ではない</span><span class="sxs-lookup"><span data-stu-id="fc5de-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="fc5de-111">チャネルの Uniform Resource Identifier (URI)。</span><span class="sxs-lookup"><span data-stu-id="fc5de-111">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc5de-112">userId</span><span class="sxs-lookup"><span data-stu-id="fc5de-112">userId</span></span></p></td>
<td><p><span data-ttu-id="fc5de-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="fc5de-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fc5de-114">参加者のプリンシパル ID (tblPrincipal ID テーブルに対応)</span><span class="sxs-lookup"><span data-stu-id="fc5de-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc5de-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="fc5de-115">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="fc5de-116">bigint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="fc5de-116">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="fc5de-117">参加イベントのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="fc5de-117">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc5de-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="fc5de-118">partedAt</span></span></p></td>
<td><p><span data-ttu-id="fc5de-119">bigint</span><span class="sxs-lookup"><span data-stu-id="fc5de-119">bigint</span></span></p></td>
<td><p><span data-ttu-id="fc5de-120">参加者がまだ参加している場合は Null です。</span><span class="sxs-lookup"><span data-stu-id="fc5de-120">Null if participant is still joined.</span></span> <span data-ttu-id="fc5de-121">チャネルが null でない場合は、チャネルのタイムスタンプがイベントから出ます。</span><span class="sxs-lookup"><span data-stu-id="fc5de-121">The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="fc5de-122">これらのエントリは、すべての翻訳者がイベントを処理すると、最終的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="fc5de-122">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc5de-123">userUri</span><span class="sxs-lookup"><span data-stu-id="fc5de-123">userUri</span></span></p></td>
<td><p><span data-ttu-id="fc5de-124">nvarchar (255)、null ではない</span><span class="sxs-lookup"><span data-stu-id="fc5de-124">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="fc5de-125">ユーザー URI。</span><span class="sxs-lookup"><span data-stu-id="fc5de-125">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fc5de-126">serverID</span><span class="sxs-lookup"><span data-stu-id="fc5de-126">serverID</span></span></p></td>
<td><p><span data-ttu-id="fc5de-127">int</span><span class="sxs-lookup"><span data-stu-id="fc5de-127">int</span></span></p></td>
<td><p><span data-ttu-id="fc5de-128">サーバー id (serverID テーブルの場合)。</span><span class="sxs-lookup"><span data-stu-id="fc5de-128">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fc5de-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="fc5de-129">sessionId</span></span></p></td>
<td><p><span data-ttu-id="fc5de-130">bigint</span><span class="sxs-lookup"><span data-stu-id="fc5de-130">bigint</span></span></p></td>
<td><p><span data-ttu-id="fc5de-131">サーバーセッション。</span><span class="sxs-lookup"><span data-stu-id="fc5de-131">Server session.</span></span> <span data-ttu-id="fc5de-132">これは、チャットサービスが開始されるたびに生成されるランダムな番号です。</span><span class="sxs-lookup"><span data-stu-id="fc5de-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="fc5de-133">これは、孤立した参加者を識別する目的でセッションを区別するために使われます。</span><span class="sxs-lookup"><span data-stu-id="fc5de-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="fc5de-134">キー</span><span class="sxs-lookup"><span data-stu-id="fc5de-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fc5de-135">列</span><span class="sxs-lookup"><span data-stu-id="fc5de-135">Column</span></span></th>
<th><span data-ttu-id="fc5de-136">説明</span><span class="sxs-lookup"><span data-stu-id="fc5de-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fc5de-137">&lt;channelUri、userId、joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="fc5de-137">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="fc5de-138">主キー。</span><span class="sxs-lookup"><span data-stu-id="fc5de-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

