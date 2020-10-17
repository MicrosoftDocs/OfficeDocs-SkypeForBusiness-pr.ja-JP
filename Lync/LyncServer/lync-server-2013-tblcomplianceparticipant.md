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
ms.openlocfilehash: 0d6ce992f7a36bd5ce731f26dcb5dbfac0e2acae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509434"
---
# <a name="tblcomplianceparticipant-in-lync-server-2013"></a><span data-ttu-id="f5995-102">Lync Server 2013 の tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="f5995-102">tblComplianceParticipant in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5995-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f5995-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f5995-104">tblComplianceParticipant には、現在の参加者がチャネルおよびサーバー別に格納されます。</span><span class="sxs-lookup"><span data-stu-id="f5995-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>

### <a name="columns"></a><span data-ttu-id="f5995-105">段組み</span><span class="sxs-lookup"><span data-stu-id="f5995-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5995-106">Column</span><span class="sxs-lookup"><span data-stu-id="f5995-106">Column</span></span></th>
<th><span data-ttu-id="f5995-107">種類</span><span class="sxs-lookup"><span data-stu-id="f5995-107">Type</span></span></th>
<th><span data-ttu-id="f5995-108">説明</span><span class="sxs-lookup"><span data-stu-id="f5995-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5995-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="f5995-109">channelUri</span></span></p></td>
<td><p><span data-ttu-id="f5995-110">NULL でない nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="f5995-110">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="f5995-111">チャネルの URI (Uniform Resource Identifier)。</span><span class="sxs-lookup"><span data-stu-id="f5995-111">Channel Uniform Resource Identifier (URI).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5995-112">userId</span><span class="sxs-lookup"><span data-stu-id="f5995-112">userId</span></span></p></td>
<td><p><span data-ttu-id="f5995-113">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="f5995-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f5995-114">参加者のプリンシパル ID (tblPrincipal.prinID テーブルに対応)。</span><span class="sxs-lookup"><span data-stu-id="f5995-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5995-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="f5995-115">joinedAt</span></span></p></td>
<td><p><span data-ttu-id="f5995-116">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="f5995-116">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="f5995-117">参加イベントのタイム スタンプ。</span><span class="sxs-lookup"><span data-stu-id="f5995-117">Time stamp of the joining event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5995-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="f5995-118">partedAt</span></span></p></td>
<td><p><span data-ttu-id="f5995-119">bigint</span><span class="sxs-lookup"><span data-stu-id="f5995-119">bigint</span></span></p></td>
<td><p><span data-ttu-id="f5995-p101">参加者がまだ参加している場合は NULL。NULL でない場合は、チャネル退出イベントのタイム スタンプ。</span><span class="sxs-lookup"><span data-stu-id="f5995-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span></p>
<p><span data-ttu-id="f5995-122">これらのエントリは、すべてのトランスレーターがイベントを処理すると最終的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="f5995-122">These entries are eventually removed when all translators process the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5995-123">userUri</span><span class="sxs-lookup"><span data-stu-id="f5995-123">userUri</span></span></p></td>
<td><p><span data-ttu-id="f5995-124">NULL でない nvarchar(255)</span><span class="sxs-lookup"><span data-stu-id="f5995-124">nvarchar(255), not null</span></span></p></td>
<td><p><span data-ttu-id="f5995-125">ユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="f5995-125">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5995-126">serverID</span><span class="sxs-lookup"><span data-stu-id="f5995-126">serverID</span></span></p></td>
<td><p><span data-ttu-id="f5995-127">int</span><span class="sxs-lookup"><span data-stu-id="f5995-127">int</span></span></p></td>
<td><p><span data-ttu-id="f5995-128">サーバーの ID (tblServerIdentity.serverID テーブルなど)。</span><span class="sxs-lookup"><span data-stu-id="f5995-128">Server identity (as in tblServerIdentity.serverID table).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5995-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="f5995-129">sessionId</span></span></p></td>
<td><p><span data-ttu-id="f5995-130">bigint</span><span class="sxs-lookup"><span data-stu-id="f5995-130">bigint</span></span></p></td>
<td><p><span data-ttu-id="f5995-p102">サーバー セッション。チャット サービスが起動するたびに生成されるランダムな数値。孤立した参加者の識別を目的としたセッションの区別に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5995-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="f5995-134">キー</span><span class="sxs-lookup"><span data-stu-id="f5995-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5995-135">列</span><span class="sxs-lookup"><span data-stu-id="f5995-135">Column</span></span></th>
<th><span data-ttu-id="f5995-136">説明</span><span class="sxs-lookup"><span data-stu-id="f5995-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5995-137">&lt;channelUri、userId、joinedAt&gt;</span><span class="sxs-lookup"><span data-stu-id="f5995-137">&lt;channelUri, userId, joinedAt&gt;</span></span></p></td>
<td><p><span data-ttu-id="f5995-138">主キー。</span><span class="sxs-lookup"><span data-stu-id="f5995-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

