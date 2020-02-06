---
title: tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType は、役割の種類とそれに関連付けられたアクセス許可セットを含む静的参照テーブルです。
ms.openlocfilehash: 888628c1aca01e90694ed946569a81b1b7394b95
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812905"
---
# <a name="tblroletype"></a><span data-ttu-id="40c7c-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="40c7c-103">tblRoleType</span></span>
 
<span data-ttu-id="40c7c-104">tblRoleType は、役割の種類とそれに関連付けられたアクセス許可セットを含む静的参照テーブルです。</span><span class="sxs-lookup"><span data-stu-id="40c7c-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="40c7c-105">**行**</span><span class="sxs-lookup"><span data-stu-id="40c7c-105">**Columns**</span></span>

|<span data-ttu-id="40c7c-106">**列**</span><span class="sxs-lookup"><span data-stu-id="40c7c-106">**Column**</span></span>|<span data-ttu-id="40c7c-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="40c7c-107">**Type**</span></span>|<span data-ttu-id="40c7c-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="40c7c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="40c7c-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="40c7c-109">rtypeID</span></span>  <br/> |<span data-ttu-id="40c7c-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="40c7c-110">int, not null</span></span>  <br/> |<span data-ttu-id="40c7c-111">役割の種類 ID。</span><span class="sxs-lookup"><span data-stu-id="40c7c-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="40c7c-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="40c7c-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="40c7c-113">nvarchar (256)、null ではない</span><span class="sxs-lookup"><span data-stu-id="40c7c-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="40c7c-114">役割の種類の説明。</span><span class="sxs-lookup"><span data-stu-id="40c7c-114">Role type description.</span></span> <span data-ttu-id="40c7c-115">次の4つの役割を使用できます。</span><span class="sxs-lookup"><span data-stu-id="40c7c-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="40c7c-116">メンバー: チャットルームのメンバー</span><span class="sxs-lookup"><span data-stu-id="40c7c-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="40c7c-117">管理職: チャットルームマネージャー</span><span class="sxs-lookup"><span data-stu-id="40c7c-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="40c7c-118">読み上げ: 聴衆チャットルームの発表者</span><span class="sxs-lookup"><span data-stu-id="40c7c-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="40c7c-119">作成者: チャットルームを作成できる</span><span class="sxs-lookup"><span data-stu-id="40c7c-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="40c7c-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="40c7c-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="40c7c-121">bigint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="40c7c-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="40c7c-122">ロールの権限セット。</span><span class="sxs-lookup"><span data-stu-id="40c7c-122">Permission set for the role.</span></span> <span data-ttu-id="40c7c-123">使用されるビットは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="40c7c-123">The used bits are:</span></span> <br/>  <span data-ttu-id="40c7c-124">2: 役割がノードを管理できる場合は True。</span><span class="sxs-lookup"><span data-stu-id="40c7c-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="40c7c-125">4: 役割で子ノードを作成できる場合は True です。</span><span class="sxs-lookup"><span data-stu-id="40c7c-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="40c7c-126">7: 役割がチャットルーム (または、カテゴリの子チャットルーム) に参加できる場合は True。</span><span class="sxs-lookup"><span data-stu-id="40c7c-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="40c7c-127">8: 役割がチャットルーム (または、カテゴリの子チャットルーム) でチャットできる場合は True。</span><span class="sxs-lookup"><span data-stu-id="40c7c-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="40c7c-128">10: 役割がチャットルームに参加していないときでもチャット履歴を読むことができる場合は True。</span><span class="sxs-lookup"><span data-stu-id="40c7c-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="40c7c-129">11: 役割がチャットルームを表示できる場合は True です。</span><span class="sxs-lookup"><span data-stu-id="40c7c-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="40c7c-130">(これは、スコープや可視性などの要因によってさらに改良されています)。</span><span class="sxs-lookup"><span data-stu-id="40c7c-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="40c7c-131">12: この役割が聴衆チャットルームでチャットできる場合は True です。</span><span class="sxs-lookup"><span data-stu-id="40c7c-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="40c7c-132">13: ノードを表示したときに、役割が可視性規則を無視できる場合は True です。</span><span class="sxs-lookup"><span data-stu-id="40c7c-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="40c7c-133">**Key**</span><span class="sxs-lookup"><span data-stu-id="40c7c-133">**Key**</span></span>

|<span data-ttu-id="40c7c-134">**列**</span><span class="sxs-lookup"><span data-stu-id="40c7c-134">**Column**</span></span>|<span data-ttu-id="40c7c-135">**説明**</span><span class="sxs-lookup"><span data-stu-id="40c7c-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="40c7c-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="40c7c-136">rtypeID</span></span>  <br/> |<span data-ttu-id="40c7c-137">主キー。</span><span class="sxs-lookup"><span data-stu-id="40c7c-137">Primary key.</span></span>  <br/> |
   

