---
title: tblPrincipalInvites
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites には、上のすべてのノードへの招待が自動的にプロビジョニングされたすべてのユーザーの招待状が含まれています。
ms.openlocfilehash: ae33d45e14340b6374299343f13c8352db1a5021
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="9a6c3-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="9a6c3-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="9a6c3-104">tblPrincipalInvites には、上のすべてのノードへの招待が自動的にプロビジョニングされたすべてのユーザーの招待状が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="9a6c3-105">**列**</span><span class="sxs-lookup"><span data-stu-id="9a6c3-105">**Columns**</span></span>

|<span data-ttu-id="9a6c3-106">**列**</span><span class="sxs-lookup"><span data-stu-id="9a6c3-106">**Column**</span></span>|<span data-ttu-id="9a6c3-107">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="9a6c3-107">**Type**</span></span>|<span data-ttu-id="9a6c3-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="9a6c3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9a6c3-109">prinID</span><span class="sxs-lookup"><span data-stu-id="9a6c3-109">prinID</span></span>  <br/> |<span data-ttu-id="9a6c3-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-110">int, not null</span></span>  <br/> |<span data-ttu-id="9a6c3-111">プリンシパルの id。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="9a6c3-112">invID</span><span class="sxs-lookup"><span data-stu-id="9a6c3-112">invID</span></span>  <br/> |<span data-ttu-id="9a6c3-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-113">int, not null</span></span>  <br/> |<span data-ttu-id="9a6c3-114">一意な連番 (プリンシパルの ID) ごと tblLastInviteId テーブルから生成します。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="9a6c3-115">ノード</span><span class="sxs-lookup"><span data-stu-id="9a6c3-115">nodeID</span></span>  <br/> |<span data-ttu-id="9a6c3-116">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-116">int, not null</span></span>  <br/> |<span data-ttu-id="9a6c3-117">ノード ID (チャット ルーム)。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="9a6c3-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="9a6c3-118">createdOn</span></span>  <br/> |<span data-ttu-id="9a6c3-119">datetime では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="9a6c3-120">作成の時間です。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="9a6c3-121">**キー**</span><span class="sxs-lookup"><span data-stu-id="9a6c3-121">**Keys**</span></span>

|<span data-ttu-id="9a6c3-122">**列**</span><span class="sxs-lookup"><span data-stu-id="9a6c3-122">**Column**</span></span>|<span data-ttu-id="9a6c3-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="9a6c3-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9a6c3-124">\<prinID、ノード\></span><span class="sxs-lookup"><span data-stu-id="9a6c3-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="9a6c3-125">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="9a6c3-126">prinID</span><span class="sxs-lookup"><span data-stu-id="9a6c3-126">prinID</span></span>  <br/> |<span data-ttu-id="9a6c3-127">TblPrincipal.prinID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="9a6c3-128">ノード</span><span class="sxs-lookup"><span data-stu-id="9a6c3-128">nodeID</span></span>  <br/> |<span data-ttu-id="9a6c3-129">TblNode.nodeID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="9a6c3-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

