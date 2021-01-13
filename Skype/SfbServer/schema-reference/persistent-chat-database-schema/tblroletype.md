---
title: tblRoleType
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
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType は静的な検索テーブルであり、役割の種類とそれに関連付けられたアクセス許可のセットが格納されています。
ms.openlocfilehash: c440463d822b908a89c84eb9c85b70e9daf442be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831527"
---
# <a name="tblroletype"></a><span data-ttu-id="d9b84-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="d9b84-103">tblRoleType</span></span>
 
<span data-ttu-id="d9b84-104">tblRoleType は静的な検索テーブルであり、役割の種類とそれに関連付けられたアクセス許可のセットが格納されています。</span><span class="sxs-lookup"><span data-stu-id="d9b84-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="d9b84-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="d9b84-105">**Columns**</span></span>

|<span data-ttu-id="d9b84-106">**列**</span><span class="sxs-lookup"><span data-stu-id="d9b84-106">**Column**</span></span>|<span data-ttu-id="d9b84-107">**型**</span><span class="sxs-lookup"><span data-stu-id="d9b84-107">**Type**</span></span>|<span data-ttu-id="d9b84-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="d9b84-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d9b84-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="d9b84-109">rtypeID</span></span>  <br/> |<span data-ttu-id="d9b84-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="d9b84-110">int, not null</span></span>  <br/> |<span data-ttu-id="d9b84-111">役割の種類の ID。</span><span class="sxs-lookup"><span data-stu-id="d9b84-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="d9b84-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="d9b84-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="d9b84-113">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d9b84-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="d9b84-p101">役割の種類の説明。使用できる役割は次の 4 つです。</span><span class="sxs-lookup"><span data-stu-id="d9b84-p101">Role type description. There are four available roles:</span></span> <br/>  <span data-ttu-id="d9b84-116">メンバー: チャット ルームのメンバー</span><span class="sxs-lookup"><span data-stu-id="d9b84-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="d9b84-117">マネージャー: チャット ルームのマネージャー</span><span class="sxs-lookup"><span data-stu-id="d9b84-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="d9b84-118">承認されたメンバー: 大会議室のチャット ルームの発表者</span><span class="sxs-lookup"><span data-stu-id="d9b84-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="d9b84-119">作成者: チャット ルームの作成者</span><span class="sxs-lookup"><span data-stu-id="d9b84-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="d9b84-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="d9b84-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="d9b84-121">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="d9b84-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="d9b84-p102">役割のアクセス許可セット。使用されるビットは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d9b84-p102">Permission set for the role. The used bits are:</span></span> <br/>  <span data-ttu-id="d9b84-124">2: 役割がノードを管理できる場合は True。</span><span class="sxs-lookup"><span data-stu-id="d9b84-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="d9b84-125">4: 役割が子ノードを作成できる場合は True。</span><span class="sxs-lookup"><span data-stu-id="d9b84-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="d9b84-126">7: 役割がチャット ルーム (またはカテゴリの子チャット ルーム) に参加できる場合は True。</span><span class="sxs-lookup"><span data-stu-id="d9b84-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="d9b84-127">8: 役割がチャット ルーム (またはカテゴリの子チャット ルーム) でチャットできる場合は True。</span><span class="sxs-lookup"><span data-stu-id="d9b84-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="d9b84-128">10: 役割がチャット ルームに参加していなくてもチャットの履歴を読むことができる場合は True。</span><span class="sxs-lookup"><span data-stu-id="d9b84-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="d9b84-p103">11: 役割がチャット ルームを見ることができる場合は True (これはスコープや可視性などの要素によってさらに微調整されます)。</span><span class="sxs-lookup"><span data-stu-id="d9b84-p103">11: True if the role can see the chat room. (This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="d9b84-131">12: 役割が大会議室のチャット ルームでチャットできる場合は True。</span><span class="sxs-lookup"><span data-stu-id="d9b84-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="d9b84-132">13: 役割がノードを表示するときに可視性ルールをバイパスできる場合は True。</span><span class="sxs-lookup"><span data-stu-id="d9b84-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="d9b84-133">**キー**</span><span class="sxs-lookup"><span data-stu-id="d9b84-133">**Key**</span></span>

|<span data-ttu-id="d9b84-134">**列**</span><span class="sxs-lookup"><span data-stu-id="d9b84-134">**Column**</span></span>|<span data-ttu-id="d9b84-135">**説明**</span><span class="sxs-lookup"><span data-stu-id="d9b84-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d9b84-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="d9b84-136">rtypeID</span></span>  <br/> |<span data-ttu-id="d9b84-137">主キー。</span><span class="sxs-lookup"><span data-stu-id="d9b84-137">Primary key.</span></span>  <br/> |
   

