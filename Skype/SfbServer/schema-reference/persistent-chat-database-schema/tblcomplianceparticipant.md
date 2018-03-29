---
title: tblComplianceParticipant
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
ms.openlocfilehash: ba488f377592b48845880acaeed61074bc31ccd2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="ade32-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="ade32-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="ade32-104">tblComplianceParticipant には、チャネルおよびサーバーごとの現在の参加者が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ade32-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="ade32-105">**列**</span><span class="sxs-lookup"><span data-stu-id="ade32-105">**Columns**</span></span>

|<span data-ttu-id="ade32-106">**列**</span><span class="sxs-lookup"><span data-stu-id="ade32-106">**Column**</span></span>|<span data-ttu-id="ade32-107">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="ade32-107">**Type**</span></span>|<span data-ttu-id="ade32-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="ade32-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ade32-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="ade32-109">channelUri</span></span>  <br/> |<span data-ttu-id="ade32-110">nvarchar (255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="ade32-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="ade32-111">チャネルの一意リソース識別子 (URI)。</span><span class="sxs-lookup"><span data-stu-id="ade32-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="ade32-112">ユーザー Id</span><span class="sxs-lookup"><span data-stu-id="ade32-112">userId</span></span>  <br/> |<span data-ttu-id="ade32-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="ade32-113">int, not null</span></span>  <br/> |<span data-ttu-id="ade32-114">(TblPrincipal.prinID のテーブルに対応する) 関係者のプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="ade32-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="ade32-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="ade32-115">joinedAt</span></span>  <br/> |<span data-ttu-id="ade32-116">bigint 型の値、null でないです。</span><span class="sxs-lookup"><span data-stu-id="ade32-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="ade32-117">参加するイベントのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="ade32-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="ade32-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="ade32-118">partedAt</span></span>  <br/> |<span data-ttu-id="ade32-119">bigint 型の値</span><span class="sxs-lookup"><span data-stu-id="ade32-119">bigint</span></span>  <br/> |<span data-ttu-id="ade32-120">参加者がまだ参加している場合は null です。</span><span class="sxs-lookup"><span data-stu-id="ade32-120">Null if participant is still joined.</span></span> <span data-ttu-id="ade32-121">チャンネルが null でない場合は、イベントをそのままのタイム ・ スタンプ。</span><span class="sxs-lookup"><span data-stu-id="ade32-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="ade32-122">すべての翻訳者がイベントを処理すると、最終的にはこれらのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="ade32-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="ade32-123">userUri</span><span class="sxs-lookup"><span data-stu-id="ade32-123">userUri</span></span>  <br/> |<span data-ttu-id="ade32-124">nvarchar(255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="ade32-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="ade32-125">ユーザー URI です。</span><span class="sxs-lookup"><span data-stu-id="ade32-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="ade32-126">serverID</span><span class="sxs-lookup"><span data-stu-id="ade32-126">serverID</span></span>  <br/> |<span data-ttu-id="ade32-127">int</span><span class="sxs-lookup"><span data-stu-id="ade32-127">int</span></span>  <br/> |<span data-ttu-id="ade32-128">(TblServerIdentity.serverID テーブル) と同様にサーバーの id。</span><span class="sxs-lookup"><span data-stu-id="ade32-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="ade32-129">セッション Id</span><span class="sxs-lookup"><span data-stu-id="ade32-129">sessionId</span></span>  <br/> |<span data-ttu-id="ade32-130">bigint 型の値</span><span class="sxs-lookup"><span data-stu-id="ade32-130">bigint</span></span>  <br/> |<span data-ttu-id="ade32-131">サーバーのセッションです。</span><span class="sxs-lookup"><span data-stu-id="ade32-131">Server session.</span></span> <span data-ttu-id="ade32-132">これは、チャット サービスが開始されるたびに生成されたランダムな番号です。</span><span class="sxs-lookup"><span data-stu-id="ade32-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="ade32-133">孤立した参加者を識別するためのセッションを区別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ade32-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="ade32-134">**キー**</span><span class="sxs-lookup"><span data-stu-id="ade32-134">**Key**</span></span>

|<span data-ttu-id="ade32-135">**列**</span><span class="sxs-lookup"><span data-stu-id="ade32-135">**Column**</span></span>|<span data-ttu-id="ade32-136">**説明**</span><span class="sxs-lookup"><span data-stu-id="ade32-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ade32-137">\<channelUri、ユーザー Id、joinedAt\></span><span class="sxs-lookup"><span data-stu-id="ade32-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="ade32-138">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="ade32-138">Primary key.</span></span>  <br/> |
   

