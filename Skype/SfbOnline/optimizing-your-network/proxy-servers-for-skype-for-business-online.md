---
title: Skype for Business Online 向けのプロキシ サーバー
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
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
description: この記事は、Skype for Business でのプロキシ サーバーの使用に関するガイダンスを提供します。
ms.openlocfilehash: a4369208ab277e0eb5490a637421de605235a0cd
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2018
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="d17a1-103">Skype for Business Online 向けのプロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="d17a1-103">Proxy Servers for Skype for Business Online</span></span>

<span data-ttu-id="d17a1-104">[] この記事は、Skype for Business でのプロキシ サーバーの使用に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d17a1-104">This article will help you with guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="d17a1-105">プロキシ サーバーの使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="d17a1-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="d17a1-p101">プロキシ経由の Skype for Business トラフィックについては、Microsoft はプロキシをバイパスすることをお勧めします。トラフィックは既に暗号化されているため、プロキシによって Skype for Business のセキュリティがさらに強くなることはありません。</span><span class="sxs-lookup"><span data-stu-id="d17a1-p101">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Skype for Business more secure because its traffic is already encrypted.</span></span>
  
<span data-ttu-id="d17a1-p102">パフォーマンスに関連する問題が、遅延時間とパケット損失によって環境に生じる可能性があります。このような問題は、Skype for Business 使用時の音声やビデオにおけるエクスペリエンスの低下につながります。</span><span class="sxs-lookup"><span data-stu-id="d17a1-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="d17a1-111">プロキシ サーバーを使用する必要がある場合</span><span class="sxs-lookup"><span data-stu-id="d17a1-111">If you need to use a proxy server</span></span>

<span data-ttu-id="d17a1-p103">組織によっては、Skype for Business トラフィックのプロキシをバイパスするオプションがありません。そのような場合は、上記の問題について注意しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="d17a1-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="d17a1-114">Microsoft は次を実行することもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d17a1-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="d17a1-115">外部の DNS 解決を使用する</span><span class="sxs-lookup"><span data-stu-id="d17a1-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="d17a1-116">ダイレクト UDP ベースのルーティングを使用する</span><span class="sxs-lookup"><span data-stu-id="d17a1-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="d17a1-117">UDP トラフィックを許可する</span><span class="sxs-lookup"><span data-stu-id="d17a1-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="d17a1-118">次のネットワーキング ガイドラインのその他の推奨事項に従う</span><span class="sxs-lookup"><span data-stu-id="d17a1-118">Following the other recommendations in our Networking guidelines:</span></span>
    
  - [<span data-ttu-id="d17a1-119">Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="d17a1-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="d17a1-120">Skype for Business Online 向けのネットワークの最適化</span><span class="sxs-lookup"><span data-stu-id="d17a1-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="d17a1-121">このガイダンスに従うことで、問題が生じる可能性が最小になります。</span><span class="sxs-lookup"><span data-stu-id="d17a1-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="proxy-vendors-with-built-in-skype-for-business-support-or-configuration-options"></a><span data-ttu-id="d17a1-122">組み込みの Skype for Business サポートまたは構成オプションを備えたプロキシ ベンダー</span><span class="sxs-lookup"><span data-stu-id="d17a1-122">Proxy vendors with built-in Skype for Business support or configuration options</span></span>

<span data-ttu-id="d17a1-123">このセクションは、Skype for Business トラフィックに対して正常に機能することが証明されている製品またはサービスを提供するプロキシ ベンダーについての情報を示します。</span><span class="sxs-lookup"><span data-stu-id="d17a1-123">This section will contain information about proxy vendors who provide products or services that are proven to work successfully with Skype for Business traffic.</span></span>
  
<span data-ttu-id="d17a1-124">**Blue Coat プロキシ ソリューション** を使用する組織に対しては、次の複数の問題に対処する新しいファームウェアがリリースされています。</span><span class="sxs-lookup"><span data-stu-id="d17a1-124">For organizations using **Bluecoat Proxy solutions**, a new firmware has been released which addresses several issues with:</span></span>
    
  - <span data-ttu-id="d17a1-125">SSL 傍受</span><span class="sxs-lookup"><span data-stu-id="d17a1-125">SSL interception</span></span>
    
  - <span data-ttu-id="d17a1-126">OCSP/SRL チェック</span><span class="sxs-lookup"><span data-stu-id="d17a1-126">OCSP/SRL checks</span></span>
    
  - <span data-ttu-id="d17a1-127">TLS 経由の SIP</span><span class="sxs-lookup"><span data-stu-id="d17a1-127">SIP over TLS</span></span>
    
  - <span data-ttu-id="d17a1-128">TURN に対するサポート</span><span class="sxs-lookup"><span data-stu-id="d17a1-128">support for TURN</span></span>
    
<span data-ttu-id="d17a1-p104">Skype for Business に対する Blue Coat のネイティブ サポートは簡単に有効にすることができ、関連トラフィックの識別と、適切な管理が実現します。これにより最適な認証、シグナリング、メディア トラフィック フローを確実に行えるようになり、セキュリティ上の心配がない優れたユーザー エクスペリエンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="d17a1-p104">Bluecoat's native support for Skype for Business can easily be enabled, allowing for the identification of relevant traffic, and managing it appropriately. This ensures optimal authentication, signaling, and media traffic flow, to provide a great user experience without security concerns.</span></span>
    
<span data-ttu-id="d17a1-131">Bluecoat のプロキシが、ネットワーク トポロジの一部である場合は、次のリンクを参照してください。https://support.symantec.com/en_US/article.DOC9757.html</span><span class="sxs-lookup"><span data-stu-id="d17a1-131">Please refer to the following link if Bluecoat Proxy is a part of your network topology: https://support.symantec.com/en_US/article.DOC9757.html</span></span>

## <a name="related-topics"></a><span data-ttu-id="d17a1-132">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="d17a1-132">Related topics</span></span>

[<span data-ttu-id="d17a1-133">Skype for Business Online 向けのネットワークの最適化</span><span class="sxs-lookup"><span data-stu-id="d17a1-133">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 