---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant には、チャネルあたり、サーバーごとに現在の参加者が含まれています。
ms.openlocfilehash: bf6913d8bcc11db1589169c4479cec4a0238825d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295462"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="c1443-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="c1443-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="c1443-104">tblComplianceParticipant には、チャネルあたり、サーバーごとに現在の参加者が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c1443-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="c1443-105">**行**</span><span class="sxs-lookup"><span data-stu-id="c1443-105">**Columns**</span></span>

|<span data-ttu-id="c1443-106">**列**</span><span class="sxs-lookup"><span data-stu-id="c1443-106">**Column**</span></span>|<span data-ttu-id="c1443-107">**型**</span><span class="sxs-lookup"><span data-stu-id="c1443-107">**Type**</span></span>|<span data-ttu-id="c1443-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="c1443-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c1443-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="c1443-109">channelUri</span></span>  <br/> |<span data-ttu-id="c1443-110">nvarchar (255)、null ではない</span><span class="sxs-lookup"><span data-stu-id="c1443-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="c1443-111">チャネルの Uniform Resource Identifier (URI)。</span><span class="sxs-lookup"><span data-stu-id="c1443-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="c1443-112">userId</span><span class="sxs-lookup"><span data-stu-id="c1443-112">userId</span></span>  <br/> |<span data-ttu-id="c1443-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="c1443-113">int, not null</span></span>  <br/> |<span data-ttu-id="c1443-114">参加者のプリンシパル ID (tblPrincipal ID テーブルに対応)</span><span class="sxs-lookup"><span data-stu-id="c1443-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="c1443-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="c1443-115">joinedAt</span></span>  <br/> |<span data-ttu-id="c1443-116">bigint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="c1443-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="c1443-117">参加イベントのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="c1443-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="c1443-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="c1443-118">partedAt</span></span>  <br/> |<span data-ttu-id="c1443-119">bigint</span><span class="sxs-lookup"><span data-stu-id="c1443-119">bigint</span></span>  <br/> |<span data-ttu-id="c1443-120">参加者がまだ参加している場合は Null です。</span><span class="sxs-lookup"><span data-stu-id="c1443-120">Null if participant is still joined.</span></span> <span data-ttu-id="c1443-121">チャネルが null でない場合は、チャネルのタイムスタンプがイベントから出ます。</span><span class="sxs-lookup"><span data-stu-id="c1443-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="c1443-122">これらのエントリは、すべての翻訳者がイベントを処理すると、最終的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="c1443-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="c1443-123">userUri</span><span class="sxs-lookup"><span data-stu-id="c1443-123">userUri</span></span>  <br/> |<span data-ttu-id="c1443-124">nvarchar (255)、null ではない</span><span class="sxs-lookup"><span data-stu-id="c1443-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="c1443-125">ユーザー URI。</span><span class="sxs-lookup"><span data-stu-id="c1443-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="c1443-126">serverID</span><span class="sxs-lookup"><span data-stu-id="c1443-126">serverID</span></span>  <br/> |<span data-ttu-id="c1443-127">int</span><span class="sxs-lookup"><span data-stu-id="c1443-127">int</span></span>  <br/> |<span data-ttu-id="c1443-128">サーバー id (serverID テーブルの場合)。</span><span class="sxs-lookup"><span data-stu-id="c1443-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="c1443-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="c1443-129">sessionId</span></span>  <br/> |<span data-ttu-id="c1443-130">bigint</span><span class="sxs-lookup"><span data-stu-id="c1443-130">bigint</span></span>  <br/> |<span data-ttu-id="c1443-131">サーバーセッション。</span><span class="sxs-lookup"><span data-stu-id="c1443-131">Server session.</span></span> <span data-ttu-id="c1443-132">これは、チャットサービスが開始されるたびに生成されるランダムな番号です。</span><span class="sxs-lookup"><span data-stu-id="c1443-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="c1443-133">これは、孤立した参加者を識別する目的でセッションを区別するために使われます。</span><span class="sxs-lookup"><span data-stu-id="c1443-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="c1443-134">**キー**</span><span class="sxs-lookup"><span data-stu-id="c1443-134">**Key**</span></span>

|<span data-ttu-id="c1443-135">**列**</span><span class="sxs-lookup"><span data-stu-id="c1443-135">**Column**</span></span>|<span data-ttu-id="c1443-136">**説明**</span><span class="sxs-lookup"><span data-stu-id="c1443-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c1443-137">\<channelUri、userId、joinedAt\></span><span class="sxs-lookup"><span data-stu-id="c1443-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="c1443-138">主キー。</span><span class="sxs-lookup"><span data-stu-id="c1443-138">Primary key.</span></span>  <br/> |
   

