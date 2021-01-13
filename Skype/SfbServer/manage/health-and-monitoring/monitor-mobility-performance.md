---
title: Skype for Business Server でモビリティのパフォーマンスを監視する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: '概要: Skype for Business Server の Mobility Service (Mcx) と Unified Communications Web API (UCWA) について説明します。'
ms.openlocfilehash: d7473d22f2de0576bf6214ae43719c8bfc70d49a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816837"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="b10bf-103">Skype for Business Server でモビリティのパフォーマンスを監視する</span><span class="sxs-lookup"><span data-stu-id="b10bf-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="b10bf-104">**概要:** Skype for Business Server の Mobility Service (Mcx) と Unified Communications Web API (UCWA) について説明します。</span><span class="sxs-lookup"><span data-stu-id="b10bf-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="b10bf-105">Skype for Business Server Mobility Service (Mcx) および Unified Communications Web API (UCWA) を使用すると、フロントエンド サーバーとフロントエンド プールの負荷が増加します。</span><span class="sxs-lookup"><span data-stu-id="b10bf-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="b10bf-106">Lync 2010 Mobile を実行している Android デバイスや Nokia デバイス、および Lync 2013 Mobile を実行している Android デバイスや Apple デバイスなど、モバイル アプリケーションが最小化されている場合でも、サーバーへの接続を維持するモバイル デバイスは、モバイル アプリケーションが最小化されているときにサーバーへの接続を終了するデバイスよりも大きな負荷を課します。</span><span class="sxs-lookup"><span data-stu-id="b10bf-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="b10bf-107">モビリティの使用が増加するに応じて、モビリティのパフォーマンスを監視して、容量を増やす必要がある場合を判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b10bf-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="b10bf-108">従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b10bf-108">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="b10bf-109">現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b10bf-109">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="b10bf-110">MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b10bf-110">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="b10bf-111">モビリティのパフォーマンスに影響を与えるいくつかの制限値があります。</span><span class="sxs-lookup"><span data-stu-id="b10bf-111">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="b10bf-112">使用可能なメモリ</span><span class="sxs-lookup"><span data-stu-id="b10bf-112">Available memory</span></span>
    
- <span data-ttu-id="b10bf-113">要求キューの制限</span><span class="sxs-lookup"><span data-stu-id="b10bf-113">Request queue limit</span></span>
    
- <span data-ttu-id="b10bf-114">同時接続数</span><span class="sxs-lookup"><span data-stu-id="b10bf-114">Concurrent connections</span></span>
    
- <span data-ttu-id="b10bf-115">IIS キューの長さ</span><span class="sxs-lookup"><span data-stu-id="b10bf-115">IIS queue length</span></span>
    
<span data-ttu-id="b10bf-116">モビリティのパフォーマンスに影響を与える可能性があるサーバーのその他の制限は、最大 12 の同時サインイン、認証、セッションの更新、および終了です。</span><span class="sxs-lookup"><span data-stu-id="b10bf-116">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="b10bf-117">ただし、ほとんどの展開でこれらの最大値を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b10bf-117">These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="b10bf-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b10bf-118">In this section</span></span>

- [<span data-ttu-id="b10bf-119">Skype for Business Server でサーバーのメモリ容量制限を監視する</span><span class="sxs-lookup"><span data-stu-id="b10bf-119">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="b10bf-120">Skype for Business Server での Mobility Service と UCWA の使用状況の監視</span><span class="sxs-lookup"><span data-stu-id="b10bf-120">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="b10bf-121">Skype for Business Server で高パフォーマンスを実現する Mobility Service の構成</span><span class="sxs-lookup"><span data-stu-id="b10bf-121">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="b10bf-122">Skype for Business Server での IIS 要求トレース ログ ファイルの監視</span><span class="sxs-lookup"><span data-stu-id="b10bf-122">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="b10bf-123">Skype for Business Server のモビリティ パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="b10bf-123">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

