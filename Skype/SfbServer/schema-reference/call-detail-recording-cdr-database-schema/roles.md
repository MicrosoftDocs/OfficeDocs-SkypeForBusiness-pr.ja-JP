---
title: Roles テーブル
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Roles テーブルは、出席者や発表者など、可能な電話会議ロールのリストを保存する静的テーブルです。
ms.openlocfilehash: 8ebd01bc9cc51b33d28f87aa85be1473a6397201
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814935"
---
# <a name="roles-table"></a><span data-ttu-id="fda2d-103">Roles テーブル</span><span class="sxs-lookup"><span data-stu-id="fda2d-103">Roles table</span></span>
 
<span data-ttu-id="fda2d-104">Roles テーブルは、出席者や発表者など、可能な電話会議ロールのリストを保存する静的テーブルです。</span><span class="sxs-lookup"><span data-stu-id="fda2d-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="fda2d-105">**列**</span><span class="sxs-lookup"><span data-stu-id="fda2d-105">**Column**</span></span>|<span data-ttu-id="fda2d-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="fda2d-106">**Data Type**</span></span>|<span data-ttu-id="fda2d-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="fda2d-107">**Key/Index**</span></span>|<span data-ttu-id="fda2d-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="fda2d-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fda2d-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="fda2d-109">**RoleId**</span></span> <br/> |<span data-ttu-id="fda2d-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="fda2d-110">tinyint</span></span>  <br/> |<span data-ttu-id="fda2d-111">Primary</span><span class="sxs-lookup"><span data-stu-id="fda2d-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="fda2d-112">**役割**</span><span class="sxs-lookup"><span data-stu-id="fda2d-112">**Role**</span></span> <br/> |<span data-ttu-id="fda2d-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fda2d-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="fda2d-114">許可される値:</span><span class="sxs-lookup"><span data-stu-id="fda2d-114">Allowed values:</span></span> <br/>  <span data-ttu-id="fda2d-115">0-不明</span><span class="sxs-lookup"><span data-stu-id="fda2d-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="fda2d-116">1-プレゼンター</span><span class="sxs-lookup"><span data-stu-id="fda2d-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="fda2d-117">2-出席者</span><span class="sxs-lookup"><span data-stu-id="fda2d-117">2 - Attendee</span></span> <br/> |
   

