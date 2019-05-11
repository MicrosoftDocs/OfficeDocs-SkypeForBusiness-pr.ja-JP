---
title: ビジネス サーバー 2015 の Skype での ErrorCategory テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory テーブルには、ビジネス サーバー 2015 診断分類の各 Skype のフレンドリ名が含まれています。 ビジネス サーバー 2015 の Skype は、既定では、次の分類を使用します。
ms.openlocfilehash: b6226396302353b815138b41b7c19f170a0d6b4d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901088"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="a3409-104">ビジネス サーバー 2015 の Skype での ErrorCategory テーブル</span><span class="sxs-lookup"><span data-stu-id="a3409-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a3409-105">ErrorCategory テーブルには、ビジネス サーバー 2015 診断分類の各 Skype のフレンドリ名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a3409-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="a3409-106">ビジネス サーバー 2015 の Skype は、既定では、次の分類を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3409-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="a3409-107">0 - 成功</span><span class="sxs-lookup"><span data-stu-id="a3409-107">0 -- Success</span></span>
    
- <span data-ttu-id="a3409-108">1-予想される障害</span><span class="sxs-lookup"><span data-stu-id="a3409-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="a3409-109">2-予期しないエラー</span><span class="sxs-lookup"><span data-stu-id="a3409-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="a3409-110">このテーブルは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a3409-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="a3409-111">**列**</span><span class="sxs-lookup"><span data-stu-id="a3409-111">**Column**</span></span>|<span data-ttu-id="a3409-112">**データ型**</span><span class="sxs-lookup"><span data-stu-id="a3409-112">**Data Type**</span></span>|<span data-ttu-id="a3409-113">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="a3409-113">**Key/Index**</span></span>|<span data-ttu-id="a3409-114">**詳細**</span><span class="sxs-lookup"><span data-stu-id="a3409-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a3409-115">**[区分コード]**</span><span class="sxs-lookup"><span data-stu-id="a3409-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="a3409-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="a3409-116">tinyint</span></span>  <br/> |<span data-ttu-id="a3409-117">Primary</span><span class="sxs-lookup"><span data-stu-id="a3409-117">Primary</span></span>  <br/> |<span data-ttu-id="a3409-118">分類の一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="a3409-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="a3409-119">**名前**</span><span class="sxs-lookup"><span data-stu-id="a3409-119">**Name**</span></span> <br/> |<span data-ttu-id="a3409-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a3409-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="a3409-121">値および分類に割り当てられたフレンドリ名です。</span><span class="sxs-lookup"><span data-stu-id="a3409-121">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="a3409-122">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a3409-122">Allowed values are:</span></span> <br/>  <span data-ttu-id="a3409-123">0 - 成功</span><span class="sxs-lookup"><span data-stu-id="a3409-123">0 -- Success</span></span> <br/>  <span data-ttu-id="a3409-124">1-予想される障害</span><span class="sxs-lookup"><span data-stu-id="a3409-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="a3409-125">2-予期しないエラー</span><span class="sxs-lookup"><span data-stu-id="a3409-125">2 - Unexpected failure</span></span> <br/> |
   

