---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites には、自動招待が有効になっているすべてのノードのプロビジョニングされた全ユーザーの招待が含まれます。
ms.openlocfilehash: 5bbccd582442001bd2122dcbacdbe3634fcfd649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815857"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="1f2b8-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="1f2b8-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="1f2b8-104">tblPrincipalInvites には、自動招待が有効になっているすべてのノードのプロビジョニングされた全ユーザーの招待が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1f2b8-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="1f2b8-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="1f2b8-105">**Columns**</span></span>

|<span data-ttu-id="1f2b8-106">**列**</span><span class="sxs-lookup"><span data-stu-id="1f2b8-106">**Column**</span></span>|<span data-ttu-id="1f2b8-107">**型**</span><span class="sxs-lookup"><span data-stu-id="1f2b8-107">**Type**</span></span>|<span data-ttu-id="1f2b8-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="1f2b8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1f2b8-109">prinID</span><span class="sxs-lookup"><span data-stu-id="1f2b8-109">prinID</span></span>  <br/> |<span data-ttu-id="1f2b8-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="1f2b8-110">int, not null</span></span>  <br/> |<span data-ttu-id="1f2b8-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="1f2b8-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="1f2b8-112">invID</span><span class="sxs-lookup"><span data-stu-id="1f2b8-112">invID</span></span>  <br/> |<span data-ttu-id="1f2b8-113">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="1f2b8-113">int, not null</span></span>  <br/> |<span data-ttu-id="1f2b8-114">tblLastInviteId テーブルから生成された (プリンシパル ID ごとの) 一意のシーケンシャル番号。</span><span class="sxs-lookup"><span data-stu-id="1f2b8-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="1f2b8-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="1f2b8-115">nodeID</span></span>  <br/> |<span data-ttu-id="1f2b8-116">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="1f2b8-116">int, not null</span></span>  <br/> |<span data-ttu-id="1f2b8-117">ノード ID (チャット ルームのみ)。</span><span class="sxs-lookup"><span data-stu-id="1f2b8-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="1f2b8-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="1f2b8-118">createdOn</span></span>  <br/> |<span data-ttu-id="1f2b8-119">NULL でない datetime</span><span class="sxs-lookup"><span data-stu-id="1f2b8-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="1f2b8-120">作成の時刻。</span><span class="sxs-lookup"><span data-stu-id="1f2b8-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="1f2b8-121">**Keys**</span><span class="sxs-lookup"><span data-stu-id="1f2b8-121">**Keys**</span></span>

|<span data-ttu-id="1f2b8-122">**列**</span><span class="sxs-lookup"><span data-stu-id="1f2b8-122">**Column**</span></span>|<span data-ttu-id="1f2b8-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="1f2b8-123">**Description**</span></span>|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |<span data-ttu-id="1f2b8-124">主キー。</span><span class="sxs-lookup"><span data-stu-id="1f2b8-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="1f2b8-125">prinID</span><span class="sxs-lookup"><span data-stu-id="1f2b8-125">prinID</span></span>  <br/> |<span data-ttu-id="1f2b8-126">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="1f2b8-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="1f2b8-127">nodeID</span><span class="sxs-lookup"><span data-stu-id="1f2b8-127">nodeID</span></span>  <br/> |<span data-ttu-id="1f2b8-128">tblNode.nodeID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="1f2b8-128">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

