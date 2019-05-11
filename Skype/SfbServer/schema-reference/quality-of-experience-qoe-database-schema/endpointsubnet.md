---
title: EndpointSubnet テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
description: EndpointSubnet はテーブルをサポートします。 各レコードでは、エンドポイントから取得された 1 つのサブネットを表します。
ms.openlocfilehash: 5c40c58043514ba50f8b92baaa5ec9c3ae67bc1f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920125"
---
# <a name="endpointsubnet-table"></a><span data-ttu-id="2663d-104">EndpointSubnet テーブル</span><span class="sxs-lookup"><span data-stu-id="2663d-104">EndpointSubnet table</span></span>
 
<span data-ttu-id="2663d-105">EndpointSubnet はテーブルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="2663d-105">The EndpointSubnet table is a supporting table.</span></span> <span data-ttu-id="2663d-106">各レコードでは、エンドポイントから取得された 1 つのサブネットを表します。</span><span class="sxs-lookup"><span data-stu-id="2663d-106">Each record represents one subnet captured from endpoints.</span></span> 
  
|<span data-ttu-id="2663d-107">**列**</span><span class="sxs-lookup"><span data-stu-id="2663d-107">**Column**</span></span>|<span data-ttu-id="2663d-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="2663d-108">**Data Type**</span></span>|<span data-ttu-id="2663d-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="2663d-109">**Key/Index**</span></span>|<span data-ttu-id="2663d-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="2663d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2663d-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="2663d-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="2663d-112">int</span><span class="sxs-lookup"><span data-stu-id="2663d-112">int</span></span>  <br/> |<span data-ttu-id="2663d-113">プライマリ サーバーで、外部</span><span class="sxs-lookup"><span data-stu-id="2663d-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="2663d-114">サブネットの整数表現。</span><span class="sxs-lookup"><span data-stu-id="2663d-114">Integer representation for the subnet.</span></span>  <br/> |
|<span data-ttu-id="2663d-115">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="2663d-115">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="2663d-116">datetime</span><span class="sxs-lookup"><span data-stu-id="2663d-116">datetime</span></span>  <br/> ||<span data-ttu-id="2663d-117">内部でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="2663d-117">For internal use only.</span></span>  <br/> |
   

