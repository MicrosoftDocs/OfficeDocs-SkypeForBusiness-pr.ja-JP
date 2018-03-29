---
title: tblLastInviteId
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId には、ユーザーごとに生成された (および tblPrincipalInvites テーブルで使用されている) 最後の招待 ID が含まれています。
ms.openlocfilehash: 55eb9d9f5edbb3cc0e8c786b650e51cdc1e3d141
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastinviteid"></a><span data-ttu-id="ee0d1-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="ee0d1-103">tblLastInviteId</span></span>
 
<span data-ttu-id="ee0d1-104">tblLastInviteId には、ユーザーごとに生成された (および tblPrincipalInvites テーブルで使用されている) 最後の招待 ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ee0d1-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="ee0d1-105">**列**</span><span class="sxs-lookup"><span data-stu-id="ee0d1-105">**Columns**</span></span>

|<span data-ttu-id="ee0d1-106">**列**</span><span class="sxs-lookup"><span data-stu-id="ee0d1-106">**Column**</span></span>|<span data-ttu-id="ee0d1-107">**タイプ**</span><span class="sxs-lookup"><span data-stu-id="ee0d1-107">**Type**</span></span>|<span data-ttu-id="ee0d1-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="ee0d1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ee0d1-109">prinID</span><span class="sxs-lookup"><span data-stu-id="ee0d1-109">prinID</span></span>  <br/> |<span data-ttu-id="ee0d1-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="ee0d1-110">int, not null</span></span>  <br/> |<span data-ttu-id="ee0d1-111">プリンシパルの id。</span><span class="sxs-lookup"><span data-stu-id="ee0d1-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="ee0d1-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="ee0d1-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="ee0d1-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="ee0d1-113">int, not null</span></span>  <br/> |<span data-ttu-id="ee0d1-114">最後の使用への招待の id。</span><span class="sxs-lookup"><span data-stu-id="ee0d1-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="ee0d1-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="ee0d1-115">**Keys**</span></span>

|<span data-ttu-id="ee0d1-116">**列**</span><span class="sxs-lookup"><span data-stu-id="ee0d1-116">**Column**</span></span>|<span data-ttu-id="ee0d1-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="ee0d1-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ee0d1-118">prinID</span><span class="sxs-lookup"><span data-stu-id="ee0d1-118">prinID</span></span>  <br/> |<span data-ttu-id="ee0d1-119">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="ee0d1-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="ee0d1-120">prinID</span><span class="sxs-lookup"><span data-stu-id="ee0d1-120">prinID</span></span>  <br/> |<span data-ttu-id="ee0d1-121">TblPrincipal.prinID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="ee0d1-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ee0d1-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee0d1-122">See also</span></span>

#### 

[<span data-ttu-id="ee0d1-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="ee0d1-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)

