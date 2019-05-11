---
title: ビジネス サーバー 2015 の Skype での CallPriorities テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities テーブルは、'緊急'、'緊急'、または '通常' など、可能な呼び出しの優先順位の一覧を格納する静的なテーブルです。
ms.openlocfilehash: aac21073e98d7c1ef8d137a736445b62e4fb9878
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901530"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a><span data-ttu-id="88c69-103">ビジネス サーバー 2015 の Skype での CallPriorities テーブル</span><span class="sxs-lookup"><span data-stu-id="88c69-103">CallPriorities table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="88c69-104">CallPriorities テーブルは、'緊急'、'緊急'、または '通常' など、可能な呼び出しの優先順位の一覧を格納する静的なテーブルです。</span><span class="sxs-lookup"><span data-stu-id="88c69-104">The CallPriorities table is a static table that stores the list of possible call priorities, such as 'emergency', 'urgent', or 'normal'.</span></span>
  
|<span data-ttu-id="88c69-105">**列**</span><span class="sxs-lookup"><span data-stu-id="88c69-105">**Column**</span></span>|<span data-ttu-id="88c69-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="88c69-106">**Data Type**</span></span>|<span data-ttu-id="88c69-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="88c69-107">**Key/Index**</span></span>|<span data-ttu-id="88c69-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="88c69-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="88c69-109">**PriorityId**</span><span class="sxs-lookup"><span data-stu-id="88c69-109">**PriorityId**</span></span> <br/> |<span data-ttu-id="88c69-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="88c69-110">tinyint</span></span>  <br/> |<span data-ttu-id="88c69-111">Primary</span><span class="sxs-lookup"><span data-stu-id="88c69-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="88c69-112">**[Priority]**</span><span class="sxs-lookup"><span data-stu-id="88c69-112">**Priority**</span></span> <br/> |<span data-ttu-id="88c69-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="88c69-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="88c69-114">使用可能な値:</span><span class="sxs-lookup"><span data-stu-id="88c69-114">Allowed values:</span></span> <br/>  <span data-ttu-id="88c69-115">0 - 不明</span><span class="sxs-lookup"><span data-stu-id="88c69-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="88c69-116">1-切迫感のないです。</span><span class="sxs-lookup"><span data-stu-id="88c69-116">1 - Non-Urgent</span></span> <br/>  <span data-ttu-id="88c69-117">2-標準</span><span class="sxs-lookup"><span data-stu-id="88c69-117">2 - Normal</span></span> <br/>  <span data-ttu-id="88c69-118">3-緊急</span><span class="sxs-lookup"><span data-stu-id="88c69-118">3 - Urgent</span></span> <br/>  <span data-ttu-id="88c69-119">4-緊急</span><span class="sxs-lookup"><span data-stu-id="88c69-119">4 - Emergency</span></span> <br/> |
   

