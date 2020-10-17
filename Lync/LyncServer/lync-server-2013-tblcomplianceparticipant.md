---
title: 'Lync Server 2013: tblComplianceParticipant'
description: 'Lync Server 2013: tblComplianceParticipant。'
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
ms.openlocfilehash: c1385b0a635f003a72de93f10f72642314ad7ebd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569073"
---
# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="2f20c-103">Lync Server 2013 の tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="2f20c-103">tblComplianceParticipant in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f20c-104">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2f20c-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2f20c-105">tblComplianceParticipant には、現在の参加者がチャネルおよびサーバー別に格納されます。</span><span class="sxs-lookup"><span data-stu-id="2f20c-105">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="2f20c-106">段組み</span><span class="sxs-lookup"><span data-stu-id="2f20c-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f20c-107">Column</span><span class="sxs-lookup"><span data-stu-id="2f20c-107">Column</span></span></th>
<th><span data-ttu-id="2f20c-108">種類</span><span class="sxs-lookup"><span data-stu-id="2f20c-108">Type</span></span></th>
<th><span data-ttu-id="2f20c-109">説明</span><span class="sxs-lookup"><span data-stu-id="2f20c-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f20c-110">channelUri</span><span class="sxs-lookup"><span data-stu-id="2f20c-110">channelUri</span></span></p></td>
<td><p><span data-ttu-id="2f20c-111">NULL でない nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="2f20c-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="2f20c-112">チャネルの URI (Uniform Resource Identifier)。</span><span class="sxs-lookup"><span data-stu-id="2f20c-112">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f20c-113">userId</span><span class="sxs-lookup"><span data-stu-id="2f20c-113">userId</span></span></p></td>
<td><p><span data-ttu-id="2f20c-114">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="2f20c-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2f20c-115">参加者のプリンシパル ID (tblPrincipal.prinID テーブルに対応)。</span><span class="sxs-lookup"><span data-stu-id="2f20c-115">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f20c-116">joinedAt</span><span class="sxs-lookup"><span data-stu-id="2f20c-116">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="2f20c-117">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="2f20c-117">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="2f20c-118">参加イベントのタイム スタンプ。</span><span class="sxs-lookup"><span data-stu-id="2f20c-118">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f20c-119">partedAt</span><span class="sxs-lookup"><span data-stu-id="2f20c-119">partedAt</span></span></p></td>
<td><p><span data-ttu-id="2f20c-120">bigint</span><span class="sxs-lookup"><span data-stu-id="2f20c-120">bigint</span></span></p></td>
<td><p><span data-ttu-id="2f20c-p101">参加者がまだ参加している場合は NULL。NULL でない場合は、チャネル退出イベントのタイム スタンプ。</span><span class="sxs-lookup"><span data-stu-id="2f20c-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="2f20c-123">これらのエントリは、すべてのトランスレーターがイベントを処理すると最終的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="2f20c-123">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f20c-124">userUri</span><span class="sxs-lookup"><span data-stu-id="2f20c-124">userUri</span></span></p></td>
<td><p><span data-ttu-id="2f20c-125">NULL でない nvarchar(255)</span><span class="sxs-lookup"><span data-stu-id="2f20c-125">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="2f20c-126">ユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="2f20c-126">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f20c-127">serverID</span><span class="sxs-lookup"><span data-stu-id="2f20c-127">serverID</span></span></p></td>
<td><p><span data-ttu-id="2f20c-128">int</span><span class="sxs-lookup"><span data-stu-id="2f20c-128">int</span></span></p></td>
<td><p><span data-ttu-id="2f20c-129">サーバーの ID (tblServerIdentity.serverID テーブルなど)。</span><span class="sxs-lookup"><span data-stu-id="2f20c-129">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f20c-130">sessionId</span><span class="sxs-lookup"><span data-stu-id="2f20c-130">sessionId</span></span></p></td>
<td><p><span data-ttu-id="2f20c-131">bigint</span><span class="sxs-lookup"><span data-stu-id="2f20c-131">bigint</span></span></p></td>
<td><p><span data-ttu-id="2f20c-p102">サーバー セッション。チャット サービスが起動するたびに生成されるランダムな数値。孤立した参加者の識別を目的としたセッションの区別に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2f20c-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="2f20c-135">キー</span><span class="sxs-lookup"><span data-stu-id="2f20c-135">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f20c-136">列</span><span class="sxs-lookup"><span data-stu-id="2f20c-136">Column</span></span></th>
<th><span data-ttu-id="2f20c-137">説明</span><span class="sxs-lookup"><span data-stu-id="2f20c-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f20c-138">&lt;channelUri、userId、joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="2f20c-138">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="2f20c-139">主キー。</span><span class="sxs-lookup"><span data-stu-id="2f20c-139">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

