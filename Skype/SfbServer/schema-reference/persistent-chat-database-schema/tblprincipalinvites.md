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
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites には、自動招待を含むすべてのノードのプロビジョニングされたすべてのユーザーの招待が含まれます。
ms.openlocfilehash: 21344cfc34ce046a1dffdf7cd3ee9557da20a7ef
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295294"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="84e03-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="84e03-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="84e03-104">tblPrincipalInvites には、自動招待を含むすべてのノードのプロビジョニングされたすべてのユーザーの招待が含まれます。</span><span class="sxs-lookup"><span data-stu-id="84e03-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="84e03-105">**行**</span><span class="sxs-lookup"><span data-stu-id="84e03-105">**Columns**</span></span>

|<span data-ttu-id="84e03-106">**列**</span><span class="sxs-lookup"><span data-stu-id="84e03-106">**Column**</span></span>|<span data-ttu-id="84e03-107">**型**</span><span class="sxs-lookup"><span data-stu-id="84e03-107">**Type**</span></span>|<span data-ttu-id="84e03-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="84e03-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="84e03-109">prinID</span><span class="sxs-lookup"><span data-stu-id="84e03-109">prinID</span></span>  <br/> |<span data-ttu-id="84e03-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="84e03-110">int, not null</span></span>  <br/> |<span data-ttu-id="84e03-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="84e03-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="84e03-112">invID</span><span class="sxs-lookup"><span data-stu-id="84e03-112">invID</span></span>  <br/> |<span data-ttu-id="84e03-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="84e03-113">int, not null</span></span>  <br/> |<span data-ttu-id="84e03-114">TblLastInviteId テーブルから生成された一意の連続番号 (プリンシパル ID ごと)。</span><span class="sxs-lookup"><span data-stu-id="84e03-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="84e03-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="84e03-115">nodeID</span></span>  <br/> |<span data-ttu-id="84e03-116">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="84e03-116">int, not null</span></span>  <br/> |<span data-ttu-id="84e03-117">ノード ID (チャットルームのみ)。</span><span class="sxs-lookup"><span data-stu-id="84e03-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="84e03-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="84e03-118">createdOn</span></span>  <br/> |<span data-ttu-id="84e03-119">datetime。 null ではありません</span><span class="sxs-lookup"><span data-stu-id="84e03-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="84e03-120">作成時刻。</span><span class="sxs-lookup"><span data-stu-id="84e03-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="84e03-121">**機能**</span><span class="sxs-lookup"><span data-stu-id="84e03-121">**Keys**</span></span>

|<span data-ttu-id="84e03-122">**列**</span><span class="sxs-lookup"><span data-stu-id="84e03-122">**Column**</span></span>|<span data-ttu-id="84e03-123">**説明**</span><span class="sxs-lookup"><span data-stu-id="84e03-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="84e03-124">\<prinID、nodeID\></span><span class="sxs-lookup"><span data-stu-id="84e03-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="84e03-125">主キー。</span><span class="sxs-lookup"><span data-stu-id="84e03-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="84e03-126">prinID</span><span class="sxs-lookup"><span data-stu-id="84e03-126">prinID</span></span>  <br/> |<span data-ttu-id="84e03-127">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="84e03-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="84e03-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="84e03-128">nodeID</span></span>  <br/> |<span data-ttu-id="84e03-129">TblNode テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="84e03-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

