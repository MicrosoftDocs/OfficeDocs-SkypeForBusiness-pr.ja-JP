---
title: Skype のビジネス サーバー用の高パフォーマンスのモバイル サービスを構成します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: '概要: は、ビジネスのサーバーの Skype では、モビリティ サービスについて説明します。'
ms.openlocfilehash: bd787e78ebd3228faa1c47f1f54e688551c3e67d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926593"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="413b6-103">Skype のビジネス サーバー用の高パフォーマンスのモバイル サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="413b6-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="413b6-104">**の概要:** ビジネス サーバーは、Skype のモビリティ サービスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="413b6-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="413b6-105">このトピックは、ビジネス サーバー移動サービス (Mcx) の Skype にのみ適用し、Lync Server 2013 の累積的な更新プログラムで提供されるようにユニファイド コミュニケーション Web API (UCWA) では適用されません: 年 2013年 2 月。</span><span class="sxs-lookup"><span data-stu-id="413b6-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="413b6-106">モビリティ サービス (Mcx) では、インターネット インフォメーション サービス (IIS) 7.5 をインストールするとモビリティ サービスのインストーラーは、フロント エンド サーバー上でいくつかのパフォーマンス設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="413b6-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="413b6-107">モビリティでは IIS 7.5 を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="413b6-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="413b6-108">これらの設定は、同時ユーザー要求の最大数と、Mobility Service で利用できるスレッドの最大数に影響します。</span><span class="sxs-lookup"><span data-stu-id="413b6-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="413b6-109">以下にパフォーマンス設定を示します。</span><span class="sxs-lookup"><span data-stu-id="413b6-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="413b6-110">IIS 7.5 での Mcx の設定</span><span class="sxs-lookup"><span data-stu-id="413b6-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="413b6-111">**maxConcurrentThreadsPerCPU** は、ゼロ (0) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="413b6-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="413b6-112">**maxConcurrentRequestsPerCPU** は、ゼロ (0) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="413b6-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="413b6-113">ASP.NET プロセス モデルは、AutoConfig に設定されます (IIS 7.5 のみ)。</span><span class="sxs-lookup"><span data-stu-id="413b6-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="413b6-114">HTTP.sys のキューの制限は 1,000 に設定されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="413b6-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

