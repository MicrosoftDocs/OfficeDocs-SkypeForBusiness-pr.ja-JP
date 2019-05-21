---
title: Teams または Skype for Business Online のプロキシサーバー
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection: M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: この記事では、Teams または Skype for Business でのプロキシサーバーの使用について説明します。
ms.openlocfilehash: e0733393a40c2d2c2fd62d986a4b4d66d0c2c35f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304371"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="999de-103">Teams または Skype for Business Online のプロキシサーバー</span><span class="sxs-lookup"><span data-stu-id="999de-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="999de-104">この記事では、Teams または Skype for Business でのプロキシサーバーの使用に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="999de-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="999de-105">プロキシ サーバーの使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="999de-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="999de-106">プロキシ経由の Teams または Skype for Business トラフィックについては、プロキシをバイパスすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="999de-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="999de-107">プロキシは、トラフィックが既に暗号化されているため、チームまたは Skype for Business の安全性を高めません。</span><span class="sxs-lookup"><span data-stu-id="999de-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="999de-108">また、プロキシを使用すると問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="999de-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="999de-109">パフォーマンスに関連する問題は、待ち時間とパケット損失によって環境に導入される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="999de-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="999de-110">このような問題が発生した場合、そのようなチームまたは Skype for Business のシナリオでは、リアルタイムのストリームが不可欠であるため、オーディオとビデオとして、否定的な経験が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="999de-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="999de-111">プロキシ サーバーを使用する必要がある場合</span><span class="sxs-lookup"><span data-stu-id="999de-111">If you need to use a proxy server</span></span>

<span data-ttu-id="999de-112">組織によっては、Teams または Skype for Business のトラフィックに対してプロキシをバイパスするオプションがありません。</span><span class="sxs-lookup"><span data-stu-id="999de-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="999de-113">そのような場合は、上記の問題について注意しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="999de-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="999de-114">Microsoft は次を実行することもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="999de-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="999de-115">外部の DNS 解決を使用する</span><span class="sxs-lookup"><span data-stu-id="999de-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="999de-116">ダイレクト UDP ベースのルーティングを使用する</span><span class="sxs-lookup"><span data-stu-id="999de-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="999de-117">UDP トラフィックを許可する</span><span class="sxs-lookup"><span data-stu-id="999de-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="999de-118">ネットワークガイドラインのその他の推奨事項に従ってください。</span><span class="sxs-lookup"><span data-stu-id="999de-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="999de-119">Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="999de-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="999de-120">Skype for Business Online 向けのネットワークの最適化</span><span class="sxs-lookup"><span data-stu-id="999de-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="999de-121">このガイダンスに従うことで、問題が生じる可能性が最小になります。</span><span class="sxs-lookup"><span data-stu-id="999de-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="999de-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="999de-122">Related topics</span></span>

[<span data-ttu-id="999de-123">Skype for Business Online 向けのネットワークの最適化</span><span class="sxs-lookup"><span data-stu-id="999de-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 