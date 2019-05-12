---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant には、チャネルおよびサーバーごとの現在の参加者が含まれています。
ms.openlocfilehash: 6644796d88f303c6614cbd73d98224fe0e41eabb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929939"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="927fa-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="927fa-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="927fa-104">tblComplianceParticipant には、チャネルおよびサーバーごとの現在の参加者が含まれています。</span><span class="sxs-lookup"><span data-stu-id="927fa-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="927fa-105">**列**</span><span class="sxs-lookup"><span data-stu-id="927fa-105">**Columns**</span></span>

|<span data-ttu-id="927fa-106">**列**</span><span class="sxs-lookup"><span data-stu-id="927fa-106">**Column**</span></span>|<span data-ttu-id="927fa-107">**型**</span><span class="sxs-lookup"><span data-stu-id="927fa-107">**Type**</span></span>|<span data-ttu-id="927fa-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="927fa-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="927fa-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="927fa-109">channelUri</span></span>  <br/> |<span data-ttu-id="927fa-110">nvarchar (255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="927fa-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="927fa-111">チャネルの一意リソース識別子 (URI)。</span><span class="sxs-lookup"><span data-stu-id="927fa-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="927fa-112">ユーザー Id</span><span class="sxs-lookup"><span data-stu-id="927fa-112">userId</span></span>  <br/> |<span data-ttu-id="927fa-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="927fa-113">int, not null</span></span>  <br/> |<span data-ttu-id="927fa-114">(TblPrincipal.prinID のテーブルに対応する) 関係者のプリンシパルの ID です。</span><span class="sxs-lookup"><span data-stu-id="927fa-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="927fa-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="927fa-115">joinedAt</span></span>  <br/> |<span data-ttu-id="927fa-116">bigint 型の値、null でないです。</span><span class="sxs-lookup"><span data-stu-id="927fa-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="927fa-117">参加するイベントのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="927fa-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="927fa-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="927fa-118">partedAt</span></span>  <br/> |<span data-ttu-id="927fa-119">bigint 型の値</span><span class="sxs-lookup"><span data-stu-id="927fa-119">bigint</span></span>  <br/> |<span data-ttu-id="927fa-120">参加者がまだ参加している場合は null です。</span><span class="sxs-lookup"><span data-stu-id="927fa-120">Null if participant is still joined.</span></span> <span data-ttu-id="927fa-121">チャンネルが null でない場合は、イベントをそのままのタイム ・ スタンプ。</span><span class="sxs-lookup"><span data-stu-id="927fa-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="927fa-122">すべての翻訳者がイベントを処理すると、最終的にはこれらのエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="927fa-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="927fa-123">userUri</span><span class="sxs-lookup"><span data-stu-id="927fa-123">userUri</span></span>  <br/> |<span data-ttu-id="927fa-124">nvarchar(255)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="927fa-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="927fa-125">ユーザー URI です。</span><span class="sxs-lookup"><span data-stu-id="927fa-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="927fa-126">serverID</span><span class="sxs-lookup"><span data-stu-id="927fa-126">serverID</span></span>  <br/> |<span data-ttu-id="927fa-127">int</span><span class="sxs-lookup"><span data-stu-id="927fa-127">int</span></span>  <br/> |<span data-ttu-id="927fa-128">(TblServerIdentity.serverID テーブル) と同様にサーバーの id。</span><span class="sxs-lookup"><span data-stu-id="927fa-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="927fa-129">セッション Id</span><span class="sxs-lookup"><span data-stu-id="927fa-129">sessionId</span></span>  <br/> |<span data-ttu-id="927fa-130">bigint 型の値</span><span class="sxs-lookup"><span data-stu-id="927fa-130">bigint</span></span>  <br/> |<span data-ttu-id="927fa-131">サーバーのセッションです。</span><span class="sxs-lookup"><span data-stu-id="927fa-131">Server session.</span></span> <span data-ttu-id="927fa-132">これは、チャット サービスが開始されるたびに生成されたランダムな番号です。</span><span class="sxs-lookup"><span data-stu-id="927fa-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="927fa-133">孤立した参加者を識別するためのセッションを区別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="927fa-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="927fa-134">**キー**</span><span class="sxs-lookup"><span data-stu-id="927fa-134">**Key**</span></span>

|<span data-ttu-id="927fa-135">**列**</span><span class="sxs-lookup"><span data-stu-id="927fa-135">**Column**</span></span>|<span data-ttu-id="927fa-136">**説明**</span><span class="sxs-lookup"><span data-stu-id="927fa-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="927fa-137">\<channelUri、ユーザー Id、joinedAt\></span><span class="sxs-lookup"><span data-stu-id="927fa-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="927fa-138">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="927fa-138">Primary key.</span></span>  <br/> |
   

