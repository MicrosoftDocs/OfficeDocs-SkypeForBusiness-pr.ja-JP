---
title: ビジネス サーバー 2015 の Skype での ErrorCategory テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory テーブルには、ビジネス サーバー 2015 診断分類の各 Skype のフレンドリ名が含まれています。 ビジネス サーバー 2015 の Skype は、既定では、次の分類を使用します。
ms.openlocfilehash: 23df7ecb7e10dc104e6274edb762369ad539f8fe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="81970-104">ビジネス サーバー 2015 の Skype での ErrorCategory テーブル</span><span class="sxs-lookup"><span data-stu-id="81970-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="81970-105">ErrorCategory テーブルには、ビジネス サーバー 2015 診断分類の各 Skype のフレンドリ名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="81970-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="81970-106">ビジネス サーバー 2015 の Skype は、既定では、次の分類を使用します。</span><span class="sxs-lookup"><span data-stu-id="81970-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="81970-107">0 - 成功</span><span class="sxs-lookup"><span data-stu-id="81970-107">0 -- Success</span></span>
    
- <span data-ttu-id="81970-108">1-予想される障害</span><span class="sxs-lookup"><span data-stu-id="81970-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="81970-109">2-予期しないエラー</span><span class="sxs-lookup"><span data-stu-id="81970-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="81970-110">このテーブルは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="81970-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="81970-111">**列**</span><span class="sxs-lookup"><span data-stu-id="81970-111">**Column**</span></span>|<span data-ttu-id="81970-112">**データ型**</span><span class="sxs-lookup"><span data-stu-id="81970-112">**Data Type**</span></span>|<span data-ttu-id="81970-113">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="81970-113">**Key/Index**</span></span>|<span data-ttu-id="81970-114">**詳細**</span><span class="sxs-lookup"><span data-stu-id="81970-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="81970-115">**[区分コード]**</span><span class="sxs-lookup"><span data-stu-id="81970-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="81970-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="81970-116">tinyint</span></span>  <br/> |<span data-ttu-id="81970-117">Primary</span><span class="sxs-lookup"><span data-stu-id="81970-117">Primary</span></span>  <br/> |<span data-ttu-id="81970-118">分類の一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="81970-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="81970-119">**名**</span><span class="sxs-lookup"><span data-stu-id="81970-119">**Name**</span></span> <br/> |<span data-ttu-id="81970-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="81970-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="81970-121">値および分類に割り当てられたフレンドリ名です。</span><span class="sxs-lookup"><span data-stu-id="81970-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="81970-122">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="81970-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="81970-123">0 - 成功</span><span class="sxs-lookup"><span data-stu-id="81970-123">0 -- Success</span></span> <br/>  <span data-ttu-id="81970-124">1-予想される障害</span><span class="sxs-lookup"><span data-stu-id="81970-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="81970-125">2-予期しないエラー</span><span class="sxs-lookup"><span data-stu-id="81970-125">2 - Unexpected failure</span></span> <br/> |
   

