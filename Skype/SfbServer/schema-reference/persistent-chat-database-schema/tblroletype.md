---
title: tblRoleType
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
ms.openlocfilehash: 2a380539c547f4ba6eb911f7e5247056c59a73ca
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblroletype"></a><span data-ttu-id="4b17d-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="4b17d-103">tblRoleType</span></span>
 
<span data-ttu-id="4b17d-104">tblRoleType は、ロールの種類とその関連付けられたアクセス許可セットの静的なルックアップ テーブルです。</span><span class="sxs-lookup"><span data-stu-id="4b17d-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="4b17d-105">**列**</span><span class="sxs-lookup"><span data-stu-id="4b17d-105">**Columns**</span></span>

|<span data-ttu-id="4b17d-106">**列**</span><span class="sxs-lookup"><span data-stu-id="4b17d-106">**Column**</span></span>|<span data-ttu-id="4b17d-107">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="4b17d-107">**Type**</span></span>|<span data-ttu-id="4b17d-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="4b17d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4b17d-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="4b17d-109">rtypeID</span></span>  <br/> |<span data-ttu-id="4b17d-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="4b17d-110">int, not null</span></span>  <br/> |<span data-ttu-id="4b17d-111">ロールの種類の id。</span><span class="sxs-lookup"><span data-stu-id="4b17d-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="4b17d-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="4b17d-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="4b17d-113">nvarchar (256)、null でないです。</span><span class="sxs-lookup"><span data-stu-id="4b17d-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="4b17d-114">ロールの種類の説明です。</span><span class="sxs-lookup"><span data-stu-id="4b17d-114">Role type description.</span></span> <span data-ttu-id="4b17d-115">次の 4 つの使用可能なロールがあります。</span><span class="sxs-lookup"><span data-stu-id="4b17d-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="4b17d-116">メンバー: チャット ルームのメンバー</span><span class="sxs-lookup"><span data-stu-id="4b17d-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="4b17d-117">: チャット ルーム マネージャー</span><span class="sxs-lookup"><span data-stu-id="4b17d-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="4b17d-118">聴衆のチャット ルームの発表者の濁点。</span><span class="sxs-lookup"><span data-stu-id="4b17d-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="4b17d-119">作成者: チャット ルームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4b17d-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="4b17d-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="4b17d-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="4b17d-121">bigint 型の値、null でないです。</span><span class="sxs-lookup"><span data-stu-id="4b17d-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="4b17d-122">アクセス許可がロールに設定します。</span><span class="sxs-lookup"><span data-stu-id="4b17d-122">Permission set for the role.</span></span> <span data-ttu-id="4b17d-123">使用されるビットは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4b17d-123">The used bits are:</span></span> <br/>  <span data-ttu-id="4b17d-124">2: 役割がノードを管理することができる場合は true です。</span><span class="sxs-lookup"><span data-stu-id="4b17d-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="4b17d-125">4: 役割がノードには子の作成できる場合に true を設定します。</span><span class="sxs-lookup"><span data-stu-id="4b17d-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="4b17d-126">7: 役割がチャット ルーム (またはカテゴリの子チャット ルーム) に参加できる場合に true を設定します。</span><span class="sxs-lookup"><span data-stu-id="4b17d-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="4b17d-127">8: 役割がチャット ルーム (またはカテゴリの子チャット ルーム) にチャットできる場合に true を設定します。</span><span class="sxs-lookup"><span data-stu-id="4b17d-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="4b17d-128">10: 役割がチャット ルームに参加していない場合でも、チャットの履歴を読み取ることができる場合に true を設定します。</span><span class="sxs-lookup"><span data-stu-id="4b17d-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="4b17d-129">11: 役割がチャット ルームを表示する場合に true を設定します。</span><span class="sxs-lookup"><span data-stu-id="4b17d-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="4b17d-130">(これはさらに洗練されているスコープと可視性などの要因によって。)</span><span class="sxs-lookup"><span data-stu-id="4b17d-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="4b17d-131">12: ロールが聴衆のチャット ルームでチャットできる場合に true を設定します。</span><span class="sxs-lookup"><span data-stu-id="4b17d-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="4b17d-132">13: 役割がノードを表示するときの可視性規則を省略できる場合に true を設定します。</span><span class="sxs-lookup"><span data-stu-id="4b17d-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="4b17d-133">**キー**</span><span class="sxs-lookup"><span data-stu-id="4b17d-133">**Key**</span></span>

|<span data-ttu-id="4b17d-134">**列**</span><span class="sxs-lookup"><span data-stu-id="4b17d-134">**Column**</span></span>|<span data-ttu-id="4b17d-135">**説明**</span><span class="sxs-lookup"><span data-stu-id="4b17d-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4b17d-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="4b17d-136">rtypeID</span></span>  <br/> |<span data-ttu-id="4b17d-137">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="4b17d-137">Primary key.</span></span>  <br/> |
   

