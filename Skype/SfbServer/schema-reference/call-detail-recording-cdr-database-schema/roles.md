---
title: Roles テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: ロール」テーブルは、出席者と発表者など、可能な会議の役割の一覧を格納する静的なテーブルです。
ms.openlocfilehash: e0088d059d6e4ed536e5f52e1290211377438889
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930305"
---
# <a name="roles-table"></a><span data-ttu-id="e7f65-103">Roles テーブル</span><span class="sxs-lookup"><span data-stu-id="e7f65-103">Roles table</span></span>
 
<span data-ttu-id="e7f65-104">ロール」テーブルは、出席者と発表者など、可能な会議の役割の一覧を格納する静的なテーブルです。</span><span class="sxs-lookup"><span data-stu-id="e7f65-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="e7f65-105">**列**</span><span class="sxs-lookup"><span data-stu-id="e7f65-105">**Column**</span></span>|<span data-ttu-id="e7f65-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="e7f65-106">**Data Type**</span></span>|<span data-ttu-id="e7f65-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="e7f65-107">**Key/Index**</span></span>|<span data-ttu-id="e7f65-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="e7f65-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e7f65-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="e7f65-109">**RoleId**</span></span> <br/> |<span data-ttu-id="e7f65-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="e7f65-110">tinyint</span></span>  <br/> |<span data-ttu-id="e7f65-111">Primary</span><span class="sxs-lookup"><span data-stu-id="e7f65-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="e7f65-112">**[役割]**</span><span class="sxs-lookup"><span data-stu-id="e7f65-112">**Role**</span></span> <br/> |<span data-ttu-id="e7f65-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e7f65-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="e7f65-114">使用可能な値:</span><span class="sxs-lookup"><span data-stu-id="e7f65-114">Allowed values:</span></span> <br/>  <span data-ttu-id="e7f65-115">0 - 不明</span><span class="sxs-lookup"><span data-stu-id="e7f65-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="e7f65-116">1-プレゼンター</span><span class="sxs-lookup"><span data-stu-id="e7f65-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="e7f65-117">2-出席者</span><span class="sxs-lookup"><span data-stu-id="e7f65-117">2 - Attendee</span></span> <br/> |
   

