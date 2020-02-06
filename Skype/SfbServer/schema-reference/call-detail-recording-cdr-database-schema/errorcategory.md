---
title: Skype for Business Server 2015 の ErrorCategory テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory テーブルには、各 Skype for Business Server 2015 診断分類のフレンドリ名が含まれています。 既定では、Skype for Business Server 2015 には次のような分類が使用されます。
ms.openlocfilehash: f3ad3f86a382b900d53c5e86140a46d7f32ca1c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815255"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="bd670-104">Skype for Business Server 2015 の ErrorCategory テーブル</span><span class="sxs-lookup"><span data-stu-id="bd670-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bd670-105">ErrorCategory テーブルには、各 Skype for Business Server 2015 診断分類のフレンドリ名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bd670-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="bd670-106">既定では、Skype for Business Server 2015 には次のような分類が使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd670-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="bd670-107">0--成功</span><span class="sxs-lookup"><span data-stu-id="bd670-107">0 -- Success</span></span>
    
- <span data-ttu-id="bd670-108">1--予期しないエラー</span><span class="sxs-lookup"><span data-stu-id="bd670-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="bd670-109">2-予期しないエラーが発生した</span><span class="sxs-lookup"><span data-stu-id="bd670-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="bd670-110">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="bd670-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="bd670-111">**列**</span><span class="sxs-lookup"><span data-stu-id="bd670-111">**Column**</span></span>|<span data-ttu-id="bd670-112">**データ型**</span><span class="sxs-lookup"><span data-stu-id="bd670-112">**Data Type**</span></span>|<span data-ttu-id="bd670-113">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="bd670-113">**Key/Index**</span></span>|<span data-ttu-id="bd670-114">**詳細**</span><span class="sxs-lookup"><span data-stu-id="bd670-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bd670-115">**区分**</span><span class="sxs-lookup"><span data-stu-id="bd670-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="bd670-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="bd670-116">tinyint</span></span>  <br/> |<span data-ttu-id="bd670-117">Primary</span><span class="sxs-lookup"><span data-stu-id="bd670-117">Primary</span></span>  <br/> |<span data-ttu-id="bd670-118">分類の一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="bd670-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="bd670-119">**名前**</span><span class="sxs-lookup"><span data-stu-id="bd670-119">**Name**</span></span> <br/> |<span data-ttu-id="bd670-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bd670-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="bd670-121">分類に割り当てられている値とフレンドリ名。</span><span class="sxs-lookup"><span data-stu-id="bd670-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="bd670-122">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bd670-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="bd670-123">0--成功</span><span class="sxs-lookup"><span data-stu-id="bd670-123">0 -- Success</span></span> <br/>  <span data-ttu-id="bd670-124">1--予期しないエラー</span><span class="sxs-lookup"><span data-stu-id="bd670-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="bd670-125">2-予期しないエラーが発生した</span><span class="sxs-lookup"><span data-stu-id="bd670-125">2 - Unexpected failure</span></span> <br/> |
   

