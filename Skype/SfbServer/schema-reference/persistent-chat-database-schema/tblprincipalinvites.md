---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites には、上のすべてのノードへの招待が自動的にプロビジョニングされたすべてのユーザーの招待状が含まれています。
ms.openlocfilehash: 5008158dcb1c62c766162595d9bffe1875d56514
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924424"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="20589-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="20589-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="20589-104">tblPrincipalInvites には、上のすべてのノードへの招待が自動的にプロビジョニングされたすべてのユーザーの招待状が含まれています。</span><span class="sxs-lookup"><span data-stu-id="20589-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="20589-105">**列**</span><span class="sxs-lookup"><span data-stu-id="20589-105">**Columns**</span></span>

|<span data-ttu-id="20589-106">**列**</span><span class="sxs-lookup"><span data-stu-id="20589-106">**Column**</span></span>|<span data-ttu-id="20589-107">**型**</span><span class="sxs-lookup"><span data-stu-id="20589-107">**Type**</span></span>|<span data-ttu-id="20589-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="20589-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="20589-109">prinID</span><span class="sxs-lookup"><span data-stu-id="20589-109">prinID</span></span>  <br/> |<span data-ttu-id="20589-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="20589-110">int, not null</span></span>  <br/> |<span data-ttu-id="20589-111">プリンシパルの id。</span><span class="sxs-lookup"><span data-stu-id="20589-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="20589-112">invID</span><span class="sxs-lookup"><span data-stu-id="20589-112">invID</span></span>  <br/> |<span data-ttu-id="20589-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="20589-113">int, not null</span></span>  <br/> |<span data-ttu-id="20589-114">一意な連番 (プリンシパルの ID) ごと tblLastInviteId テーブルから生成します。</span><span class="sxs-lookup"><span data-stu-id="20589-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="20589-115">ノード</span><span class="sxs-lookup"><span data-stu-id="20589-115">nodeID</span></span>  <br/> |<span data-ttu-id="20589-116">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="20589-116">int, not null</span></span>  <br/> |<span data-ttu-id="20589-117">ノード ID (チャット ルーム)。</span><span class="sxs-lookup"><span data-stu-id="20589-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="20589-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="20589-118">createdOn</span></span>  <br/> |<span data-ttu-id="20589-119">datetime では、null でないです。</span><span class="sxs-lookup"><span data-stu-id="20589-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="20589-120">作成の時間です。</span><span class="sxs-lookup"><span data-stu-id="20589-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="20589-121">**キー**</span><span class="sxs-lookup"><span data-stu-id="20589-121">**Keys**</span></span>

|<span data-ttu-id="20589-122">**列**</span><span class="sxs-lookup"><span data-stu-id="20589-122">**Column**</span></span>|<span data-ttu-id="20589-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="20589-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="20589-124">\<prinID、ノード\></span><span class="sxs-lookup"><span data-stu-id="20589-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="20589-125">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="20589-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="20589-126">prinID</span><span class="sxs-lookup"><span data-stu-id="20589-126">prinID</span></span>  <br/> |<span data-ttu-id="20589-127">TblPrincipal.prinID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="20589-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="20589-128">ノード</span><span class="sxs-lookup"><span data-stu-id="20589-128">nodeID</span></span>  <br/> |<span data-ttu-id="20589-129">TblNode.nodeID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="20589-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

