---
title: tblLastInviteId
ms.reviewer: ''
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
ms.openlocfilehash: 977911150992b2e90b7dc344af0550a25ad77221
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212559"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="5c84b-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="5c84b-103">tblLastInviteId</span></span>
 
<span data-ttu-id="5c84b-104">tblLastInviteId には、ユーザーごとに生成された (および tblPrincipalInvites テーブルで使用されている) 最後の招待 ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5c84b-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="5c84b-105">**列**</span><span class="sxs-lookup"><span data-stu-id="5c84b-105">**Columns**</span></span>

|<span data-ttu-id="5c84b-106">**列**</span><span class="sxs-lookup"><span data-stu-id="5c84b-106">**Column**</span></span>|<span data-ttu-id="5c84b-107">**型**</span><span class="sxs-lookup"><span data-stu-id="5c84b-107">**Type**</span></span>|<span data-ttu-id="5c84b-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="5c84b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5c84b-109">prinID</span><span class="sxs-lookup"><span data-stu-id="5c84b-109">prinID</span></span>  <br/> |<span data-ttu-id="5c84b-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="5c84b-110">int, not null</span></span>  <br/> |<span data-ttu-id="5c84b-111">プリンシパルの id。</span><span class="sxs-lookup"><span data-stu-id="5c84b-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="5c84b-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="5c84b-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="5c84b-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="5c84b-113">int, not null</span></span>  <br/> |<span data-ttu-id="5c84b-114">最後の使用への招待の id。</span><span class="sxs-lookup"><span data-stu-id="5c84b-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="5c84b-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="5c84b-115">**Keys**</span></span>

|<span data-ttu-id="5c84b-116">**列**</span><span class="sxs-lookup"><span data-stu-id="5c84b-116">**Column**</span></span>|<span data-ttu-id="5c84b-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="5c84b-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5c84b-118">prinID</span><span class="sxs-lookup"><span data-stu-id="5c84b-118">prinID</span></span>  <br/> |<span data-ttu-id="5c84b-119">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="5c84b-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="5c84b-120">prinID</span><span class="sxs-lookup"><span data-stu-id="5c84b-120">prinID</span></span>  <br/> |<span data-ttu-id="5c84b-121">TblPrincipal.prinID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="5c84b-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="5c84b-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c84b-122">See also</span></span>

[<span data-ttu-id="5c84b-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="5c84b-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
