---
title: tblLastInviteId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId には、ユーザーごとに生成された (および tblPrincipalInvites テーブルで使用されている) 最後の招待 ID が含まれています。
ms.openlocfilehash: f57ca67a91b71b9245644a53eb3e5c5771ca6fb0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929904"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="58ae1-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="58ae1-103">tblLastInviteId</span></span>
 
<span data-ttu-id="58ae1-104">tblLastInviteId には、ユーザーごとに生成された (および tblPrincipalInvites テーブルで使用されている) 最後の招待 ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="58ae1-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="58ae1-105">**列**</span><span class="sxs-lookup"><span data-stu-id="58ae1-105">**Columns**</span></span>

|<span data-ttu-id="58ae1-106">**列**</span><span class="sxs-lookup"><span data-stu-id="58ae1-106">**Column**</span></span>|<span data-ttu-id="58ae1-107">**型**</span><span class="sxs-lookup"><span data-stu-id="58ae1-107">**Type**</span></span>|<span data-ttu-id="58ae1-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="58ae1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="58ae1-109">prinID</span><span class="sxs-lookup"><span data-stu-id="58ae1-109">prinID</span></span>  <br/> |<span data-ttu-id="58ae1-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="58ae1-110">int, not null</span></span>  <br/> |<span data-ttu-id="58ae1-111">プリンシパルの id。</span><span class="sxs-lookup"><span data-stu-id="58ae1-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="58ae1-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="58ae1-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="58ae1-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="58ae1-113">int, not null</span></span>  <br/> |<span data-ttu-id="58ae1-114">最後の使用への招待の id。</span><span class="sxs-lookup"><span data-stu-id="58ae1-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="58ae1-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="58ae1-115">**Keys**</span></span>

|<span data-ttu-id="58ae1-116">**列**</span><span class="sxs-lookup"><span data-stu-id="58ae1-116">**Column**</span></span>|<span data-ttu-id="58ae1-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="58ae1-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="58ae1-118">prinID</span><span class="sxs-lookup"><span data-stu-id="58ae1-118">prinID</span></span>  <br/> |<span data-ttu-id="58ae1-119">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="58ae1-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="58ae1-120">prinID</span><span class="sxs-lookup"><span data-stu-id="58ae1-120">prinID</span></span>  <br/> |<span data-ttu-id="58ae1-121">TblPrincipal.prinID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="58ae1-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="58ae1-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="58ae1-122">See also</span></span>

[<span data-ttu-id="58ae1-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="58ae1-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
