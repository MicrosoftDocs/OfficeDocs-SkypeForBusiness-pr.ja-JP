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
ms.openlocfilehash: 5f94714bfe42d6777907f3ce3e467e4add7a00d8
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2018
ms.locfileid: "19504853"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="40ef3-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="40ef3-103">tblLastInviteId</span></span>
 
<span data-ttu-id="40ef3-104">tblLastInviteId には、ユーザーごとに生成された (および tblPrincipalInvites テーブルで使用されている) 最後の招待 ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="40ef3-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="40ef3-105">**列**</span><span class="sxs-lookup"><span data-stu-id="40ef3-105">**Columns**</span></span>

|<span data-ttu-id="40ef3-106">**列**</span><span class="sxs-lookup"><span data-stu-id="40ef3-106">**Column**</span></span>|<span data-ttu-id="40ef3-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="40ef3-107">**Type**</span></span>|<span data-ttu-id="40ef3-108">**説明**</span><span class="sxs-lookup"><span data-stu-id="40ef3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="40ef3-109">prinID</span><span class="sxs-lookup"><span data-stu-id="40ef3-109">prinID</span></span>  <br/> |<span data-ttu-id="40ef3-110">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="40ef3-110">int, not null</span></span>  <br/> |<span data-ttu-id="40ef3-111">プリンシパルの id。</span><span class="sxs-lookup"><span data-stu-id="40ef3-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="40ef3-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="40ef3-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="40ef3-113">int 型、null でないです。</span><span class="sxs-lookup"><span data-stu-id="40ef3-113">int, not null</span></span>  <br/> |<span data-ttu-id="40ef3-114">最後の使用への招待の id。</span><span class="sxs-lookup"><span data-stu-id="40ef3-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="40ef3-115">**キー**</span><span class="sxs-lookup"><span data-stu-id="40ef3-115">**Keys**</span></span>

|<span data-ttu-id="40ef3-116">**列**</span><span class="sxs-lookup"><span data-stu-id="40ef3-116">**Column**</span></span>|<span data-ttu-id="40ef3-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="40ef3-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="40ef3-118">prinID</span><span class="sxs-lookup"><span data-stu-id="40ef3-118">prinID</span></span>  <br/> |<span data-ttu-id="40ef3-119">プライマリ ・ キーです。</span><span class="sxs-lookup"><span data-stu-id="40ef3-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="40ef3-120">prinID</span><span class="sxs-lookup"><span data-stu-id="40ef3-120">prinID</span></span>  <br/> |<span data-ttu-id="40ef3-121">TblPrincipal.prinID テーブル内の参照と外部キーです。</span><span class="sxs-lookup"><span data-stu-id="40ef3-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="40ef3-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="40ef3-122">See also</span></span>

[<span data-ttu-id="40ef3-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="40ef3-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)