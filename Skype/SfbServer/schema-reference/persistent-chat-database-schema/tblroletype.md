---
title: tblRoleType
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType は、ロールの種類とその関連付けられたアクセス許可セットの静的なルックアップ テーブルです。
ms.openlocfilehash: 6b5e545306c402fbfb89094a19799fe3ff6d2e34
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883146"
---
# <a name="tblroletype"></a><span data-ttu-id="2e303-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="2e303-103">tblRoleType</span></span>
 
<span data-ttu-id="2e303-104">tblRoleType は、ロールの種類とその関連付けられたアクセス許可セットの静的なルックアップ テーブルです。</span><span class="sxs-lookup"><span data-stu-id="2e303-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="2e303-105">**列**</span><span class="sxs-lookup"><span data-stu-id="2e303-105">**Columns**</span></span>

|<span data-ttu-id="2e303-106">**列**</span><span class="sxs-lookup"><span data-stu-id="2e303-106">**Column**</span></span>|<span data-ttu-id="2e303-107">**型**</span><span class="sxs-lookup"><span data-stu-id="2e303-107">**Type**</span></span>|<span data-ttu-id="2e303-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="2e303-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2e303-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="2e303-109">rtypeID</span></span>  <br/> |<span data-ttu-id="2e303-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="2e303-110">int, not null</span></span>  <br/> |<span data-ttu-id="2e303-111">ロールの種類の id。</span><span class="sxs-lookup"><span data-stu-id="2e303-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="2e303-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="2e303-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="2e303-113">nvarchar (256)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="2e303-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="2e303-114">ロールの種類の説明です。</span><span class="sxs-lookup"><span data-stu-id="2e303-114">Role type description.</span></span> <span data-ttu-id="2e303-115">次の 4 つの使用可能なロールがあります。</span><span class="sxs-lookup"><span data-stu-id="2e303-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="2e303-116">メンバー: チャット ルームのメンバー</span><span class="sxs-lookup"><span data-stu-id="2e303-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="2e303-117">: チャット ルーム マネージャー</span><span class="sxs-lookup"><span data-stu-id="2e303-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="2e303-118">聴衆のチャット ルームの発表者の濁点。</span><span class="sxs-lookup"><span data-stu-id="2e303-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="2e303-119">作成者: チャット ルームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2e303-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="2e303-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="2e303-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="2e303-121">bigint 型の値、null でないです。</span><span class="sxs-lookup"><span data-stu-id="2e303-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="2e303-122">アクセス許可がロールに設定します。</span><span class="sxs-lookup"><span data-stu-id="2e303-122">Permission set for the role.</span></span> <span data-ttu-id="2e303-123">使用されるビットは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2e303-123">The used bits are:</span></span> <br/>  <span data-ttu-id="2e303-124">2: 役割がノードを管理することができる場合は true です。</span><span class="sxs-lookup"><span data-stu-id="2e303-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="2e303-125">4: 役割がノードには子の作成できる場合に true を設定します。</span><span class="sxs-lookup"><span data-stu-id="2e303-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="2e303-126">7: 役割がチャット ルーム (またはカテゴリの子チャット ルーム) に参加できる場合に true を設定します。</span><span class="sxs-lookup"><span data-stu-id="2e303-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="2e303-127">8: 役割がチャット ルーム (またはカテゴリの子チャット ルーム) にチャットできる場合に true を設定します。</span><span class="sxs-lookup"><span data-stu-id="2e303-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="2e303-128">10: 役割がチャット ルームに参加していない場合でも、チャットの履歴を読み取ることができる場合に true を設定します。</span><span class="sxs-lookup"><span data-stu-id="2e303-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="2e303-129">11: 役割がチャット ルームを表示する場合に true を設定します。</span><span class="sxs-lookup"><span data-stu-id="2e303-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="2e303-130">(これはさらに洗練されているスコープと可視性などの要因によって。)</span><span class="sxs-lookup"><span data-stu-id="2e303-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="2e303-131">12: ロールが聴衆のチャット ルームでチャットできる場合に true を設定します。</span><span class="sxs-lookup"><span data-stu-id="2e303-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="2e303-132">13: 役割がノードを表示するときの可視性規則を省略できる場合に true を設定します。</span><span class="sxs-lookup"><span data-stu-id="2e303-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="2e303-133">**キー**</span><span class="sxs-lookup"><span data-stu-id="2e303-133">**Key**</span></span>

|<span data-ttu-id="2e303-134">**列**</span><span class="sxs-lookup"><span data-stu-id="2e303-134">**Column**</span></span>|<span data-ttu-id="2e303-135">**説明**</span><span class="sxs-lookup"><span data-stu-id="2e303-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2e303-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="2e303-136">rtypeID</span></span>  <br/> |<span data-ttu-id="2e303-137">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="2e303-137">Primary key.</span></span>  <br/> |
   

