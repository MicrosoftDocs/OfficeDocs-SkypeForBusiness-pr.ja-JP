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
description: この記事では、Skype for Business でのプロキシ サーバーの使用に関する情報を提供します。
ms.openlocfilehash: 09ed98c5f69d6e244a5f87125e4ad607e4d16226
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240416"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="e5eda-103">Skype for Business Online のプロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="e5eda-103">Proxy servers for Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="e5eda-104">この記事では、Skype for Business でのプロキシ サーバーの使用に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5eda-104">This article provides guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="e5eda-105">プロキシ サーバーの使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="e5eda-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="e5eda-106">プロキシ経由の Skype for Business トラフィックについては、Microsoft はプロキシをバイパスすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e5eda-106">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="e5eda-107">プロキシは、トラフィックが既に暗号化されているので、Skype for Business の安全性を高めしません。</span><span class="sxs-lookup"><span data-stu-id="e5eda-107">Proxies don't make Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="e5eda-108">プロキシを使用すると、問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e5eda-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="e5eda-109">パフォーマンス関連の問題は、待機時間とパケット損失によって環境に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e5eda-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="e5eda-110">このような問題は、リアルタイム ストリームが不可欠なオーディオやビデオなどの Teams や Skype for Business のシナリオで悪影響を及ぶ結果になります。</span><span class="sxs-lookup"><span data-stu-id="e5eda-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="e5eda-111">プロキシ サーバーを使用する必要がある場合</span><span class="sxs-lookup"><span data-stu-id="e5eda-111">If you need to use a proxy server</span></span>

<span data-ttu-id="e5eda-p103">組織によっては、Skype for Business トラフィックのプロキシをバイパスするオプションがありません。そのような場合は、上記の問題について注意しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5eda-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="e5eda-114">Microsoft は次を実行することもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e5eda-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="e5eda-115">外部の DNS 解決を使用する</span><span class="sxs-lookup"><span data-stu-id="e5eda-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="e5eda-116">ダイレクト UDP ベースのルーティングを使用する</span><span class="sxs-lookup"><span data-stu-id="e5eda-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="e5eda-117">UDP トラフィックを許可する</span><span class="sxs-lookup"><span data-stu-id="e5eda-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="e5eda-118">ネットワーク ガイドラインの他の推奨事項に従います。</span><span class="sxs-lookup"><span data-stu-id="e5eda-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="e5eda-119">Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="e5eda-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](media-quality-and-network-connectivity-performance.md)
    
  - [<span data-ttu-id="e5eda-120">Skype for Business Online 向けのネットワークの最適化</span><span class="sxs-lookup"><span data-stu-id="e5eda-120">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
    
<span data-ttu-id="e5eda-121">このガイダンスに従うことで、問題が生じる可能性が最小になります。</span><span class="sxs-lookup"><span data-stu-id="e5eda-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e5eda-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5eda-122">Related topics</span></span>

[<span data-ttu-id="e5eda-123">Skype for Business Online 向けのネットワークの最適化</span><span class="sxs-lookup"><span data-stu-id="e5eda-123">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
 
