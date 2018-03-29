---
title: EndpointSubnet テーブル
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
description: EndpointSubnet はテーブルをサポートします。 各レコードでは、エンドポイントから取得された 1 つのサブネットを表します。
ms.openlocfilehash: 71df1d94fd8aa74969249090f7f1d4a21939bcd2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="endpointsubnet-table"></a><span data-ttu-id="4d9c5-104">EndpointSubnet テーブル</span><span class="sxs-lookup"><span data-stu-id="4d9c5-104">EndpointSubnet table</span></span>
 
<span data-ttu-id="4d9c5-105">EndpointSubnet はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="4d9c5-105">The EndpointSubnet table is a supporting table.</span></span> <span data-ttu-id="4d9c5-106">各レコードでは、エンドポイントから取得された 1 つのサブネットを表します。</span><span class="sxs-lookup"><span data-stu-id="4d9c5-106">Each record represents one subnet captured from endpoints.</span></span> 
  
|<span data-ttu-id="4d9c5-107">**列**</span><span class="sxs-lookup"><span data-stu-id="4d9c5-107">**Column**</span></span>|<span data-ttu-id="4d9c5-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="4d9c5-108">**Data Type**</span></span>|<span data-ttu-id="4d9c5-109">**キーまたはインデックス**</span><span class="sxs-lookup"><span data-stu-id="4d9c5-109">**Key/Index**</span></span>|<span data-ttu-id="4d9c5-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="4d9c5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4d9c5-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="4d9c5-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="4d9c5-112">int</span><span class="sxs-lookup"><span data-stu-id="4d9c5-112">int</span></span>  <br/> |<span data-ttu-id="4d9c5-113">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="4d9c5-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="4d9c5-114">サブネットの整数表現。</span><span class="sxs-lookup"><span data-stu-id="4d9c5-114">Integer representation for the subnet.</span></span>  <br/> |
|<span data-ttu-id="4d9c5-115">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="4d9c5-115">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="4d9c5-116">datetime</span><span class="sxs-lookup"><span data-stu-id="4d9c5-116">datetime</span></span>  <br/> ||<span data-ttu-id="4d9c5-117">内部でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="4d9c5-117">For internal use only.</span></span>  <br/> |
   

