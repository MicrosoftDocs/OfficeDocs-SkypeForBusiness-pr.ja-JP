---
title: 'Lync Server 2013: パフォーマンスのためのモビリティの監視'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3b6cbdefcb7c78f68fe8838109dea3be5b8203d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a><span data-ttu-id="1ddce-102">Lync Server 2013 でのモバイルパフォーマンスの監視</span><span class="sxs-lookup"><span data-stu-id="1ddce-102">Monitoring mobility for performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ddce-103">_**最終更新日:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="1ddce-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="1ddce-104">Lync Server Mobility Service (Mcx) とユニファイドコミュニケーション Web API (UCWA) では、フロントエンドサーバーとフロントエンドプールの負荷が高くなります。</span><span class="sxs-lookup"><span data-stu-id="1ddce-104">The Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="1ddce-105">モバイルアプリケーションが最小化されている場合でもサーバーへの接続を維持するモバイルデバイス (lync 2010 Mobile を実行している Android や Nokia デバイス、Lync 2013 Mobile を実行している Android および Apple デバイスなど) には、高負荷の負荷がかかることがあります。モバイルアプリケーションが最小化されているときに、サーバーとの接続を終了します。</span><span class="sxs-lookup"><span data-stu-id="1ddce-105">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="1ddce-106">モバイル使用の増加に応じて、容量を増やす必要があるタイミングを判断するために、モビリティのパフォーマンスを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ddce-106">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

<span data-ttu-id="1ddce-107">モビリティのパフォーマンスに影響を与えるいくつかの制限値があります。</span><span class="sxs-lookup"><span data-stu-id="1ddce-107">Several limits influence mobility performance:</span></span>

  - <span data-ttu-id="1ddce-108">使用可能なメモリ</span><span class="sxs-lookup"><span data-stu-id="1ddce-108">Available memory</span></span>

  - <span data-ttu-id="1ddce-109">要求キューの制限</span><span class="sxs-lookup"><span data-stu-id="1ddce-109">Request queue limit</span></span>

  - <span data-ttu-id="1ddce-110">同時接続数</span><span class="sxs-lookup"><span data-stu-id="1ddce-110">Concurrent connections</span></span>

  - <span data-ttu-id="1ddce-111">IIS キューの長さ</span><span class="sxs-lookup"><span data-stu-id="1ddce-111">IIS queue length</span></span>

<span data-ttu-id="1ddce-112">モビリティのパフォーマンスに影響を与える可能性のあるサーバーの制限は、最大12個の同時サインイン、認証、セッションの更新、終了です。</span><span class="sxs-lookup"><span data-stu-id="1ddce-112">Other limits on servers that can influence mobility performance are a maximum of twelve concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="1ddce-113">ただし、ほとんどの展開でこれらの最大値を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1ddce-113">These maximums do not need to be modified for most deployments.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1ddce-114">このセクション中</span><span class="sxs-lookup"><span data-stu-id="1ddce-114">In This Section</span></span>

  - [<span data-ttu-id="1ddce-115">Lync Server 2013 でのサーバーメモリ容量の上限を監視する</span><span class="sxs-lookup"><span data-stu-id="1ddce-115">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [<span data-ttu-id="1ddce-116">Lync Server 2013 でのモビリティサービスと UCWA の使用状況の監視</span><span class="sxs-lookup"><span data-stu-id="1ddce-116">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [<span data-ttu-id="1ddce-117">Lync Server 2013 での高パフォーマンスのモビリティサービスの構成</span><span class="sxs-lookup"><span data-stu-id="1ddce-117">Configuring Mobility Service for high performance in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [<span data-ttu-id="1ddce-118">Lync Server 2013 で IIS 要求トレースのログファイルを監視する</span><span class="sxs-lookup"><span data-stu-id="1ddce-118">Monitoring IIS request tracing log files in Lync Server 2013</span></span>](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [<span data-ttu-id="1ddce-119">Lync Server 2013 のモバイルパフォーマンスカウンター</span><span class="sxs-lookup"><span data-stu-id="1ddce-119">Mobility performance counters in Lync Server 2013</span></span>](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

