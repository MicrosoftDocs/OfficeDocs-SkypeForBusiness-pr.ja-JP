---
title: Skype for Business Server 2015 の CallPriorities 度表
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
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 度テーブルは、"緊急"、"緊急"、"標準" などの、可能な呼び出しの優先順位の一覧を保存する静的テーブルです。
ms.openlocfilehash: 57ab4c2b190b14d26a7f8be1791eb70473f1eb3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815445"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e2626-103">Skype for Business Server 2015 の CallPriorities 度表</span><span class="sxs-lookup"><span data-stu-id="e2626-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e2626-104">CallPriorities 度テーブルは、"緊急"、"緊急"、"標準" などの、可能な呼び出しの優先順位の一覧を保存する静的テーブルです。</span><span class="sxs-lookup"><span data-stu-id="e2626-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="e2626-105">**列**</span><span class="sxs-lookup"><span data-stu-id="e2626-105">**Column**</span></span>|<span data-ttu-id="e2626-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="e2626-106">**Data Type**</span></span>|<span data-ttu-id="e2626-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="e2626-107">**Key/Index**</span></span>|<span data-ttu-id="e2626-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="e2626-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e2626-109">**優先順位 Id**</span><span class="sxs-lookup"><span data-stu-id="e2626-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="e2626-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="e2626-110">tinyint</span></span>  <br/> |<span data-ttu-id="e2626-111">Primary</span><span class="sxs-lookup"><span data-stu-id="e2626-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="e2626-112">**[Priority]**</span><span class="sxs-lookup"><span data-stu-id="e2626-112">**Priority**</span></span> <br/> |<span data-ttu-id="e2626-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e2626-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="e2626-114">許可される値:</span><span class="sxs-lookup"><span data-stu-id="e2626-114">Allowed values:</span></span> <br/>  <span data-ttu-id="e2626-115">0-不明</span><span class="sxs-lookup"><span data-stu-id="e2626-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="e2626-116">1-緊急以外</span><span class="sxs-lookup"><span data-stu-id="e2626-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="e2626-117">2-標準</span><span class="sxs-lookup"><span data-stu-id="e2626-117">2 - Normal</span></span> <br/>  <span data-ttu-id="e2626-118">3-緊急</span><span class="sxs-lookup"><span data-stu-id="e2626-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="e2626-119">4-緊急</span><span class="sxs-lookup"><span data-stu-id="e2626-119">4 - Emergency</span></span> <br/> |
   

