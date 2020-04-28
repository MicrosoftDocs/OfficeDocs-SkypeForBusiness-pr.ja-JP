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
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: この記事では、Microsoft Teams または Skype for Business でのプロキシサーバーの使用に関する情報を提供します。
ms.openlocfilehash: 5a0d35ee2b8c95c4dea30886497e184f57077264
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905679"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="5590d-103">Teams または Skype for Business Online 向けのプロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="5590d-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="5590d-104">この記事では、Teams または Skype for Business でのプロキシサーバーの使用に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="5590d-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="5590d-105">プロキシ サーバーの使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="5590d-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="5590d-106">プロキシ経由の Teams または Skype for Business トラフィックについては、プロキシをバイパスすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5590d-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="5590d-107">プロキシは、トラフィックが既に暗号化されているため、チームまたは Skype for Business の安全性を高めません。</span><span class="sxs-lookup"><span data-stu-id="5590d-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="5590d-108">また、プロキシを使用すると問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5590d-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="5590d-109">パフォーマンスに関連する問題は、待ち時間とパケット損失によって環境に導入される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5590d-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="5590d-110">このような問題が発生した場合、そのようなチームまたは Skype for Business のシナリオでは、リアルタイムのストリームが不可欠であるため、オーディオとビデオとして、否定的な経験が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5590d-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="5590d-111">プロキシ サーバーを使用する必要がある場合</span><span class="sxs-lookup"><span data-stu-id="5590d-111">If you need to use a proxy server</span></span>

<span data-ttu-id="5590d-112">組織によっては、Teams または Skype for Business のトラフィックに対してプロキシをバイパスするオプションがありません。</span><span class="sxs-lookup"><span data-stu-id="5590d-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="5590d-113">そのような場合は、上記の問題について注意しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="5590d-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="5590d-114">Microsoft は次を実行することもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5590d-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="5590d-115">外部の DNS 解決を使用する</span><span class="sxs-lookup"><span data-stu-id="5590d-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="5590d-116">ダイレクト UDP ベースのルーティングを使用する</span><span class="sxs-lookup"><span data-stu-id="5590d-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="5590d-117">UDP トラフィックを許可する</span><span class="sxs-lookup"><span data-stu-id="5590d-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="5590d-118">ネットワークガイドラインのその他の推奨事項に従う: [Teams 用に組織のネットワークを準備](prepare-network.md)する</span><span class="sxs-lookup"><span data-stu-id="5590d-118">Following the other recommendations in our networking guidelines: [Prepare your organization's network for Teams](prepare-network.md)</span></span>
  
    
<span data-ttu-id="5590d-119">このガイダンスに従うことで、問題が生じる可能性が最小になります。</span><span class="sxs-lookup"><span data-stu-id="5590d-119">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5590d-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="5590d-120">Related topics</span></span>

[<span data-ttu-id="5590d-121">Office 365 のネットワーク接続の原則</span><span class="sxs-lookup"><span data-stu-id="5590d-121">Office 365 Network Connectivity Principles</span></span>](https://aka.ms/pnc)

[<span data-ttu-id="5590d-122">Teams 用に組織のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="5590d-122">Prepare your organization's network for Teams</span></span>](prepare-network.md)
