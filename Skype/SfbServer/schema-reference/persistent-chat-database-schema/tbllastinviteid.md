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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId には、各ユーザーに対して生成された (tblPrincipalInvites テーブルで使用された) 最後の招待 ID が含まれます。
ms.openlocfilehash: 17d1b725da034f79f8efc9ff9071c36430efde7d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814575"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="f8121-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="f8121-103">tblLastInviteId</span></span>
 
<span data-ttu-id="f8121-104">tblLastInviteId には、各ユーザーに対して生成された (tblPrincipalInvites テーブルで使用された) 最後の招待 ID が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f8121-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="f8121-105">**行**</span><span class="sxs-lookup"><span data-stu-id="f8121-105">**Columns**</span></span>

|<span data-ttu-id="f8121-106">**列**</span><span class="sxs-lookup"><span data-stu-id="f8121-106">**Column**</span></span>|<span data-ttu-id="f8121-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="f8121-107">**Type**</span></span>|<span data-ttu-id="f8121-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="f8121-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f8121-109">prinID</span><span class="sxs-lookup"><span data-stu-id="f8121-109">prinID</span></span>  <br/> |<span data-ttu-id="f8121-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="f8121-110">int, not null</span></span>  <br/> |<span data-ttu-id="f8121-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="f8121-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="f8121-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="f8121-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="f8121-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="f8121-113">int, not null</span></span>  <br/> |<span data-ttu-id="f8121-114">最後に使用した招待の ID。</span><span class="sxs-lookup"><span data-stu-id="f8121-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="f8121-115">**機能**</span><span class="sxs-lookup"><span data-stu-id="f8121-115">**Keys**</span></span>

|<span data-ttu-id="f8121-116">**列**</span><span class="sxs-lookup"><span data-stu-id="f8121-116">**Column**</span></span>|<span data-ttu-id="f8121-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="f8121-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f8121-118">prinID</span><span class="sxs-lookup"><span data-stu-id="f8121-118">prinID</span></span>  <br/> |<span data-ttu-id="f8121-119">主キー。</span><span class="sxs-lookup"><span data-stu-id="f8121-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f8121-120">prinID</span><span class="sxs-lookup"><span data-stu-id="f8121-120">prinID</span></span>  <br/> |<span data-ttu-id="f8121-121">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="f8121-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f8121-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8121-122">See also</span></span>

[<span data-ttu-id="f8121-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="f8121-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
