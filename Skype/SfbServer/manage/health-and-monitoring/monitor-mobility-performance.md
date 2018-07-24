---
title: Skype でのパフォーマンスをビジネスのサーバーの移動を監視します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: '概要: は、ビジネスのサーバーに、モビリティ サービス (Mcx)、Skype では、ユニファイド コミュニケーション Web API (UCWA) について説明します。'
ms.openlocfilehash: 4affcb532697f24c87d62e18fc26552639dc00e1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20990638"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="8d1ae-103">Skype でのパフォーマンスをビジネスのサーバーの移動を監視します。</span><span class="sxs-lookup"><span data-stu-id="8d1ae-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="8d1ae-104">**の概要:** Business Server には、モビリティ サービス (Mcx)、Skype では、ユニファイド コミュニケーション Web API (UCWA) について説明します。</span><span class="sxs-lookup"><span data-stu-id="8d1ae-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="8d1ae-105">ビジネス サーバー移動サービス (Mcx) と、ユニファイド コミュニケーション Web API (UCWA) の Skype では、フロント エンド サーバーとフロント エンド プールの負荷が増加します。</span><span class="sxs-lookup"><span data-stu-id="8d1ae-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="8d1ae-106">Lync 2013 モバイルを実行しているアプリとアップルのデバイスと同様に Lync 2010 のモバイルを実行している Android および Nokia のデバイスなど、モバイル アプリケーションが最小化されている場合でも、サーバーへの接続を維持するモバイル デバイスがデバイスよりも大きな負荷を課すことモバイル アプリケーションが最小化したときに、サーバーへの接続を終了します。</span><span class="sxs-lookup"><span data-stu-id="8d1ae-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="8d1ae-107">モビリティの使用量が増えるにつれて、モビリティのパフォーマンス、容量を増やす必要がある場合を決定するを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d1ae-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="8d1ae-108">従来のモバイル クライアント用の MCX サポートはビジネス サーバー 2019 の Skype で利用可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="8d1ae-108">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="8d1ae-109">ユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d1ae-109">Your users will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="8d1ae-110">モビリティのパフォーマンスに影響を与えるいくつかの制限値があります。</span><span class="sxs-lookup"><span data-stu-id="8d1ae-110">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="8d1ae-111">使用可能なメモリ</span><span class="sxs-lookup"><span data-stu-id="8d1ae-111">Available memory</span></span>
    
- <span data-ttu-id="8d1ae-112">要求キューの制限</span><span class="sxs-lookup"><span data-stu-id="8d1ae-112">Request queue limit</span></span>
    
- <span data-ttu-id="8d1ae-113">同時接続数</span><span class="sxs-lookup"><span data-stu-id="8d1ae-113">Concurrent connections</span></span>
    
- <span data-ttu-id="8d1ae-114">IIS キューの長さ</span><span class="sxs-lookup"><span data-stu-id="8d1ae-114">IIS queue length</span></span>
    
<span data-ttu-id="8d1ae-p103">モビリティのパフォーマンスに影響する可能性のある、サーバーへのその他の制限値として、最大 12 の同時サインイン数、認証数、セッションの更新数、および終了数があります。ただし、ほとんどの展開でこれらの最大値を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8d1ae-p103">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="8d1ae-117">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8d1ae-117">In this section</span></span>

- [<span data-ttu-id="8d1ae-118">Skype ビジネス サーバー用にサーバーのメモリ容量制限のためのモニター</span><span class="sxs-lookup"><span data-stu-id="8d1ae-118">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="8d1ae-119">ビジネス サーバーの Skype での移動サービスおよび UCWA の使用状況を監視します。</span><span class="sxs-lookup"><span data-stu-id="8d1ae-119">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="8d1ae-120">Skype のビジネス サーバー用の高パフォーマンスのモバイル サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="8d1ae-120">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="8d1ae-121">Skype 内のログ ファイルのトレースをビジネスのサーバーを IIS 要求を監視します。</span><span class="sxs-lookup"><span data-stu-id="8d1ae-121">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="8d1ae-122">Skype ビジネス サーバーの移動のパフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="8d1ae-122">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

