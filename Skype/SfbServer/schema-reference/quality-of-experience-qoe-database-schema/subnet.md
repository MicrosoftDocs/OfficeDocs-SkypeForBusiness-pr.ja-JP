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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880477"
---
# <a name="subnet-table"></a><span data-ttu-id="30b78-104">Subnet テーブル</span><span class="sxs-lookup"><span data-stu-id="30b78-104">Subnet table</span></span>
 
<span data-ttu-id="30b78-105">サブネット テーブルはサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="30b78-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="30b78-106">各レコードは、ネットワーク構成設定で定義されている 1 つのサブネットを表します。</span><span class="sxs-lookup"><span data-stu-id="30b78-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="30b78-107">**列**</span><span class="sxs-lookup"><span data-stu-id="30b78-107">**Column**</span></span>|<span data-ttu-id="30b78-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="30b78-108">**Data Type**</span></span>|<span data-ttu-id="30b78-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="30b78-109">**Key/Index**</span></span>|<span data-ttu-id="30b78-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="30b78-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="30b78-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="30b78-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="30b78-112">int</span><span class="sxs-lookup"><span data-stu-id="30b78-112">int</span></span>  <br/> |<span data-ttu-id="30b78-113">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="30b78-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="30b78-114">サブネット ip アドレスの整数表現。</span><span class="sxs-lookup"><span data-stu-id="30b78-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="30b78-115">**サブネット マスク**</span><span class="sxs-lookup"><span data-stu-id="30b78-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="30b78-116">int</span><span class="sxs-lookup"><span data-stu-id="30b78-116">int</span></span>  <br/> ||<span data-ttu-id="30b78-117">サブネット マスク。</span><span class="sxs-lookup"><span data-stu-id="30b78-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="30b78-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="30b78-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="30b78-119">int</span><span class="sxs-lookup"><span data-stu-id="30b78-119">int</span></span>  <br/> |<span data-ttu-id="30b78-120">外部</span><span class="sxs-lookup"><span data-stu-id="30b78-120">Foreign</span></span>  <br/> |<span data-ttu-id="30b78-121">[UserSite テーブル](usersite.md)から参照されています。</span><span class="sxs-lookup"><span data-stu-id="30b78-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="30b78-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="30b78-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="30b78-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="30b78-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="30b78-124">サブネットの説明です。</span><span class="sxs-lookup"><span data-stu-id="30b78-124">The description for the subnet.</span></span>  <br/> |
   

