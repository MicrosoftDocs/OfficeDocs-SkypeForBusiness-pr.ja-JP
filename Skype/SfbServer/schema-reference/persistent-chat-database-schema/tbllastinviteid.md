---
title: tblLastInviteId
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
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId には、各ユーザーに対して生成された (そして tblPrincipalInvites テーブルで使用された) 最後の招待 ID が格納されます。
ms.openlocfilehash: 9d5ec67a4f5c3db8558c58834582d489fde00ab6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815967"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="605ff-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="605ff-103">tblLastInviteId</span></span>
 
<span data-ttu-id="605ff-104">tblLastInviteId には、各ユーザーに対して生成された (そして tblPrincipalInvites テーブルで使用された) 最後の招待 ID が格納されます。</span><span class="sxs-lookup"><span data-stu-id="605ff-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="605ff-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="605ff-105">**Columns**</span></span>

|<span data-ttu-id="605ff-106">**列**</span><span class="sxs-lookup"><span data-stu-id="605ff-106">**Column**</span></span>|<span data-ttu-id="605ff-107">**型**</span><span class="sxs-lookup"><span data-stu-id="605ff-107">**Type**</span></span>|<span data-ttu-id="605ff-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="605ff-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="605ff-109">prinID</span><span class="sxs-lookup"><span data-stu-id="605ff-109">prinID</span></span>  <br/> |<span data-ttu-id="605ff-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="605ff-110">int, not null</span></span>  <br/> |<span data-ttu-id="605ff-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="605ff-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="605ff-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="605ff-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="605ff-113">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="605ff-113">int, not null</span></span>  <br/> |<span data-ttu-id="605ff-114">最後に使用された招待 ID。</span><span class="sxs-lookup"><span data-stu-id="605ff-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="605ff-115">**Keys**</span><span class="sxs-lookup"><span data-stu-id="605ff-115">**Keys**</span></span>

|<span data-ttu-id="605ff-116">**列**</span><span class="sxs-lookup"><span data-stu-id="605ff-116">**Column**</span></span>|<span data-ttu-id="605ff-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="605ff-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="605ff-118">prinID</span><span class="sxs-lookup"><span data-stu-id="605ff-118">prinID</span></span>  <br/> |<span data-ttu-id="605ff-119">主キー。</span><span class="sxs-lookup"><span data-stu-id="605ff-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="605ff-120">prinID</span><span class="sxs-lookup"><span data-stu-id="605ff-120">prinID</span></span>  <br/> |<span data-ttu-id="605ff-121">tblPrincipal.prinID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="605ff-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="605ff-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="605ff-122">See also</span></span>

[<span data-ttu-id="605ff-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="605ff-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
