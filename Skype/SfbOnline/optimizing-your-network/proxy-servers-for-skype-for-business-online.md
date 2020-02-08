---
title: Teams または Skype for Business Online 向けのプロキシ サーバー
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: この記事では、Skype for Business でのプロキシサーバーの使用について説明します。
ms.openlocfilehash: a154b36fc03dc84916d5cb4bd383ff80bef901cd
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863754"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="3acd4-103">Skype for Business Online のプロキシサーバー</span><span class="sxs-lookup"><span data-stu-id="3acd4-103">Proxy servers for Skype for Business Online</span></span>

<span data-ttu-id="3acd4-104">この記事では、Skype for Business でのプロキシサーバーの使用に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="3acd4-104">This article provides guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="3acd4-105">プロキシ サーバーの使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="3acd4-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="3acd4-106">プロキシ経由の Skype for Business トラフィックについては、Microsoft はプロキシをバイパスすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3acd4-106">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="3acd4-107">プロキシでは、トラフィックが既に暗号化されているため、Skype for Business のセキュリティを強化することはできません。</span><span class="sxs-lookup"><span data-stu-id="3acd4-107">Proxies don't make Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="3acd4-108">また、プロキシを使用すると問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3acd4-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="3acd4-109">パフォーマンスに関連する問題は、待ち時間とパケット損失によって環境に導入される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3acd4-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="3acd4-110">このような問題が発生した場合、そのようなチームまたは Skype for Business のシナリオでは、リアルタイムのストリームが不可欠であるため、オーディオとビデオとして、否定的な経験が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3acd4-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="3acd4-111">プロキシ サーバーを使用する必要がある場合</span><span class="sxs-lookup"><span data-stu-id="3acd4-111">If you need to use a proxy server</span></span>

<span data-ttu-id="3acd4-p103">組織によっては、Skype for Business トラフィックのプロキシをバイパスするオプションがありません。そのような場合は、上記の問題について注意しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="3acd4-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="3acd4-114">Microsoft は次を実行することもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3acd4-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="3acd4-115">外部の DNS 解決を使用する</span><span class="sxs-lookup"><span data-stu-id="3acd4-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="3acd4-116">ダイレクト UDP ベースのルーティングを使用する</span><span class="sxs-lookup"><span data-stu-id="3acd4-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="3acd4-117">UDP トラフィックを許可する</span><span class="sxs-lookup"><span data-stu-id="3acd4-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="3acd4-118">ネットワークガイドラインのその他の推奨事項に従ってください。</span><span class="sxs-lookup"><span data-stu-id="3acd4-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="3acd4-119">Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="3acd4-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](media-quality-and-network-connectivity-performance.md)
    
  - [<span data-ttu-id="3acd4-120">Skype for Business Online 向けのネットワークの最適化</span><span class="sxs-lookup"><span data-stu-id="3acd4-120">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
    
<span data-ttu-id="3acd4-121">このガイダンスに従うことで、問題が生じる可能性が最小になります。</span><span class="sxs-lookup"><span data-stu-id="3acd4-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3acd4-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3acd4-122">Related topics</span></span>

[<span data-ttu-id="3acd4-123">Skype for Business Online 向けのネットワークの最適化</span><span class="sxs-lookup"><span data-stu-id="3acd4-123">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
 