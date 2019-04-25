---
title: チームやビジネス オンラインの Skype のプロキシ サーバー
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: この資料では、ビジネスのためのチームまたは Skype でプロキシ サーバーを使用する方法の情報を提供します。
ms.openlocfilehash: a09a1bf53fe4d1a38742856c051a80e5928f36ef
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32246119"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="7c78d-103">チームやビジネス オンラインの Skype のプロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="7c78d-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="7c78d-104">この資料では、ビジネスのためのチームまたは Skype でプロキシ サーバーを使用する方法のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="7c78d-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="7c78d-105">プロキシ サーバーの使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="7c78d-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="7c78d-106">に関してはチームまたは Skype ビジネス トラフィックのプロキシを介して場合、は、プロキシをバイパスすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7c78d-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="7c78d-107">プロキシを作成しないチームやビジネス用の Skype よりセキュリティで保護されたトラフィックが既に暗号化されているためです。</span><span class="sxs-lookup"><span data-stu-id="7c78d-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="7c78d-108">プロキシを持つと、問題が発生することができます。</span><span class="sxs-lookup"><span data-stu-id="7c78d-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="7c78d-109">パフォーマンス関連の問題は、遅延とパケット損失を環境に導入できます。</span><span class="sxs-lookup"><span data-stu-id="7c78d-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="7c78d-110">リアルタイム ストリームが必要なオーディオとビデオ、ビジネス シナリオのようなチームや Skype での負の経験ではこれらの問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="7c78d-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="7c78d-111">プロキシ サーバーを使用する必要がある場合</span><span class="sxs-lookup"><span data-stu-id="7c78d-111">If you need to use a proxy server</span></span>

<span data-ttu-id="7c78d-112">一部の組織があるチームまたは Skype のビジネスのトラフィックのプロキシをバイパスするオプションなし。</span><span class="sxs-lookup"><span data-stu-id="7c78d-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="7c78d-113">そのような場合は、上記の問題について注意しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c78d-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="7c78d-114">Microsoft は次を実行することもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7c78d-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="7c78d-115">外部の DNS 解決を使用する</span><span class="sxs-lookup"><span data-stu-id="7c78d-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="7c78d-116">ダイレクト UDP ベースのルーティングを使用する</span><span class="sxs-lookup"><span data-stu-id="7c78d-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="7c78d-117">UDP トラフィックを許可する</span><span class="sxs-lookup"><span data-stu-id="7c78d-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="7c78d-118">ネットワーク ガイドラインの他の推奨事項に従います。</span><span class="sxs-lookup"><span data-stu-id="7c78d-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="7c78d-119">Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="7c78d-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="7c78d-120">Skype for Business Online 向けのネットワークの最適化</span><span class="sxs-lookup"><span data-stu-id="7c78d-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="7c78d-121">このガイダンスに従うことで、問題が生じる可能性が最小になります。</span><span class="sxs-lookup"><span data-stu-id="7c78d-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7c78d-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7c78d-122">Related topics</span></span>

[<span data-ttu-id="7c78d-123">Skype for Business Online 向けのネットワークの最適化</span><span class="sxs-lookup"><span data-stu-id="7c78d-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 