---
title: Skype for Business Server 2015 でのモビリティのパフォーマンスの監視
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: '概要: では、ビジネス サーバー 2015 の Skype のモビリティ サービス (Mcx) とユニファイド コミュニケーション Web API (UCWA) について説明します。'
ms.openlocfilehash: 1981bff8398f3fab9206f9dab748c545268f7edf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server-2015"></a><span data-ttu-id="b06bc-103">Skype for Business Server 2015 でのモビリティのパフォーマンスの監視</span><span class="sxs-lookup"><span data-stu-id="b06bc-103">Monitor mobility for performance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b06bc-104">**の概要:**ビジネス サーバー 2015 の Skype のモビリティ サービス (Mcx) とユニファイド コミュニケーション Web API (UCWA) について説明します。</span><span class="sxs-lookup"><span data-stu-id="b06bc-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b06bc-105">ビジネス サーバー移動サービス (Mcx) と、ユニファイド コミュニケーション Web API (UCWA) の Skype では、フロント エンド サーバーとフロント エンド プールの負荷が増加します。</span><span class="sxs-lookup"><span data-stu-id="b06bc-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="b06bc-106">Lync 2013 モバイルを実行しているアプリとアップルのデバイスと同様に Lync 2010 のモバイルを実行している Android および Nokia のデバイスなど、モバイル アプリケーションが最小化されている場合でも、サーバーへの接続を維持するモバイル デバイスがデバイスよりも大きな負荷を課すことモバイル アプリケーションが最小化したときに、サーバーへの接続を終了します。</span><span class="sxs-lookup"><span data-stu-id="b06bc-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="b06bc-107">モビリティの使用量が増えるにつれて、モビリティのパフォーマンス、容量を増やす必要がある場合を決定するを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b06bc-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>
  
<span data-ttu-id="b06bc-108">モビリティのパフォーマンスに影響を与えるいくつかの制限値があります。</span><span class="sxs-lookup"><span data-stu-id="b06bc-108">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="b06bc-109">使用可能なメモリ</span><span class="sxs-lookup"><span data-stu-id="b06bc-109">Available memory</span></span>
    
- <span data-ttu-id="b06bc-110">要求キューの制限</span><span class="sxs-lookup"><span data-stu-id="b06bc-110">Request queue limit</span></span>
    
- <span data-ttu-id="b06bc-111">同時接続数</span><span class="sxs-lookup"><span data-stu-id="b06bc-111">Concurrent connections</span></span>
    
- <span data-ttu-id="b06bc-112">IIS キューの長さ</span><span class="sxs-lookup"><span data-stu-id="b06bc-112">IIS queue length</span></span>
    
<span data-ttu-id="b06bc-p102">モビリティのパフォーマンスに影響する可能性のある、サーバーへのその他の制限値として、最大 12 の同時サインイン数、認証数、セッションの更新数、および終了数があります。ただし、ほとんどの展開でこれらの最大値を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b06bc-p102">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="b06bc-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b06bc-115">In this section</span></span>

- [<span data-ttu-id="b06bc-116">ビジネス サーバー 2015 の Skype のサーバーのメモリ容量制限のためのモニター</span><span class="sxs-lookup"><span data-stu-id="b06bc-116">Monitor for server memory capacity limits in Skype for Business Server 2015</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="b06bc-117">ビジネス サーバー 2015 の Skype での移動サービスおよび UCWA の使用状況を監視します。</span><span class="sxs-lookup"><span data-stu-id="b06bc-117">Monitor Mobility Service and UCWA usage in Skype for Business Server 2015</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="b06bc-118">Skype ビジネス サーバー 2015 の高パフォーマンスのモバイル サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="b06bc-118">Configure Mobility Service for high performance in Skype for Business Server 2015</span></span>](configure-service.md)
    
- [<span data-ttu-id="b06bc-119">監視 IIS 要求トレース ログ ファイルでは、Skype ビジネス サーバー 2015 の</span><span class="sxs-lookup"><span data-stu-id="b06bc-119">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="b06bc-120">ビジネス サーバー 2015 の Skype のモビリティ パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="b06bc-120">Mobility performance counters in Skype for Business Server 2015</span></span>](performance-counters.md)
    

