---
title: Subnet テーブル
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Subnet テーブルは、サポート テーブルです。 それぞれのレコードは、ネットワーク構成の設定で定義された 1 つのサブネットを表します。
ms.openlocfilehash: b4683c654d5d188d2f5096dd7ec9da124001f68b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831337"
---
# <a name="subnet-table"></a><span data-ttu-id="21c00-104">Subnet テーブル</span><span class="sxs-lookup"><span data-stu-id="21c00-104">Subnet table</span></span>
 
<span data-ttu-id="21c00-p102">Subnet テーブルは、サポート テーブルです。それぞれのレコードは、ネットワーク構成の設定で定義された 1 つのサブネットを表します。</span><span class="sxs-lookup"><span data-stu-id="21c00-p102">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="21c00-107">**列**</span><span class="sxs-lookup"><span data-stu-id="21c00-107">**Column**</span></span>|<span data-ttu-id="21c00-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="21c00-108">**Data Type**</span></span>|<span data-ttu-id="21c00-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="21c00-109">**Key/Index**</span></span>|<span data-ttu-id="21c00-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="21c00-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="21c00-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="21c00-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="21c00-112">int</span><span class="sxs-lookup"><span data-stu-id="21c00-112">int</span></span>  <br/> |<span data-ttu-id="21c00-113">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="21c00-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="21c00-114">サブネット IP の整数表現。</span><span class="sxs-lookup"><span data-stu-id="21c00-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="21c00-115">**SubnetMask**</span><span class="sxs-lookup"><span data-stu-id="21c00-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="21c00-116">int</span><span class="sxs-lookup"><span data-stu-id="21c00-116">int</span></span>  <br/> ||<span data-ttu-id="21c00-117">サブネット マスク。</span><span class="sxs-lookup"><span data-stu-id="21c00-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="21c00-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="21c00-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="21c00-119">int</span><span class="sxs-lookup"><span data-stu-id="21c00-119">int</span></span>  <br/> |<span data-ttu-id="21c00-120">外部</span><span class="sxs-lookup"><span data-stu-id="21c00-120">Foreign</span></span>  <br/> |<span data-ttu-id="21c00-121">[UserSite テーブルから参照されます](usersite.md)。</span><span class="sxs-lookup"><span data-stu-id="21c00-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="21c00-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="21c00-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="21c00-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="21c00-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="21c00-124">サブネットの説明。</span><span class="sxs-lookup"><span data-stu-id="21c00-124">The description for the subnet.</span></span>  <br/> |
   

