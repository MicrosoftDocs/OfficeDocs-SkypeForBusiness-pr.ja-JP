---
title: Roles テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: ロール」テーブルは、出席者と発表者など、可能な会議の役割の一覧を格納する静的なテーブルです。
ms.openlocfilehash: a9f35c510eaca054dd504db4045686cb4eeaac4c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="roles-table"></a><span data-ttu-id="98d06-103">Roles テーブル</span><span class="sxs-lookup"><span data-stu-id="98d06-103">Roles table</span></span>
 
<span data-ttu-id="98d06-104">ロール」テーブルは、出席者と発表者など、可能な会議の役割の一覧を格納する静的なテーブルです。</span><span class="sxs-lookup"><span data-stu-id="98d06-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="98d06-105">**列**</span><span class="sxs-lookup"><span data-stu-id="98d06-105">**Column**</span></span>|<span data-ttu-id="98d06-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="98d06-106">**Data Type**</span></span>|<span data-ttu-id="98d06-107">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="98d06-107">**Key/Index**</span></span>|<span data-ttu-id="98d06-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="98d06-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="98d06-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="98d06-109">**RoleId**</span></span> <br/> |<span data-ttu-id="98d06-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="98d06-110">tinyint</span></span>  <br/> |<span data-ttu-id="98d06-111">Primary</span><span class="sxs-lookup"><span data-stu-id="98d06-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="98d06-112">**[役割]**</span><span class="sxs-lookup"><span data-stu-id="98d06-112">**Role**</span></span> <br/> |<span data-ttu-id="98d06-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="98d06-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="98d06-114">使用可能な値:</span><span class="sxs-lookup"><span data-stu-id="98d06-114">Allowed values:</span></span> <br/>  <span data-ttu-id="98d06-115">0 - 不明</span><span class="sxs-lookup"><span data-stu-id="98d06-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="98d06-116">1-プレゼンター</span><span class="sxs-lookup"><span data-stu-id="98d06-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="98d06-117">2-出席者</span><span class="sxs-lookup"><span data-stu-id="98d06-117">2 - Attendee</span></span> <br/> |
   

