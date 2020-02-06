---
title: Skype for Business Server で高パフォーマンスのモビリティサービスを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: '概要: Skype for Business Server のモビリティサービスについて説明します。'
ms.openlocfilehash: d50aab5ced14753a7665c6560220d1dfdca1061d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818057"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="4895c-103">Skype for Business Server で高パフォーマンスのモビリティサービスを構成する</span><span class="sxs-lookup"><span data-stu-id="4895c-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="4895c-104">**概要:** Skype for Business Server のモビリティサービスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4895c-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4895c-105">このトピックは、Skype for Business Server Mobility Service (Mcx) にのみ適用され、Lync Server 2013 2013 の累積更新プログラムで提供されるように、統合コミュニケーション Web API (UCWA) には適用されません。</span><span class="sxs-lookup"><span data-stu-id="4895c-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="4895c-106">インターネットインフォメーションサービス (IIS) 7.5 にモバイルサービス (Mcx) をインストールすると、Mobility Service installer によって、フロントエンドサーバーの一部のパフォーマンス設定が構成されます。</span><span class="sxs-lookup"><span data-stu-id="4895c-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="4895c-107">モビリティでは IIS 7.5 を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4895c-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="4895c-108">これらの設定は、同時ユーザー要求の最大数と、Mobility Service で利用できるスレッドの最大数に影響します。</span><span class="sxs-lookup"><span data-stu-id="4895c-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="4895c-109">以下にパフォーマンス設定を示します。</span><span class="sxs-lookup"><span data-stu-id="4895c-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="4895c-110">IIS 7.5 での Mcx の設定</span><span class="sxs-lookup"><span data-stu-id="4895c-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="4895c-111">**maxConcurrentThreadsPerCPU** は、ゼロ (0) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4895c-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="4895c-112">**maxConcurrentRequestsPerCPU** は、ゼロ (0) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4895c-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="4895c-113">ASP.NET プロセス モデルは、AutoConfig に設定されます (IIS 7.5 のみ)。</span><span class="sxs-lookup"><span data-stu-id="4895c-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="4895c-114">HTTP.sys のキューの制限は 1,000 に設定されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="4895c-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

