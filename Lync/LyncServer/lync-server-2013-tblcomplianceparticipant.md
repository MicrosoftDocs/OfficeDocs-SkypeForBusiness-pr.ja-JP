---
title: 'Lync Server 2013: tblComplianceParticipant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e98b257552f728d0976df6331673f1f55d0dbdeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="45149-102">Lync Server 2013 内の tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="45149-102">tblComplianceParticipant in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45149-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="45149-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="45149-104">tblComplianceParticipant には、チャネルあたり、サーバーごとに現在の参加者が含まれています。</span><span class="sxs-lookup"><span data-stu-id="45149-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="45149-105">行</span><span class="sxs-lookup"><span data-stu-id="45149-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45149-106">列</span><span class="sxs-lookup"><span data-stu-id="45149-106">Column</span></span></th>
<th><span data-ttu-id="45149-107">型</span><span class="sxs-lookup"><span data-stu-id="45149-107">Type</span></span></th>
<th><span data-ttu-id="45149-108">説明</span><span class="sxs-lookup"><span data-stu-id="45149-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45149-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="45149-109">channelUri</span></span></p></td>
<td><p><span data-ttu-id="45149-110">nvarchar (255)、null ではない</span><span class="sxs-lookup"><span data-stu-id="45149-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="45149-111">チャネルの Uniform Resource Identifier (URI)。</span><span class="sxs-lookup"><span data-stu-id="45149-111">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45149-112">userId</span><span class="sxs-lookup"><span data-stu-id="45149-112">userId</span></span></p></td>
<td><p><span data-ttu-id="45149-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="45149-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="45149-114">参加者のプリンシパル ID (tblPrincipal ID テーブルに対応)</span><span class="sxs-lookup"><span data-stu-id="45149-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45149-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="45149-115">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="45149-116">bigint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="45149-116">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="45149-117">参加イベントのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="45149-117">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45149-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="45149-118">partedAt</span></span></p></td>
<td><p><span data-ttu-id="45149-119">bigint</span><span class="sxs-lookup"><span data-stu-id="45149-119">bigint</span></span></p></td>
<td><p><span data-ttu-id="45149-120">参加者がまだ参加している場合は Null です。</span><span class="sxs-lookup"><span data-stu-id="45149-120">Null if participant is still joined.</span></span> <span data-ttu-id="45149-121">チャネルが null でない場合は、チャネルのタイムスタンプがイベントから出ます。</span><span class="sxs-lookup"><span data-stu-id="45149-121">The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="45149-122">これらのエントリは、すべての翻訳者がイベントを処理すると、最終的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="45149-122">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45149-123">userUri</span><span class="sxs-lookup"><span data-stu-id="45149-123">userUri</span></span></p></td>
<td><p><span data-ttu-id="45149-124">nvarchar (255)、null ではない</span><span class="sxs-lookup"><span data-stu-id="45149-124">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="45149-125">ユーザー URI。</span><span class="sxs-lookup"><span data-stu-id="45149-125">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45149-126">serverID</span><span class="sxs-lookup"><span data-stu-id="45149-126">serverID</span></span></p></td>
<td><p><span data-ttu-id="45149-127">int</span><span class="sxs-lookup"><span data-stu-id="45149-127">int</span></span></p></td>
<td><p><span data-ttu-id="45149-128">サーバー id (serverID テーブルの場合)。</span><span class="sxs-lookup"><span data-stu-id="45149-128">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45149-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="45149-129">sessionId</span></span></p></td>
<td><p><span data-ttu-id="45149-130">bigint</span><span class="sxs-lookup"><span data-stu-id="45149-130">bigint</span></span></p></td>
<td><p><span data-ttu-id="45149-131">サーバーセッション。</span><span class="sxs-lookup"><span data-stu-id="45149-131">Server session.</span></span> <span data-ttu-id="45149-132">これは、チャットサービスが開始されるたびに生成されるランダムな番号です。</span><span class="sxs-lookup"><span data-stu-id="45149-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="45149-133">これは、孤立した参加者を識別する目的でセッションを区別するために使われます。</span><span class="sxs-lookup"><span data-stu-id="45149-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="45149-134">キー</span><span class="sxs-lookup"><span data-stu-id="45149-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45149-135">列</span><span class="sxs-lookup"><span data-stu-id="45149-135">Column</span></span></th>
<th><span data-ttu-id="45149-136">説明</span><span class="sxs-lookup"><span data-stu-id="45149-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45149-137">&lt;channelUri、userId、joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="45149-137">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="45149-138">主キー。</span><span class="sxs-lookup"><span data-stu-id="45149-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

