---
title: 'Lync Server 2013: 高パフォーマンスのモビリティサービスの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 460c56a9e51ab64491402eed22d40d60ad7d89c1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a><span data-ttu-id="66d1a-102">Lync Server 2013 での高パフォーマンスの Mobility Service の構成</span><span class="sxs-lookup"><span data-stu-id="66d1a-102">Configuring Mobility Service for high performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66d1a-103">_**トピックの最終更新日:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="66d1a-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="66d1a-104">このトピックは Lync Server 2013 Mobility Service (Mcx) にのみ適用され、Lync Server 2013 の累積的な更新プログラム (2 月 11 2013 日) で提供されるように、統合コミュニケーション Web API (UCWA) には適用されません。</span><span class="sxs-lookup"><span data-stu-id="66d1a-104">This topic applies only to the Lync Server 2013 Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="66d1a-105">インターネットインフォメーションサービス (IIS) 7.5 に Mobility Service (Mcx) をインストールすると、Mobility Service インストーラーによってフロントエンドサーバーのパフォーマンス設定の一部が構成されます。</span><span class="sxs-lookup"><span data-stu-id="66d1a-105">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="66d1a-106">モビリティでは IIS 7.5 を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="66d1a-106">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="66d1a-107">これらの設定は、同時ユーザー要求の最大数と、Mobility Service で利用できるスレッドの最大数に影響します。</span><span class="sxs-lookup"><span data-stu-id="66d1a-107">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>

<span data-ttu-id="66d1a-108">次に、パフォーマンス設定を示します。</span><span class="sxs-lookup"><span data-stu-id="66d1a-108">Here are the performance settings:</span></span>

<div>

## <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="66d1a-109">IIS 7.5 上の Mcx の設定</span><span class="sxs-lookup"><span data-stu-id="66d1a-109">Settings for Mcx on IIS 7.5</span></span>

1.  <span data-ttu-id="66d1a-110">**maxConcurrentThreadsPerCPU** は、ゼロ (0) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="66d1a-110">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>

2.  <span data-ttu-id="66d1a-111">**maxConcurrentRequestsPerCPU** は、ゼロ (0) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="66d1a-111">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>

3.  <span data-ttu-id="66d1a-112">ASP.NET プロセス モデルは、AutoConfig に設定されます (IIS 7.5 のみ)。</span><span class="sxs-lookup"><span data-stu-id="66d1a-112">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>

4.  <span data-ttu-id="66d1a-113">HTTP.sys のキューの制限は 1,000 に設定されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="66d1a-113">HTTP.sys queue limit is set to 1,000 (by default).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

