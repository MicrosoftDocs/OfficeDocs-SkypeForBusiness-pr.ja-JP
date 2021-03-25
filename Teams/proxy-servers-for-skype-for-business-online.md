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
description: この記事では、Microsoft Teams または Skype for Business でプロキシ サーバーを使用する方法について説明します。
ms.openlocfilehash: 0e2089cfa327a610c3ee98f1f20862a28939fd0c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117725"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="54ab7-103">Teams または Skype for Business Online 向けのプロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="54ab7-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="54ab7-104">この記事では、Teams または Skype for Business でプロキシ サーバーを使用する方法について、ガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="54ab7-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="54ab7-105">プロキシ サーバーの使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="54ab7-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="54ab7-106">プロキシ経由の Teams または Skype for Business トラフィックの場合、Microsoft はプロキシをバイパスする方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="54ab7-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="54ab7-107">トラフィックは既に暗号化されているので、プロキシによって Teams または Skype for Business のセキュリティが高くなされません。</span><span class="sxs-lookup"><span data-stu-id="54ab7-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="54ab7-108">プロキシを使用すると、問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="54ab7-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="54ab7-109">パフォーマンス関連の問題は、待機時間とパケット損失によって環境に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="54ab7-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="54ab7-110">このような問題は、リアルタイム ストリームが不可欠な音声やビデオなどの Teams や Skype for Business のシナリオで負のエクスペリエンスを生み出します。</span><span class="sxs-lookup"><span data-stu-id="54ab7-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="54ab7-111">プロキシ サーバーを使用する必要がある場合</span><span class="sxs-lookup"><span data-stu-id="54ab7-111">If you need to use a proxy server</span></span>

<span data-ttu-id="54ab7-112">組織によっては、Teams または Skype for Business トラフィックのプロキシをバイパスするオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="54ab7-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="54ab7-113">そのような場合は、上記の問題について注意しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="54ab7-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="54ab7-114">Microsoft は次を実行することもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="54ab7-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="54ab7-115">外部の DNS 解決を使用する</span><span class="sxs-lookup"><span data-stu-id="54ab7-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="54ab7-116">ダイレクト UDP ベースのルーティングを使用する</span><span class="sxs-lookup"><span data-stu-id="54ab7-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="54ab7-117">UDP トラフィックを許可する</span><span class="sxs-lookup"><span data-stu-id="54ab7-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="54ab7-118">ネットワーク ガイドラインのその他の推奨事項に従う: 組織のネットワーク [を Teams 用に準備する](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="54ab7-118">Following the other recommendations in our networking guidelines: [Prepare your organization's network for Teams](prepare-network.md)</span></span>
  
    
<span data-ttu-id="54ab7-119">このガイダンスに従うことで、問題が生じる可能性が最小になります。</span><span class="sxs-lookup"><span data-stu-id="54ab7-119">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="54ab7-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="54ab7-120">Related topics</span></span>

[<span data-ttu-id="54ab7-121">Microsoft 365 および Office 365 ネットワーク接続の原則</span><span class="sxs-lookup"><span data-stu-id="54ab7-121">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="54ab7-122">Teams 用に組織のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="54ab7-122">Prepare your organization's network for Teams</span></span>](prepare-network.md)