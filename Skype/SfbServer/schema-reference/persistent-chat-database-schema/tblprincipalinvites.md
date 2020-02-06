---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites には、自動招待を含むすべてのノードのプロビジョニングされたすべてのユーザーの招待が含まれます。
ms.openlocfilehash: dfa41ec5715c7c5255b26fcdb32561e74c4f08df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814185"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="86abc-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="86abc-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="86abc-104">tblPrincipalInvites には、自動招待を含むすべてのノードのプロビジョニングされたすべてのユーザーの招待が含まれます。</span><span class="sxs-lookup"><span data-stu-id="86abc-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="86abc-105">**行**</span><span class="sxs-lookup"><span data-stu-id="86abc-105">**Columns**</span></span>

|<span data-ttu-id="86abc-106">**列**</span><span class="sxs-lookup"><span data-stu-id="86abc-106">**Column**</span></span>|<span data-ttu-id="86abc-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="86abc-107">**Type**</span></span>|<span data-ttu-id="86abc-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="86abc-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="86abc-109">prinID</span><span class="sxs-lookup"><span data-stu-id="86abc-109">prinID</span></span>  <br/> |<span data-ttu-id="86abc-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="86abc-110">int, not null</span></span>  <br/> |<span data-ttu-id="86abc-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="86abc-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="86abc-112">invID</span><span class="sxs-lookup"><span data-stu-id="86abc-112">invID</span></span>  <br/> |<span data-ttu-id="86abc-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="86abc-113">int, not null</span></span>  <br/> |<span data-ttu-id="86abc-114">TblLastInviteId テーブルから生成された一意の連続番号 (プリンシパル ID ごと)。</span><span class="sxs-lookup"><span data-stu-id="86abc-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="86abc-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="86abc-115">nodeID</span></span>  <br/> |<span data-ttu-id="86abc-116">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="86abc-116">int, not null</span></span>  <br/> |<span data-ttu-id="86abc-117">ノード ID (チャットルームのみ)。</span><span class="sxs-lookup"><span data-stu-id="86abc-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="86abc-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="86abc-118">createdOn</span></span>  <br/> |<span data-ttu-id="86abc-119">datetime。 null ではありません</span><span class="sxs-lookup"><span data-stu-id="86abc-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="86abc-120">作成時刻。</span><span class="sxs-lookup"><span data-stu-id="86abc-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="86abc-121">**機能**</span><span class="sxs-lookup"><span data-stu-id="86abc-121">**Keys**</span></span>

|<span data-ttu-id="86abc-122">**列**</span><span class="sxs-lookup"><span data-stu-id="86abc-122">**Column**</span></span>|<span data-ttu-id="86abc-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="86abc-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="86abc-124">\<prinID、nodeID\></span><span class="sxs-lookup"><span data-stu-id="86abc-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="86abc-125">主キー。</span><span class="sxs-lookup"><span data-stu-id="86abc-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="86abc-126">prinID</span><span class="sxs-lookup"><span data-stu-id="86abc-126">prinID</span></span>  <br/> |<span data-ttu-id="86abc-127">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="86abc-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="86abc-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="86abc-128">nodeID</span></span>  <br/> |<span data-ttu-id="86abc-129">TblNode テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="86abc-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

