---
title: ビジネス サーバー 2015 の Skype での ErrorCategory テーブル
ms.reviewer: ''
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
ms.openlocfilehash: 70322d30b516d003fcac015a4eda7382a13cd2be
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886960"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e6465-104">ビジネス サーバー 2015 の Skype での ErrorCategory テーブル</span><span class="sxs-lookup"><span data-stu-id="e6465-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e6465-105">ErrorCategory テーブルには、ビジネス サーバー 2015 診断分類の各 Skype のフレンドリ名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e6465-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="e6465-106">ビジネス サーバー 2015 の Skype は、既定では、次の分類を使用します。</span><span class="sxs-lookup"><span data-stu-id="e6465-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="e6465-107">0 - 成功</span><span class="sxs-lookup"><span data-stu-id="e6465-107">0 -- Success</span></span>
    
- <span data-ttu-id="e6465-108">1-予想される障害</span><span class="sxs-lookup"><span data-stu-id="e6465-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="e6465-109">2-予期しないエラー</span><span class="sxs-lookup"><span data-stu-id="e6465-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="e6465-110">このテーブルは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e6465-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="e6465-111">**列**</span><span class="sxs-lookup"><span data-stu-id="e6465-111">**Column**</span></span>|<span data-ttu-id="e6465-112">**データ型**</span><span class="sxs-lookup"><span data-stu-id="e6465-112">**Data Type**</span></span>|<span data-ttu-id="e6465-113">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="e6465-113">**Key/Index**</span></span>|<span data-ttu-id="e6465-114">**詳細**</span><span class="sxs-lookup"><span data-stu-id="e6465-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e6465-115">**[区分コード]**</span><span class="sxs-lookup"><span data-stu-id="e6465-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="e6465-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="e6465-116">tinyint</span></span>  <br/> |<span data-ttu-id="e6465-117">Primary</span><span class="sxs-lookup"><span data-stu-id="e6465-117">Primary</span></span>  <br/> |<span data-ttu-id="e6465-118">分類の一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="e6465-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="e6465-119">**名前**</span><span class="sxs-lookup"><span data-stu-id="e6465-119">**Name**</span></span> <br/> |<span data-ttu-id="e6465-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e6465-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="e6465-121">値および分類に割り当てられたフレンドリ名です。</span><span class="sxs-lookup"><span data-stu-id="e6465-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="e6465-122">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e6465-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="e6465-123">0 - 成功</span><span class="sxs-lookup"><span data-stu-id="e6465-123">0 -- Success</span></span> <br/>  <span data-ttu-id="e6465-124">1-予想される障害</span><span class="sxs-lookup"><span data-stu-id="e6465-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="e6465-125">2-予期しないエラー</span><span class="sxs-lookup"><span data-stu-id="e6465-125">2 - Unexpected failure</span></span> <br/> |
   

