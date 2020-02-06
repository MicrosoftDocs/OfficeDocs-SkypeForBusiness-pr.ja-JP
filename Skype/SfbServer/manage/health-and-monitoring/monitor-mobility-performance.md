---
title: Skype for Business Server のパフォーマンスを監視する
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
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: '概要: Skype for Business Server のモビリティサービス (Mcx) とユニファイドコミュニケーション Web API (UCWA) について説明します。'
ms.openlocfilehash: 4d604c46704881a055385336f8b1ff32862d929a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817836"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="0e132-103">Skype for Business Server のパフォーマンスを監視する</span><span class="sxs-lookup"><span data-stu-id="0e132-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="0e132-104">**概要:** Skype for Business Server のモビリティサービス (Mcx) とユニファイドコミュニケーション Web API (UCWA) について説明します。</span><span class="sxs-lookup"><span data-stu-id="0e132-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="0e132-105">Skype for Business Server Mobility Service (Mcx) とユニファイドコミュニケーション Web API (UCWA) では、フロントエンドサーバーとフロントエンドプールの負荷が高くなります。</span><span class="sxs-lookup"><span data-stu-id="0e132-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="0e132-106">モバイルアプリケーションが最小化されている場合でもサーバーへの接続を維持するモバイルデバイス (lync 2010 Mobile を実行している Android や Nokia デバイス、Lync 2013 Mobile を実行している Android および Apple デバイスなど) には、高負荷の負荷がかかることがあります。モバイルアプリケーションが最小化されているときに、サーバーとの接続を終了します。</span><span class="sxs-lookup"><span data-stu-id="0e132-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="0e132-107">モバイル使用の増加に応じて、容量を増やす必要があるタイミングを判断するために、モビリティのパフォーマンスを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e132-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="0e132-108">Skype for Business Server 2019 では、従来のモバイルクライアントに対する MCX (モバイルサービス) のサポートは利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0e132-108">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="0e132-109">現在のすべての Skype for Business のモバイルクライアントでは、インスタントメッセージング (IM)、プレゼンス、連絡先をサポートするために、既にユニファイドコミュニケーション Web API (UCWA) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="0e132-109">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="0e132-110">MCX を使用するレガシクライアントを使っているユーザーは、現在のクライアントにアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e132-110">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="0e132-111">モビリティのパフォーマンスに影響を与えるいくつかの制限値があります。</span><span class="sxs-lookup"><span data-stu-id="0e132-111">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="0e132-112">使用可能なメモリ</span><span class="sxs-lookup"><span data-stu-id="0e132-112">Available memory</span></span>
    
- <span data-ttu-id="0e132-113">要求キューの制限</span><span class="sxs-lookup"><span data-stu-id="0e132-113">Request queue limit</span></span>
    
- <span data-ttu-id="0e132-114">同時接続数</span><span class="sxs-lookup"><span data-stu-id="0e132-114">Concurrent connections</span></span>
    
- <span data-ttu-id="0e132-115">IIS キューの長さ</span><span class="sxs-lookup"><span data-stu-id="0e132-115">IIS queue length</span></span>
    
<span data-ttu-id="0e132-p103">モビリティのパフォーマンスに影響する可能性のある、サーバーへのその他の制限値として、最大 12 の同時サインイン数、認証数、セッションの更新数、および終了数があります。ただし、ほとんどの展開でこれらの最大値を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0e132-p103">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="0e132-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0e132-118">In this section</span></span>

- [<span data-ttu-id="0e132-119">Skype for Business Server でサーバーのメモリ容量の上限を監視する</span><span class="sxs-lookup"><span data-stu-id="0e132-119">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="0e132-120">Skype for Business Server のモビリティサービスと UCWA の使用状況を監視する</span><span class="sxs-lookup"><span data-stu-id="0e132-120">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="0e132-121">Skype for Business Server で高パフォーマンスのモビリティサービスを構成する</span><span class="sxs-lookup"><span data-stu-id="0e132-121">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="0e132-122">Skype for Business Server で IIS 要求トレースログファイルを監視する</span><span class="sxs-lookup"><span data-stu-id="0e132-122">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="0e132-123">Skype for Business Server のモバイルパフォーマンスカウンター</span><span class="sxs-lookup"><span data-stu-id="0e132-123">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

