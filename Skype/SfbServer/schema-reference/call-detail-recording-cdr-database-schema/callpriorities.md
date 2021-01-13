---
title: Skype for Business Server 2015 の CallPriorities テーブル
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
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities テーブルは、"emergency"、"urgent"、"normal" など、可能な通話優先度のリストを格納する静的テーブルです。
ms.openlocfilehash: 54fdd70dcd939cfeb227862d6152577c4c91d3b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813437"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4b3d3-103">Skype for Business Server 2015 の CallPriorities テーブル</span><span class="sxs-lookup"><span data-stu-id="4b3d3-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4b3d3-104">CallPriorities テーブルは、"emergency"、"urgent"、"normal" など、可能な通話優先度のリストを格納する静的テーブルです。</span><span class="sxs-lookup"><span data-stu-id="4b3d3-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="4b3d3-105">**列**</span><span class="sxs-lookup"><span data-stu-id="4b3d3-105">**Column**</span></span>|<span data-ttu-id="4b3d3-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="4b3d3-106">**Data Type**</span></span>|<span data-ttu-id="4b3d3-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="4b3d3-107">**Key/Index**</span></span>|<span data-ttu-id="4b3d3-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="4b3d3-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4b3d3-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="4b3d3-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="4b3d3-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="4b3d3-110">tinyint</span></span>  <br/> |<span data-ttu-id="4b3d3-111">Primary</span><span class="sxs-lookup"><span data-stu-id="4b3d3-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="4b3d3-112">**[優先度]**</span><span class="sxs-lookup"><span data-stu-id="4b3d3-112">**Priority**</span></span> <br/> |<span data-ttu-id="4b3d3-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4b3d3-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="4b3d3-114">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4b3d3-114">Allowed values:</span></span> <br/>  <span data-ttu-id="4b3d3-115">0 - 不明</span><span class="sxs-lookup"><span data-stu-id="4b3d3-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="4b3d3-116">1 - 非緊急</span><span class="sxs-lookup"><span data-stu-id="4b3d3-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="4b3d3-117">2 -- 通常</span><span class="sxs-lookup"><span data-stu-id="4b3d3-117">2 - Normal</span></span> <br/>  <span data-ttu-id="4b3d3-118">3 -- 至急</span><span class="sxs-lookup"><span data-stu-id="4b3d3-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="4b3d3-119">4 -- 緊急</span><span class="sxs-lookup"><span data-stu-id="4b3d3-119">4 - Emergency</span></span> <br/> |
   

