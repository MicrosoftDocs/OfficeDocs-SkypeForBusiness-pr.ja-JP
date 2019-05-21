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
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Roles テーブルは、出席者や発表者など、可能な電話会議ロールのリストを保存する静的テーブルです。
ms.openlocfilehash: 2cf1fb22230d92951df0b3b8e18a5bd666c73519
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295896"
---
# <a name="roles-table"></a><span data-ttu-id="3aace-103">Roles テーブル</span><span class="sxs-lookup"><span data-stu-id="3aace-103">Roles table</span></span>
 
<span data-ttu-id="3aace-104">Roles テーブルは、出席者や発表者など、可能な電話会議ロールのリストを保存する静的テーブルです。</span><span class="sxs-lookup"><span data-stu-id="3aace-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="3aace-105">**列**</span><span class="sxs-lookup"><span data-stu-id="3aace-105">**Column**</span></span>|<span data-ttu-id="3aace-106">**データ型**</span><span class="sxs-lookup"><span data-stu-id="3aace-106">**Data Type**</span></span>|<span data-ttu-id="3aace-107">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="3aace-107">**Key/Index**</span></span>|<span data-ttu-id="3aace-108">**詳細**</span><span class="sxs-lookup"><span data-stu-id="3aace-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3aace-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="3aace-109">**RoleId**</span></span> <br/> |<span data-ttu-id="3aace-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="3aace-110">tinyint</span></span>  <br/> |<span data-ttu-id="3aace-111">Primary</span><span class="sxs-lookup"><span data-stu-id="3aace-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="3aace-112">**[役割]**</span><span class="sxs-lookup"><span data-stu-id="3aace-112">**Role**</span></span> <br/> |<span data-ttu-id="3aace-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3aace-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="3aace-114">許可される値:</span><span class="sxs-lookup"><span data-stu-id="3aace-114">Allowed values:</span></span> <br/>  <span data-ttu-id="3aace-115">0-不明</span><span class="sxs-lookup"><span data-stu-id="3aace-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="3aace-116">1-プレゼンター</span><span class="sxs-lookup"><span data-stu-id="3aace-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="3aace-117">2-出席者</span><span class="sxs-lookup"><span data-stu-id="3aace-117">2 - Attendee</span></span> <br/> |
   

