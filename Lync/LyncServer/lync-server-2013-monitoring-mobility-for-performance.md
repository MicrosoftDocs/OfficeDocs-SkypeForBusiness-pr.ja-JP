---
title: 'Lync Server 2013: パフォーマンスのためのモビリティの監視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 131a6a4dd6fffb3081ff2b1dee58318afd525eaa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a><span data-ttu-id="a9ac4-102">Lync Server 2013 でのパフォーマンスのためのモビリティの監視</span><span class="sxs-lookup"><span data-stu-id="a9ac4-102">Monitoring mobility for performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9ac4-103">_**トピックの最終更新日:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="a9ac4-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="a9ac4-104">Lync Server Mobility Service (Mcx) と統合コミュニケーション Web API (UCWA) によって、フロントエンドサーバーおよびフロントエンドプールの負荷が増加します。</span><span class="sxs-lookup"><span data-stu-id="a9ac4-104">The Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="a9ac4-105">モバイルアプリケーションが最小化されている場合でも (Lync 2010 Mobile を実行している Android や Nokia デバイス、Lync 2013 Mobile を実行している Android や Apple デバイスなど)、サーバーとの接続を維持するモバイルデバイスでは、デバイスよりも高い負荷が課せられています。モバイルアプリケーションが最小化されている場合は、サーバーへの接続を終了します。</span><span class="sxs-lookup"><span data-stu-id="a9ac4-105">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="a9ac4-106">モビリティの使用量が増加するにつれて、モビリティのパフォーマンスを監視して、処理能力を高める必要があるかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9ac4-106">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

<span data-ttu-id="a9ac4-107">モビリティのパフォーマンスに影響を与えるいくつかの制限値があります。</span><span class="sxs-lookup"><span data-stu-id="a9ac4-107">Several limits influence mobility performance:</span></span>

  - <span data-ttu-id="a9ac4-108">使用可能なメモリ</span><span class="sxs-lookup"><span data-stu-id="a9ac4-108">Available memory</span></span>

  - <span data-ttu-id="a9ac4-109">要求キューの制限</span><span class="sxs-lookup"><span data-stu-id="a9ac4-109">Request queue limit</span></span>

  - <span data-ttu-id="a9ac4-110">同時接続数</span><span class="sxs-lookup"><span data-stu-id="a9ac4-110">Concurrent connections</span></span>

  - <span data-ttu-id="a9ac4-111">IIS キューの長さ</span><span class="sxs-lookup"><span data-stu-id="a9ac4-111">IIS queue length</span></span>

<span data-ttu-id="a9ac4-112">モビリティのパフォーマンスに影響を与える可能性があるサーバーのその他の制限は、最大12個の同時サインイン、認証、セッション更新、および終了です。</span><span class="sxs-lookup"><span data-stu-id="a9ac4-112">Other limits on servers that can influence mobility performance are a maximum of twelve concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="a9ac4-113">ただし、ほとんどの展開でこれらの最大値を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a9ac4-113">These maximums do not need to be modified for most deployments.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a9ac4-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a9ac4-114">In This Section</span></span>

  - [<span data-ttu-id="a9ac4-115">Lync Server 2013 でのサーバーのメモリ容量制限の監視</span><span class="sxs-lookup"><span data-stu-id="a9ac4-115">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [<span data-ttu-id="a9ac4-116">Lync Server 2013 でのモビリティサービスおよび UCWA の使用状況の監視</span><span class="sxs-lookup"><span data-stu-id="a9ac4-116">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [<span data-ttu-id="a9ac4-117">Lync Server 2013 での高パフォーマンスの Mobility Service の構成</span><span class="sxs-lookup"><span data-stu-id="a9ac4-117">Configuring Mobility Service for high performance in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [<span data-ttu-id="a9ac4-118">Lync Server 2013 での IIS 要求トレースログファイルの監視</span><span class="sxs-lookup"><span data-stu-id="a9ac4-118">Monitoring IIS request tracing log files in Lync Server 2013</span></span>](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [<span data-ttu-id="a9ac4-119">Lync Server 2013 のモビリティパフォーマンスカウンター</span><span class="sxs-lookup"><span data-stu-id="a9ac4-119">Mobility performance counters in Lync Server 2013</span></span>](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

