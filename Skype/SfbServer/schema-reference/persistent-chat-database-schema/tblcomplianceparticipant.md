---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant には、現在の参加者がチャネルおよびサーバー別に格納されます。
ms.openlocfilehash: c6aae3c1e7b13456708034512c6b68d67d6d1f92
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809747"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="98858-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="98858-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="98858-104">tblComplianceParticipant には、現在の参加者がチャネルおよびサーバー別に格納されます。</span><span class="sxs-lookup"><span data-stu-id="98858-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="98858-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="98858-105">**Columns**</span></span>

|<span data-ttu-id="98858-106">**列**</span><span class="sxs-lookup"><span data-stu-id="98858-106">**Column**</span></span>|<span data-ttu-id="98858-107">**型**</span><span class="sxs-lookup"><span data-stu-id="98858-107">**Type**</span></span>|<span data-ttu-id="98858-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="98858-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="98858-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="98858-109">channelUri</span></span>  <br/> |<span data-ttu-id="98858-110">NULL でない nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="98858-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="98858-111">チャネルの URI (Uniform Resource Identifier)。</span><span class="sxs-lookup"><span data-stu-id="98858-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="98858-112">userId</span><span class="sxs-lookup"><span data-stu-id="98858-112">userId</span></span>  <br/> |<span data-ttu-id="98858-113">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="98858-113">int, not null</span></span>  <br/> |<span data-ttu-id="98858-114">参加者のプリンシパル ID (tblPrincipal.prinID テーブルに対応)。</span><span class="sxs-lookup"><span data-stu-id="98858-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="98858-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="98858-115">joinedAt</span></span>  <br/> |<span data-ttu-id="98858-116">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="98858-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="98858-117">参加イベントのタイム スタンプ。</span><span class="sxs-lookup"><span data-stu-id="98858-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="98858-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="98858-118">partedAt</span></span>  <br/> |<span data-ttu-id="98858-119">bigint</span><span class="sxs-lookup"><span data-stu-id="98858-119">bigint</span></span>  <br/> |<span data-ttu-id="98858-p101">参加者がまだ参加している場合は NULL。NULL でない場合は、チャネル退出イベントのタイム スタンプ。</span><span class="sxs-lookup"><span data-stu-id="98858-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="98858-122">これらのエントリは、すべてのトランスレーターがイベントを処理すると最終的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="98858-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="98858-123">userUri</span><span class="sxs-lookup"><span data-stu-id="98858-123">userUri</span></span>  <br/> |<span data-ttu-id="98858-124">NULL でない nvarchar(255)</span><span class="sxs-lookup"><span data-stu-id="98858-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="98858-125">ユーザーの URI。</span><span class="sxs-lookup"><span data-stu-id="98858-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="98858-126">serverID</span><span class="sxs-lookup"><span data-stu-id="98858-126">serverID</span></span>  <br/> |<span data-ttu-id="98858-127">int</span><span class="sxs-lookup"><span data-stu-id="98858-127">int</span></span>  <br/> |<span data-ttu-id="98858-128">サーバーの ID (tblServerIdentity.serverID テーブルなど)。</span><span class="sxs-lookup"><span data-stu-id="98858-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="98858-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="98858-129">sessionId</span></span>  <br/> |<span data-ttu-id="98858-130">bigint</span><span class="sxs-lookup"><span data-stu-id="98858-130">bigint</span></span>  <br/> |<span data-ttu-id="98858-p102">サーバー セッション。チャット サービスが起動するたびに生成されるランダムな数値。孤立した参加者の識別を目的としたセッションの区別に使用されます。</span><span class="sxs-lookup"><span data-stu-id="98858-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="98858-134">**キー**</span><span class="sxs-lookup"><span data-stu-id="98858-134">**Key**</span></span>

|<span data-ttu-id="98858-135">**列**</span><span class="sxs-lookup"><span data-stu-id="98858-135">**Column**</span></span>|<span data-ttu-id="98858-136">**説明**</span><span class="sxs-lookup"><span data-stu-id="98858-136">**Description**</span></span>|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |<span data-ttu-id="98858-137">主キー。</span><span class="sxs-lookup"><span data-stu-id="98858-137">Primary key.</span></span>  <br/> |
   

