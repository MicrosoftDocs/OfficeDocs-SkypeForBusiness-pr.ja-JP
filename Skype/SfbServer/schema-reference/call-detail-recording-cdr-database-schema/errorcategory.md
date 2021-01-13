---
title: Skype for Business Server 2015 の ErrorCategory テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory テーブルには、各 Skype for Business Server 2015 診断分類の表示名が含まれる。 既定では、Skype for Business Server 2015 は次の分類を使用します。
ms.openlocfilehash: ca3719f6d284cf715be1a87b1c7a5dc04ae84b04
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813147"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="a5a1b-104">Skype for Business Server 2015 の ErrorCategory テーブル</span><span class="sxs-lookup"><span data-stu-id="a5a1b-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a5a1b-105">ErrorCategory テーブルには、各 Skype for Business Server 2015 診断分類の表示名が含まれる。</span><span class="sxs-lookup"><span data-stu-id="a5a1b-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="a5a1b-106">既定では、Skype for Business Server 2015 は次の分類を使用します。</span><span class="sxs-lookup"><span data-stu-id="a5a1b-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="a5a1b-107">0 -- 成功</span><span class="sxs-lookup"><span data-stu-id="a5a1b-107">0 -- Success</span></span>
    
- <span data-ttu-id="a5a1b-108">1 -- 予期されるエラー</span><span class="sxs-lookup"><span data-stu-id="a5a1b-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="a5a1b-109">2 - 予期しないエラー</span><span class="sxs-lookup"><span data-stu-id="a5a1b-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="a5a1b-110">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a5a1b-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="a5a1b-111">**列**</span><span class="sxs-lookup"><span data-stu-id="a5a1b-111">**Column**</span></span>|<span data-ttu-id="a5a1b-112">**データ型**</span><span class="sxs-lookup"><span data-stu-id="a5a1b-112">**Data Type**</span></span>|<span data-ttu-id="a5a1b-113">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="a5a1b-113">**Key/Index**</span></span>|<span data-ttu-id="a5a1b-114">**詳細**</span><span class="sxs-lookup"><span data-stu-id="a5a1b-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a5a1b-115">**CategoryId**</span><span class="sxs-lookup"><span data-stu-id="a5a1b-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="a5a1b-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="a5a1b-116">tinyint</span></span>  <br/> |<span data-ttu-id="a5a1b-117">Primary</span><span class="sxs-lookup"><span data-stu-id="a5a1b-117">Primary</span></span>  <br/> |<span data-ttu-id="a5a1b-118">分類の一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="a5a1b-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="a5a1b-119">**名前**</span><span class="sxs-lookup"><span data-stu-id="a5a1b-119">**Name**</span></span> <br/> |<span data-ttu-id="a5a1b-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a5a1b-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="a5a1b-p103">分類に割り当てられる値とフレンドリ名。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a5a1b-p103">Value and friendly name assigned to the classification. Allowed values are:</span></span> <br/>  <span data-ttu-id="a5a1b-123">0 -- 成功</span><span class="sxs-lookup"><span data-stu-id="a5a1b-123">0 -- Success</span></span> <br/>  <span data-ttu-id="a5a1b-124">1 -- 予期されるエラー</span><span class="sxs-lookup"><span data-stu-id="a5a1b-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="a5a1b-125">2 - 予期しないエラー</span><span class="sxs-lookup"><span data-stu-id="a5a1b-125">2 - Unexpected failure</span></span> <br/> |
   

