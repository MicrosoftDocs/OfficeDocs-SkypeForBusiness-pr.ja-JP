---
title: ビジネス サーバー 2015 の Skype での CallPriorities テーブル
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
ms.openlocfilehash: ccd92857015e865e36cbef4147c4355369263e90
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8d280-103">ビジネス サーバー 2015 の Skype での CallPriorities テーブル</span><span class="sxs-lookup"><span data-stu-id="8d280-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8d280-104">CallPriorities テーブルは、'緊急'、'緊急'、または '通常' など、可能な呼び出しの優先順位の一覧を格納する静的なテーブルです。</span><span class="sxs-lookup"><span data-stu-id="8d280-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="8d280-105">**列**</span><span class="sxs-lookup"><span data-stu-id="8d280-105">**Column**</span></span>|<span data-ttu-id="8d280-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="8d280-106">**Data Type**</span></span>|<span data-ttu-id="8d280-107">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="8d280-107">**Key/Index**</span></span>|<span data-ttu-id="8d280-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="8d280-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8d280-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="8d280-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="8d280-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="8d280-110">tinyint</span></span>  <br/> |<span data-ttu-id="8d280-111">Primary</span><span class="sxs-lookup"><span data-stu-id="8d280-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="8d280-112">**優先度**</span><span class="sxs-lookup"><span data-stu-id="8d280-112">**Priority**</span></span> <br/> |<span data-ttu-id="8d280-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8d280-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="8d280-114">使用可能な値:</span><span class="sxs-lookup"><span data-stu-id="8d280-114">Allowed values:</span></span> <br/>  <span data-ttu-id="8d280-115">0 - 不明</span><span class="sxs-lookup"><span data-stu-id="8d280-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="8d280-116">1-切迫感のないです。</span><span class="sxs-lookup"><span data-stu-id="8d280-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="8d280-117">2-標準</span><span class="sxs-lookup"><span data-stu-id="8d280-117">2 - Normal</span></span> <br/>  <span data-ttu-id="8d280-118">3-緊急</span><span class="sxs-lookup"><span data-stu-id="8d280-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="8d280-119">4-緊急</span><span class="sxs-lookup"><span data-stu-id="8d280-119">4 - Emergency</span></span> <br/> |
   

