---
title: EndpointSubnet テーブル
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
description: EndpointSubnet テーブルは、サポートテーブルです。 各レコードは、エンドポイントから取得された1つのサブネットを表します。
ms.openlocfilehash: dcb80256a8a1fb1fb880021e140a0f037142087f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809345"
---
# <a name="endpointsubnet-table"></a><span data-ttu-id="c24d8-104">EndpointSubnet テーブル</span><span class="sxs-lookup"><span data-stu-id="c24d8-104">EndpointSubnet table</span></span>
 
<span data-ttu-id="c24d8-105">EndpointSubnet テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="c24d8-105">The EndpointSubnet table is a supporting table.</span></span> <span data-ttu-id="c24d8-106">各レコードは、エンドポイントから取得された1つのサブネットを表します。</span><span class="sxs-lookup"><span data-stu-id="c24d8-106">Each record represents one subnet captured from endpoints.</span></span> 
  
|<span data-ttu-id="c24d8-107">**列**</span><span class="sxs-lookup"><span data-stu-id="c24d8-107">**Column**</span></span>|<span data-ttu-id="c24d8-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="c24d8-108">**Data Type**</span></span>|<span data-ttu-id="c24d8-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="c24d8-109">**Key/Index**</span></span>|<span data-ttu-id="c24d8-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="c24d8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c24d8-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="c24d8-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="c24d8-112">int</span><span class="sxs-lookup"><span data-stu-id="c24d8-112">int</span></span>  <br/> |<span data-ttu-id="c24d8-113">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="c24d8-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="c24d8-114">サブネットの整数表現。</span><span class="sxs-lookup"><span data-stu-id="c24d8-114">Integer representation for the subnet.</span></span>  <br/> |
|<span data-ttu-id="c24d8-115">**Nextupdatupdat**</span><span class="sxs-lookup"><span data-stu-id="c24d8-115">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="c24d8-116">datetime</span><span class="sxs-lookup"><span data-stu-id="c24d8-116">datetime</span></span>  <br/> ||<span data-ttu-id="c24d8-117">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="c24d8-117">For internal use only.</span></span>  <br/> |
   

