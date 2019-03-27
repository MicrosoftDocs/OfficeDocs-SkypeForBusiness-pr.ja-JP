---
title: ビジネス サーバー 2015 の Skype での CallPriorities テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities テーブルは、'緊急'、'緊急'、または '通常' など、可能な呼び出しの優先順位の一覧を格納する静的なテーブルです。
ms.openlocfilehash: faf4e7f04d7a63b096cb2369c21916e5fcb71a24
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882991"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d1755-103">ビジネス サーバー 2015 の Skype での CallPriorities テーブル</span><span class="sxs-lookup"><span data-stu-id="d1755-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d1755-104">CallPriorities テーブルは、'緊急'、'緊急'、または '通常' など、可能な呼び出しの優先順位の一覧を格納する静的なテーブルです。</span><span class="sxs-lookup"><span data-stu-id="d1755-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="d1755-105">**列**</span><span class="sxs-lookup"><span data-stu-id="d1755-105">**Column**</span></span>|<span data-ttu-id="d1755-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="d1755-106">**Data Type**</span></span>|<span data-ttu-id="d1755-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="d1755-107">**Key/Index**</span></span>|<span data-ttu-id="d1755-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="d1755-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d1755-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="d1755-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="d1755-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="d1755-110">tinyint</span></span>  <br/> |<span data-ttu-id="d1755-111">Primary</span><span class="sxs-lookup"><span data-stu-id="d1755-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="d1755-112">**[Priority]**</span><span class="sxs-lookup"><span data-stu-id="d1755-112">**Priority**</span></span> <br/> |<span data-ttu-id="d1755-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d1755-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="d1755-114">使用可能な値:</span><span class="sxs-lookup"><span data-stu-id="d1755-114">Allowed values:</span></span> <br/>  <span data-ttu-id="d1755-115">0 - 不明</span><span class="sxs-lookup"><span data-stu-id="d1755-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="d1755-116">1-切迫感のないです。</span><span class="sxs-lookup"><span data-stu-id="d1755-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="d1755-117">2-標準</span><span class="sxs-lookup"><span data-stu-id="d1755-117">2 - Normal</span></span> <br/>  <span data-ttu-id="d1755-118">3-緊急</span><span class="sxs-lookup"><span data-stu-id="d1755-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="d1755-119">4-緊急</span><span class="sxs-lookup"><span data-stu-id="d1755-119">4 - Emergency</span></span> <br/> |
   

