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
search.appverid: MET150
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
ms.openlocfilehash: 3d83e2f6d4eb2b88a52eb949217ac2f00c72acff
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850015"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="c0d98-103">Skype for Business Online 向けのプロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="c0d98-103">Proxy Servers for Skype for Business Online</span></span>

<span data-ttu-id="c0d98-104">[] この記事は、Skype for Business でのプロキシ サーバーの使用に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c0d98-104">This article will help you with guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="c0d98-105">プロキシ サーバーの使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="c0d98-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="c0d98-p101">プロキシ経由の Skype for Business トラフィックについては、Microsoft はプロキシをバイパスすることをお勧めします。トラフィックは既に暗号化されているため、プロキシによって Skype for Business のセキュリティがさらに強くなることはありません。</span><span class="sxs-lookup"><span data-stu-id="c0d98-p101">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Skype for Business more secure because its traffic is already encrypted.</span></span>
  
<span data-ttu-id="c0d98-p102">パフォーマンスに関連する問題が、遅延時間とパケット損失によって環境に生じる可能性があります。このような問題は、Skype for Business 使用時の音声やビデオにおけるエクスペリエンスの低下につながります。</span><span class="sxs-lookup"><span data-stu-id="c0d98-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="c0d98-111">プロキシ サーバーを使用する必要がある場合</span><span class="sxs-lookup"><span data-stu-id="c0d98-111">If you need to use a proxy server</span></span>

<span data-ttu-id="c0d98-p103">組織によっては、Skype for Business トラフィックのプロキシをバイパスするオプションがありません。そのような場合は、上記の問題について注意しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0d98-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="c0d98-114">Microsoft は次を実行することもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c0d98-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="c0d98-115">外部の DNS 解決を使用する</span><span class="sxs-lookup"><span data-stu-id="c0d98-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="c0d98-116">ダイレクト UDP ベースのルーティングを使用する</span><span class="sxs-lookup"><span data-stu-id="c0d98-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="c0d98-117">UDP トラフィックを許可する</span><span class="sxs-lookup"><span data-stu-id="c0d98-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="c0d98-118">次のネットワーキング ガイドラインのその他の推奨事項に従う</span><span class="sxs-lookup"><span data-stu-id="c0d98-118">Following the other recommendations in our Networking guidelines:</span></span>
    
  - [<span data-ttu-id="c0d98-119">Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="c0d98-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="c0d98-120">Skype for Business Online 向けのネットワークの最適化</span><span class="sxs-lookup"><span data-stu-id="c0d98-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="c0d98-121">このガイダンスに従うことで、問題が生じる可能性が最小になります。</span><span class="sxs-lookup"><span data-stu-id="c0d98-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c0d98-122">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="c0d98-122">Related topics</span></span>

[<span data-ttu-id="c0d98-123">Skype for Business Online 向けのネットワークの最適化</span><span class="sxs-lookup"><span data-stu-id="c0d98-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 