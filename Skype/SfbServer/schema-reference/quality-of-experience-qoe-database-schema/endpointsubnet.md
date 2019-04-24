---
title: EndpointSubnet テーブル
ms.reviewer: ''
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
ms.openlocfilehash: 43cb50a3c59ac81d0b1d0f00d66cfc3c8775693b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212229"
---
# <a name="endpointsubnet-table"></a><span data-ttu-id="5e558-104">EndpointSubnet テーブル</span><span class="sxs-lookup"><span data-stu-id="5e558-104">EndpointSubnet table</span></span>
 
<span data-ttu-id="5e558-105">EndpointSubnet はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5e558-105">The EndpointSubnet table is a supporting table.</span></span> <span data-ttu-id="5e558-106">各レコードでは、エンドポイントから取得された 1 つのサブネットを表します。</span><span class="sxs-lookup"><span data-stu-id="5e558-106">Each record represents one subnet captured from endpoints.</span></span> 
  
|<span data-ttu-id="5e558-107">**列**</span><span class="sxs-lookup"><span data-stu-id="5e558-107">**Column**</span></span>|<span data-ttu-id="5e558-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="5e558-108">**Data Type**</span></span>|<span data-ttu-id="5e558-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="5e558-109">**Key/Index**</span></span>|<span data-ttu-id="5e558-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="5e558-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5e558-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="5e558-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="5e558-112">int</span><span class="sxs-lookup"><span data-stu-id="5e558-112">int</span></span>  <br/> |<span data-ttu-id="5e558-113">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="5e558-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="5e558-114">サブネットの整数表現。</span><span class="sxs-lookup"><span data-stu-id="5e558-114">Integer representation for the subnet.</span></span>  <br/> |
|<span data-ttu-id="5e558-115">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="5e558-115">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="5e558-116">datetime</span><span class="sxs-lookup"><span data-stu-id="5e558-116">datetime</span></span>  <br/> ||<span data-ttu-id="5e558-117">内部でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="5e558-117">For internal use only.</span></span>  <br/> |
   

