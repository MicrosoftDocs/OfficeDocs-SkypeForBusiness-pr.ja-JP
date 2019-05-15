---
title: Subnet テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: サブネット テーブルはサポート テーブルです。 各レコードは、ネットワーク構成設定で定義されている 1 つのサブネットを表します。
ms.openlocfilehash: f659d73bbdd654365697a9f853fbb48162e1bba2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907067"
---
# <a name="subnet-table"></a><span data-ttu-id="4d9c8-104">Subnet テーブル</span><span class="sxs-lookup"><span data-stu-id="4d9c8-104">Subnet table</span></span>
 
<span data-ttu-id="4d9c8-105">サブネット テーブルはサポート テーブルです。</span><span class="sxs-lookup"><span data-stu-id="4d9c8-105">The Subnet table is a supporting table.</span></span> <span data-ttu-id="4d9c8-106">各レコードは、ネットワーク構成設定で定義されている 1 つのサブネットを表します。</span><span class="sxs-lookup"><span data-stu-id="4d9c8-106">Each record represents one subnet defined in network configuration setting.</span></span>
  
|<span data-ttu-id="4d9c8-107">**列**</span><span class="sxs-lookup"><span data-stu-id="4d9c8-107">**Column**</span></span>|<span data-ttu-id="4d9c8-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="4d9c8-108">**Data Type**</span></span>|<span data-ttu-id="4d9c8-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="4d9c8-109">**Key/Index**</span></span>|<span data-ttu-id="4d9c8-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="4d9c8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4d9c8-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="4d9c8-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="4d9c8-112">int</span><span class="sxs-lookup"><span data-stu-id="4d9c8-112">int</span></span>  <br/> |<span data-ttu-id="4d9c8-113">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="4d9c8-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="4d9c8-114">サブネット ip アドレスの整数表現。</span><span class="sxs-lookup"><span data-stu-id="4d9c8-114">Integer representation for the subnet IP.</span></span>  <br/> |
|<span data-ttu-id="4d9c8-115">**サブネット マスク**</span><span class="sxs-lookup"><span data-stu-id="4d9c8-115">**SubnetMask**</span></span> <br/> |<span data-ttu-id="4d9c8-116">int</span><span class="sxs-lookup"><span data-stu-id="4d9c8-116">int</span></span>  <br/> ||<span data-ttu-id="4d9c8-117">サブネット マスク。</span><span class="sxs-lookup"><span data-stu-id="4d9c8-117">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="4d9c8-118">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="4d9c8-118">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="4d9c8-119">int</span><span class="sxs-lookup"><span data-stu-id="4d9c8-119">int</span></span>  <br/> |<span data-ttu-id="4d9c8-120">外部</span><span class="sxs-lookup"><span data-stu-id="4d9c8-120">Foreign</span></span>  <br/> |<span data-ttu-id="4d9c8-121">[UserSite テーブル](usersite.md)から参照されています。</span><span class="sxs-lookup"><span data-stu-id="4d9c8-121">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="4d9c8-122">**SubnetDescription**</span><span class="sxs-lookup"><span data-stu-id="4d9c8-122">**SubnetDescription**</span></span> <br/> |<span data-ttu-id="4d9c8-123">nvarchar(512)</span><span class="sxs-lookup"><span data-stu-id="4d9c8-123">nvarchar(512)</span></span>  <br/> ||<span data-ttu-id="4d9c8-124">サブネットの説明です。</span><span class="sxs-lookup"><span data-stu-id="4d9c8-124">The description for the subnet.</span></span>  <br/> |
   

