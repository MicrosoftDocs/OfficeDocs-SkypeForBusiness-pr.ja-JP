---
title: Subnet テーブル
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: サブネット テーブルはサポート テーブルです。 各レコードは、ネットワーク構成設定で定義されている 1 つのサブネットを表します。
ms.openlocfilehash: aa91202bfb46a96f86ea3a631be3b964a17a6058
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212089"
---
# <a name="subnet-table"></a><span data-ttu-id="aa1d3-104">Subnet テーブル</span><span class="sxs-lookup"><span data-stu-id="aa1d3-104">Subnet table</span></span>
 
<span data-ttu-id="aa1d3-105">サブネット テーブルはサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="aa1d3-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="aa1d3-106">各レコードは、ネットワーク構成設定で定義されている 1 つのサブネットを表します。</span><span class="sxs-lookup"><span data-stu-id="aa1d3-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="aa1d3-107">**列**</span><span class="sxs-lookup"><span data-stu-id="aa1d3-107">**Column**</span></span>|<span data-ttu-id="aa1d3-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="aa1d3-108">**Data Type**</span></span>|<span data-ttu-id="aa1d3-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="aa1d3-109">**Key/Index**</span></span>|<span data-ttu-id="aa1d3-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="aa1d3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="aa1d3-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="aa1d3-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="aa1d3-112">int</span><span class="sxs-lookup"><span data-stu-id="aa1d3-112">int</span></span>  <br/> |<span data-ttu-id="aa1d3-113">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="aa1d3-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="aa1d3-114">サブネット ip アドレスの整数表現。</span><span class="sxs-lookup"><span data-stu-id="aa1d3-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="aa1d3-115">**サブネット マスク**</span><span class="sxs-lookup"><span data-stu-id="aa1d3-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="aa1d3-116">int</span><span class="sxs-lookup"><span data-stu-id="aa1d3-116">int</span></span>  <br/> ||<span data-ttu-id="aa1d3-117">サブネット マスク。</span><span class="sxs-lookup"><span data-stu-id="aa1d3-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="aa1d3-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="aa1d3-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="aa1d3-119">int</span><span class="sxs-lookup"><span data-stu-id="aa1d3-119">int</span></span>  <br/> |<span data-ttu-id="aa1d3-120">外部</span><span class="sxs-lookup"><span data-stu-id="aa1d3-120">Foreign</span></span>  <br/> |<span data-ttu-id="aa1d3-121">[UserSite テーブル](usersite.md)から参照されています。</span><span class="sxs-lookup"><span data-stu-id="aa1d3-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="aa1d3-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="aa1d3-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="aa1d3-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="aa1d3-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="aa1d3-124">サブネットの説明です。</span><span class="sxs-lookup"><span data-stu-id="aa1d3-124">The description for the subnet.</span></span>  <br/> |
   

