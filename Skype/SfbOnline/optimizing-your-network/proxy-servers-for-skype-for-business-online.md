---
title: "Skype for Business Online のプロキシ サーバー"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: "この記事にプロキシ サーバーを skype for Business を使ってに関するガイダンスを支援します。"
ms.openlocfilehash: 19c12ed4265c6549f00b54b3463215702d3ced2b
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="fe614-103">Skype for Business Online のプロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="fe614-103">Proxy Servers for Skype for Business Online</span></span>

<span data-ttu-id="fe614-104">この記事にプロキシ サーバーを skype for Business を使ってに関するガイダンスを支援します。</span><span class="sxs-lookup"><span data-stu-id="fe614-104">This article will help you with guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="fe614-105">推奨プロキシ サーバーを使用しません。</span><span class="sxs-lookup"><span data-stu-id="fe614-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="fe614-p101">際に Skype ビジネス トラフィック用プロキシ経由で、プロキシのバイパスをお勧めします。プロキシしない Skype for Business をより安全にトラフィックが既に暗号化されているためです。</span><span class="sxs-lookup"><span data-stu-id="fe614-p101">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Skype for Business more secure because its traffic is already encrypted.</span></span>
  
<span data-ttu-id="fe614-p102">プロキシのある問題が発生することができます。パフォーマンスに関連する問題を導入して、遅延とパケット損失をすることができます。これらなどの問題がリアルタイム ストリームが必須として、音声、ビデオ、ビジネス シナリオには、このような Skype で負のエクスペリエンスで発生します。</span><span class="sxs-lookup"><span data-stu-id="fe614-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="fe614-111">プロキシ サーバーを使用する必要がある場合</span><span class="sxs-lookup"><span data-stu-id="fe614-111">If you need to use a proxy server</span></span>

<span data-ttu-id="fe614-p103">一部の組織には、Skype for Business のトラフィック用のプロキシを使用しないオプションもありますありません。大文字と小文字の場合は、前述の問題を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe614-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="fe614-114">強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fe614-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="fe614-115">外部の DNS 解決を使用します。</span><span class="sxs-lookup"><span data-stu-id="fe614-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="fe614-116">ベースのルーティングを直接 UDP を使用します。</span><span class="sxs-lookup"><span data-stu-id="fe614-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="fe614-117">UDP トラフィックを許可します。</span><span class="sxs-lookup"><span data-stu-id="fe614-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="fe614-118">ネットワーク ガイドラインで他の推奨事項します。</span><span class="sxs-lookup"><span data-stu-id="fe614-118">Following the other recommendations in our Networking guidelines:</span></span>
    
  - [<span data-ttu-id="fe614-119">メディアの品質と skype for Business Online のネットワーク接続パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="fe614-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="fe614-120">Skype for Business Online のネットワークを最適化します。</span><span class="sxs-lookup"><span data-stu-id="fe614-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="fe614-121">このガイドをフォローすると、潜在的な問題を最小化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe614-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="proxy-vendors-with-built-in-skype-for-business-support-or-configuration-options"></a><span data-ttu-id="fe614-122">組み込みの Skype for Business のサポートや設定のオプションのプロキシ仕入先</span><span class="sxs-lookup"><span data-stu-id="fe614-122">Proxy vendors with built-in Skype for Business support or configuration options</span></span>

<span data-ttu-id="fe614-123">このセクションには、製品やがビジネス トラフィック用 Skype で正常に動作する実証されているサービスを提供するプロキシ ベンダーに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fe614-123">This section will contain information about proxy vendors who provide products or services that are proven to work successfully with Skype for Business traffic.</span></span>
  
<span data-ttu-id="fe614-124">**Bluecoat プロキシ ソリューション**を使用して組織の場合、新しいファームウェアがリリースされましたいくつかの問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="fe614-124">For organizations using **Bluecoat Proxy solutions**, a new firmware has been released which addresses several issues with:</span></span>
    
  - <span data-ttu-id="fe614-125">SSL 傍受</span><span class="sxs-lookup"><span data-stu-id="fe614-125">SSL interception</span></span>
    
  - <span data-ttu-id="fe614-126">OCSP/SRL チェック</span><span class="sxs-lookup"><span data-stu-id="fe614-126">OCSP/SRL checks</span></span>
    
  - <span data-ttu-id="fe614-127">TLS 経由で SIP します。</span><span class="sxs-lookup"><span data-stu-id="fe614-127">SIP over TLS</span></span>
    
  - <span data-ttu-id="fe614-128">サポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fe614-128">support for TURN</span></span>
    
<span data-ttu-id="fe614-p104">Skype for Business の bluecoat のネイティブでサポート簡単にできる、関連するトラフィックを識別するためにできるようにし、適切に管理できます。最適な認証では、通知、これによりし、メディア トラフィック フローは、セキュリティ上の問題なく優れたユーザー エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="fe614-p104">Bluecoat's native support for Skype for Business can easily be enabled, allowing for the identification of relevant traffic, and managing it appropriately. This ensures optimal authentication, signaling, and media traffic flow, to provide a great user experience without security concerns.</span></span>
    
<span data-ttu-id="fe614-131">Bluecoat プロキシが、ネットワーク トポロジの一部である場合は、次のリンクを参照してください: https://support.symantec.com/en_US/article.DOC9757.html</span><span class="sxs-lookup"><span data-stu-id="fe614-131">Please refer to the following link if Bluecoat Proxy is a part of your network topology: https://support.symantec.com/en_US/article.DOC9757.html</span></span>

## <a name="related-topics"></a><span data-ttu-id="fe614-132">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fe614-132">Related topics</span></span>

[<span data-ttu-id="fe614-133">Skype for Business Online のネットワークを最適化します。</span><span class="sxs-lookup"><span data-stu-id="fe614-133">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)