---
title: Subnet テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.
ms.openlocfilehash: ed54341e66c3370086047eb9b073d2560172a261
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="subnet-table"></a><span data-ttu-id="2014c-104">Subnet テーブル</span><span class="sxs-lookup"><span data-stu-id="2014c-104">Subnet table</span></span>
 
<span data-ttu-id="2014c-105">The Subnet table is a supporting table.</span><span class="sxs-lookup"><span data-stu-id="2014c-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="2014c-106">Each record represents one subnet defined in network configuration setting.</span><span class="sxs-lookup"><span data-stu-id="2014c-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="2014c-107">**Column**</span><span class="sxs-lookup"><span data-stu-id="2014c-107">**Column**</span></span>|<span data-ttu-id="2014c-108">**Data Type**</span><span class="sxs-lookup"><span data-stu-id="2014c-108">**Data Type**</span></span>|<span data-ttu-id="2014c-109">**Key/Index**</span><span class="sxs-lookup"><span data-stu-id="2014c-109">**Key/Index**</span></span>|<span data-ttu-id="2014c-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="2014c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2014c-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="2014c-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="2014c-112">int</span><span class="sxs-lookup"><span data-stu-id="2014c-112">int</span></span>  <br/> |<span data-ttu-id="2014c-113">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="2014c-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="2014c-114">Integer representation for the subnet IP.</span><span class="sxs-lookup"><span data-stu-id="2014c-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="2014c-115">**SubnetMask**</span><span class="sxs-lookup"><span data-stu-id="2014c-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="2014c-116">int</span><span class="sxs-lookup"><span data-stu-id="2014c-116">int</span></span>  <br/> ||<span data-ttu-id="2014c-117">サブネット マスク。</span><span class="sxs-lookup"><span data-stu-id="2014c-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="2014c-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="2014c-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="2014c-119">int</span><span class="sxs-lookup"><span data-stu-id="2014c-119">int</span></span>  <br/> |<span data-ttu-id="2014c-120">Foreign</span><span class="sxs-lookup"><span data-stu-id="2014c-120">Foreign</span></span>  <br/> |<span data-ttu-id="2014c-121">Referenced from the [UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="2014c-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="2014c-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="2014c-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="2014c-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="2014c-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="2014c-124">The description for the subnet.</span><span class="sxs-lookup"><span data-stu-id="2014c-124">The description for the subnet.</span></span>  <br/> |
   

