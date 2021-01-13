---
title: EndpointSubnet テーブル
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
ms.assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
description: EndpointSubnet テーブルは、サポート テーブルです。 各レコードは、エンドポイントから取得された 1 つのサブネットを表します。
ms.openlocfilehash: 9671c7dc269b7f13f0679c6da12b46ea7d7c8b5f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815827"
---
# <a name="endpointsubnet-table"></a><span data-ttu-id="b4818-104">EndpointSubnet テーブル</span><span class="sxs-lookup"><span data-stu-id="b4818-104">EndpointSubnet table</span></span>
 
<span data-ttu-id="b4818-p102">EndpointSubnet テーブルは、サポート テーブルです。各レコードは、エンドポイントから取得された 1 つのサブネットを表します。</span><span class="sxs-lookup"><span data-stu-id="b4818-p102">The EndpointSubnet table is a supporting table. Each record represents one subnet captured from endpoints.</span></span> 
  
|<span data-ttu-id="b4818-107">**列**</span><span class="sxs-lookup"><span data-stu-id="b4818-107">**Column**</span></span>|<span data-ttu-id="b4818-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="b4818-108">**Data Type**</span></span>|<span data-ttu-id="b4818-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="b4818-109">**Key/Index**</span></span>|<span data-ttu-id="b4818-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="b4818-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b4818-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="b4818-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="b4818-112">int</span><span class="sxs-lookup"><span data-stu-id="b4818-112">int</span></span>  <br/> |<span data-ttu-id="b4818-113">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="b4818-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="b4818-114">サブネットの整数表現。</span><span class="sxs-lookup"><span data-stu-id="b4818-114">Integer representation for the subnet.</span></span>  <br/> |
|<span data-ttu-id="b4818-115">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="b4818-115">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="b4818-116">日付型</span><span class="sxs-lookup"><span data-stu-id="b4818-116">datetime</span></span>  <br/> ||<span data-ttu-id="b4818-117">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="b4818-117">For internal use only.</span></span>  <br/> |
   

