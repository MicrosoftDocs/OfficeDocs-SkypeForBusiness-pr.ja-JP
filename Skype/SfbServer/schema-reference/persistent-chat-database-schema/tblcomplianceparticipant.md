---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant には、チャネルおよびサーバーごとの現在の参加者が含まれています。
ms.openlocfilehash: a3d18c4a78af2892a837e1105a435a3ce46ea14b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881417"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="60237-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="60237-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="60237-104">tblComplianceParticipant には、チャネルおよびサーバーごとの現在の参加者が含まれています。</span><span class="sxs-lookup"><span data-stu-id="60237-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="60237-105">**列**</span><span class="sxs-lookup"><span data-stu-id="60237-105">**Columns**</span></span>

|<span data-ttu-id="60237-106">**列**</span><span class="sxs-lookup"><span data-stu-id="60237-106">**Column**</span></span>|<span data-ttu-id="60237-107">**型**</span><span class="sxs-lookup"><span data-stu-id="60237-107">**Type**</span></span>|<span data-ttu-id="60237-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="60237-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="60237-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="60237-109">channelUri</span></span>  <br/> |<span data-ttu-id="60237-110">nvarchar (255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="60237-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="60237-111">チャネルの一意リソース識別子 (URI)。</span><span class="sxs-lookup"><span data-stu-id="60237-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="60237-112">ユーザー Id</span><span class="sxs-lookup"><span data-stu-id="60237-112">userId</span></span>  <br/> |<span data-ttu-id="60237-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="60237-113">int, not null</span></span>  <br/> |<span data-ttu-id="60237-114">(TblPrincipal.prinID のテーブルに対応する) 関係者のプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="60237-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="60237-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="60237-115">joinedAt</span></span>  <br/> |<span data-ttu-id="60237-116">bigint 型の値、null でないです。</span><span class="sxs-lookup"><span data-stu-id="60237-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="60237-117">参加するイベントのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="60237-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="60237-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="60237-118">partedAt</span></span>  <br/> |<span data-ttu-id="60237-119">bigint 型の値</span><span class="sxs-lookup"><span data-stu-id="60237-119">bigint</span></span>  <br/> |<span data-ttu-id="60237-120">参加者がまだ参加している場合は null です。</span><span class="sxs-lookup"><span data-stu-id="60237-120">Null if participant is still joined.</span></span> <span data-ttu-id="60237-121">チャンネルが null でない場合は、イベントをそのままのタイム ・ スタンプ。</span><span class="sxs-lookup"><span data-stu-id="60237-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="60237-122">すべての翻訳者がイベントを処理すると、最終的にはこれらのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="60237-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="60237-123">userUri</span><span class="sxs-lookup"><span data-stu-id="60237-123">userUri</span></span>  <br/> |<span data-ttu-id="60237-124">nvarchar(255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="60237-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="60237-125">ユーザー URI です。</span><span class="sxs-lookup"><span data-stu-id="60237-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="60237-126">serverID</span><span class="sxs-lookup"><span data-stu-id="60237-126">serverID</span></span>  <br/> |<span data-ttu-id="60237-127">int</span><span class="sxs-lookup"><span data-stu-id="60237-127">int</span></span>  <br/> |<span data-ttu-id="60237-128">(TblServerIdentity.serverID テーブル) と同様にサーバーの id。</span><span class="sxs-lookup"><span data-stu-id="60237-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="60237-129">セッション Id</span><span class="sxs-lookup"><span data-stu-id="60237-129">sessionId</span></span>  <br/> |<span data-ttu-id="60237-130">bigint 型の値</span><span class="sxs-lookup"><span data-stu-id="60237-130">bigint</span></span>  <br/> |<span data-ttu-id="60237-131">サーバーのセッションです。</span><span class="sxs-lookup"><span data-stu-id="60237-131">Server session.</span></span> <span data-ttu-id="60237-132">これは、チャット サービスが開始されるたびに生成されたランダムな番号です。</span><span class="sxs-lookup"><span data-stu-id="60237-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="60237-133">孤立した参加者を識別するためのセッションを区別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="60237-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="60237-134">**キー**</span><span class="sxs-lookup"><span data-stu-id="60237-134">**Key**</span></span>

|<span data-ttu-id="60237-135">**列**</span><span class="sxs-lookup"><span data-stu-id="60237-135">**Column**</span></span>|<span data-ttu-id="60237-136">**説明**</span><span class="sxs-lookup"><span data-stu-id="60237-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="60237-137">\<channelUri、ユーザー Id、joinedAt\></span><span class="sxs-lookup"><span data-stu-id="60237-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="60237-138">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="60237-138">Primary key.</span></span>  <br/> |
   

