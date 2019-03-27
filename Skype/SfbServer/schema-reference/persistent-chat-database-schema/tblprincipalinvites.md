---
title: tblPrincipalInvites
ms.reviewer: ''
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
ms.openlocfilehash: fbf61265f4970b57ffa95a52c8bafa395fb3a331
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876691"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="7648d-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="7648d-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="7648d-104">tblPrincipalInvites には、上のすべてのノードへの招待が自動的にプロビジョニングされたすべてのユーザーの招待状が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7648d-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="7648d-105">**列**</span><span class="sxs-lookup"><span data-stu-id="7648d-105">**Columns**</span></span>

|<span data-ttu-id="7648d-106">**列**</span><span class="sxs-lookup"><span data-stu-id="7648d-106">**Column**</span></span>|<span data-ttu-id="7648d-107">**型**</span><span class="sxs-lookup"><span data-stu-id="7648d-107">**Type**</span></span>|<span data-ttu-id="7648d-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="7648d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7648d-109">prinID</span><span class="sxs-lookup"><span data-stu-id="7648d-109">prinID</span></span>  <br/> |<span data-ttu-id="7648d-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="7648d-110">int, not null</span></span>  <br/> |<span data-ttu-id="7648d-111">プリンシパルの id。</span><span class="sxs-lookup"><span data-stu-id="7648d-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="7648d-112">invID</span><span class="sxs-lookup"><span data-stu-id="7648d-112">invID</span></span>  <br/> |<span data-ttu-id="7648d-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="7648d-113">int, not null</span></span>  <br/> |<span data-ttu-id="7648d-114">一意な連番 (プリンシパルの ID) ごと tblLastInviteId テーブルから生成します。</span><span class="sxs-lookup"><span data-stu-id="7648d-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="7648d-115">ノード</span><span class="sxs-lookup"><span data-stu-id="7648d-115">nodeID</span></span>  <br/> |<span data-ttu-id="7648d-116">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="7648d-116">int, not null</span></span>  <br/> |<span data-ttu-id="7648d-117">ノード ID (チャット ルーム)。</span><span class="sxs-lookup"><span data-stu-id="7648d-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="7648d-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="7648d-118">createdOn</span></span>  <br/> |<span data-ttu-id="7648d-119">datetime では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="7648d-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="7648d-120">作成の時間です。</span><span class="sxs-lookup"><span data-stu-id="7648d-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="7648d-121">**キー**</span><span class="sxs-lookup"><span data-stu-id="7648d-121">**Keys**</span></span>

|<span data-ttu-id="7648d-122">**列**</span><span class="sxs-lookup"><span data-stu-id="7648d-122">**Column**</span></span>|<span data-ttu-id="7648d-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="7648d-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7648d-124">\<prinID、ノード\></span><span class="sxs-lookup"><span data-stu-id="7648d-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="7648d-125">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="7648d-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="7648d-126">prinID</span><span class="sxs-lookup"><span data-stu-id="7648d-126">prinID</span></span>  <br/> |<span data-ttu-id="7648d-127">TblPrincipal.prinID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="7648d-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="7648d-128">ノード</span><span class="sxs-lookup"><span data-stu-id="7648d-128">nodeID</span></span>  <br/> |<span data-ttu-id="7648d-129">TblNode.nodeID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="7648d-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

