---
title: Skype for Business Server で高パフォーマンスのモビリティサービスを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: '概要: Skype for Business Server のモビリティサービスについて説明します。'
ms.openlocfilehash: 35e04fa080964495ccd9abed28c0688dd7be45a9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305844"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="1e22b-103">Skype for Business Server で高パフォーマンスのモビリティサービスを構成する</span><span class="sxs-lookup"><span data-stu-id="1e22b-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="1e22b-104">**概要:** Skype for Business Server のモビリティサービスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1e22b-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1e22b-105">このトピックは、Skype for business server Mobility Service (mcx) にのみ適用され、Lync Server 2013 2013 の累積更新プログラムで提供されるように、統合コミュニケーション Web API (ucwa) には適用されません。</span><span class="sxs-lookup"><span data-stu-id="1e22b-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="1e22b-106">インターネットインフォメーションサービス (IIS) 7.5 にモバイルサービス (Mcx) をインストールすると、Mobility Service installer によって、フロントエンドサーバーの一部のパフォーマンス設定が構成されます。</span><span class="sxs-lookup"><span data-stu-id="1e22b-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="1e22b-107">モビリティでは IIS 7.5 を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1e22b-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="1e22b-108">これらの設定は、同時ユーザー要求の最大数と、Mobility Service で利用できるスレッドの最大数に影響します。</span><span class="sxs-lookup"><span data-stu-id="1e22b-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="1e22b-109">以下にパフォーマンス設定を示します。</span><span class="sxs-lookup"><span data-stu-id="1e22b-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="1e22b-110">IIS 7.5 での Mcx の設定</span><span class="sxs-lookup"><span data-stu-id="1e22b-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="1e22b-111">**maxConcurrentThreadsPerCPU** は、ゼロ (0) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1e22b-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="1e22b-112">**maxConcurrentRequestsPerCPU** は、ゼロ (0) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1e22b-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="1e22b-113">ASP.NET プロセス モデルは、AutoConfig に設定されます (IIS 7.5 のみ)。</span><span class="sxs-lookup"><span data-stu-id="1e22b-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="1e22b-114">HTTP.sys のキューの制限は 1,000 に設定されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="1e22b-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

