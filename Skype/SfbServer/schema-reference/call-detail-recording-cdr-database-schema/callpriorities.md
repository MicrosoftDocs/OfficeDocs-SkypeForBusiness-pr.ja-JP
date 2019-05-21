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
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 度テーブルは、"緊急"、"緊急"、"標準" などの、可能な呼び出しの優先順位の一覧を保存する静的テーブルです。
ms.openlocfilehash: 6d324ce11b2e149378b6275441cb4a2467a641db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296568"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e5f95-103">Skype for Business Server 2015 の CallPriorities 度表</span><span class="sxs-lookup"><span data-stu-id="e5f95-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e5f95-104">CallPriorities 度テーブルは、"緊急"、"緊急"、"標準" などの、可能な呼び出しの優先順位の一覧を保存する静的テーブルです。</span><span class="sxs-lookup"><span data-stu-id="e5f95-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="e5f95-105">**列**</span><span class="sxs-lookup"><span data-stu-id="e5f95-105">**Column**</span></span>|<span data-ttu-id="e5f95-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="e5f95-106">**Data Type**</span></span>|<span data-ttu-id="e5f95-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="e5f95-107">**Key/Index**</span></span>|<span data-ttu-id="e5f95-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="e5f95-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e5f95-109">**優先順位 Id**</span><span class="sxs-lookup"><span data-stu-id="e5f95-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="e5f95-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="e5f95-110">tinyint</span></span>  <br/> |<span data-ttu-id="e5f95-111">Primary</span><span class="sxs-lookup"><span data-stu-id="e5f95-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="e5f95-112">**[Priority]**</span><span class="sxs-lookup"><span data-stu-id="e5f95-112">**Priority**</span></span> <br/> |<span data-ttu-id="e5f95-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5f95-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="e5f95-114">許可される値:</span><span class="sxs-lookup"><span data-stu-id="e5f95-114">Allowed values:</span></span> <br/>  <span data-ttu-id="e5f95-115">0-不明</span><span class="sxs-lookup"><span data-stu-id="e5f95-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="e5f95-116">1-緊急以外</span><span class="sxs-lookup"><span data-stu-id="e5f95-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="e5f95-117">2-標準</span><span class="sxs-lookup"><span data-stu-id="e5f95-117">2 - Normal</span></span> <br/>  <span data-ttu-id="e5f95-118">3-緊急</span><span class="sxs-lookup"><span data-stu-id="e5f95-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="e5f95-119">4-緊急</span><span class="sxs-lookup"><span data-stu-id="e5f95-119">4 - Emergency</span></span> <br/> |
   

