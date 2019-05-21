---
title: tblLastInviteId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId には、各ユーザーに対して生成された (tblPrincipalInvites テーブルで使用された) 最後の招待 ID が含まれます。
ms.openlocfilehash: f36b0824bb8e9dbf2cb0aa14575cc1649bde708a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295357"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="677a0-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="677a0-103">tblLastInviteId</span></span>
 
<span data-ttu-id="677a0-104">tblLastInviteId には、各ユーザーに対して生成された (tblPrincipalInvites テーブルで使用された) 最後の招待 ID が含まれます。</span><span class="sxs-lookup"><span data-stu-id="677a0-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="677a0-105">**行**</span><span class="sxs-lookup"><span data-stu-id="677a0-105">**Columns**</span></span>

|<span data-ttu-id="677a0-106">**列**</span><span class="sxs-lookup"><span data-stu-id="677a0-106">**Column**</span></span>|<span data-ttu-id="677a0-107">**型**</span><span class="sxs-lookup"><span data-stu-id="677a0-107">**Type**</span></span>|<span data-ttu-id="677a0-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="677a0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="677a0-109">prinID</span><span class="sxs-lookup"><span data-stu-id="677a0-109">prinID</span></span>  <br/> |<span data-ttu-id="677a0-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="677a0-110">int, not null</span></span>  <br/> |<span data-ttu-id="677a0-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="677a0-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="677a0-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="677a0-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="677a0-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="677a0-113">int, not null</span></span>  <br/> |<span data-ttu-id="677a0-114">最後に使用した招待の ID。</span><span class="sxs-lookup"><span data-stu-id="677a0-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="677a0-115">**機能**</span><span class="sxs-lookup"><span data-stu-id="677a0-115">**Keys**</span></span>

|<span data-ttu-id="677a0-116">**列**</span><span class="sxs-lookup"><span data-stu-id="677a0-116">**Column**</span></span>|<span data-ttu-id="677a0-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="677a0-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="677a0-118">prinID</span><span class="sxs-lookup"><span data-stu-id="677a0-118">prinID</span></span>  <br/> |<span data-ttu-id="677a0-119">主キー。</span><span class="sxs-lookup"><span data-stu-id="677a0-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="677a0-120">prinID</span><span class="sxs-lookup"><span data-stu-id="677a0-120">prinID</span></span>  <br/> |<span data-ttu-id="677a0-121">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="677a0-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="677a0-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="677a0-122">See also</span></span>

[<span data-ttu-id="677a0-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="677a0-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
