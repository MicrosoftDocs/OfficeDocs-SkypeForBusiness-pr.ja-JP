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
localization_priority: Normal
ms.assetid: d62e51d6-2117-4c41-adce-08f8d9d75ce0
description: EndpointSubnet テーブルは、サポートテーブルです。 各レコードは、エンドポイントから取得された1つのサブネットを表します。
ms.openlocfilehash: b8a8e62178919da72082f99acad7798f3935a5ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294951"
---
# <a name="endpointsubnet-table"></a><span data-ttu-id="e25e5-104">EndpointSubnet テーブル</span><span class="sxs-lookup"><span data-stu-id="e25e5-104">EndpointSubnet table</span></span>
 
<span data-ttu-id="e25e5-105">EndpointSubnet テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="e25e5-105">The EndpointSubnet table is a supporting table.</span></span> <span data-ttu-id="e25e5-106">各レコードは、エンドポイントから取得された1つのサブネットを表します。</span><span class="sxs-lookup"><span data-stu-id="e25e5-106">Each record represents one subnet captured from endpoints.</span></span> 
  
|<span data-ttu-id="e25e5-107">**列**</span><span class="sxs-lookup"><span data-stu-id="e25e5-107">**Column**</span></span>|<span data-ttu-id="e25e5-108">**データ型**</span><span class="sxs-lookup"><span data-stu-id="e25e5-108">**Data Type**</span></span>|<span data-ttu-id="e25e5-109">**キー/インデックス**</span><span class="sxs-lookup"><span data-stu-id="e25e5-109">**Key/Index**</span></span>|<span data-ttu-id="e25e5-110">**詳細**</span><span class="sxs-lookup"><span data-stu-id="e25e5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e25e5-111">**SubnetIP**</span><span class="sxs-lookup"><span data-stu-id="e25e5-111">**SubnetIP**</span></span> <br/> |<span data-ttu-id="e25e5-112">int</span><span class="sxs-lookup"><span data-stu-id="e25e5-112">int</span></span>  <br/> |<span data-ttu-id="e25e5-113">プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="e25e5-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e25e5-114">サブネットの整数表現。</span><span class="sxs-lookup"><span data-stu-id="e25e5-114">Integer representation for the subnet.</span></span>  <br/> |
|<span data-ttu-id="e25e5-115">**Nextupdatupdat**</span><span class="sxs-lookup"><span data-stu-id="e25e5-115">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="e25e5-116">datetime</span><span class="sxs-lookup"><span data-stu-id="e25e5-116">datetime</span></span>  <br/> ||<span data-ttu-id="e25e5-117">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="e25e5-117">For internal use only.</span></span>  <br/> |
   

