---
title: パイロット プールとレガシ プールの共存の確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 従来のプールとの間でパイロットプールを共存させるプロセス。
ms.openlocfilehash: b41a1f24786fdf807f9c9c1d5854e397654fdadb
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2019
ms.locfileid: "35758905"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="69d10-103">パイロット プールとレガシ プールの共存の確認</span><span class="sxs-lookup"><span data-stu-id="69d10-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="69d10-104">**この記事の内容**</span><span class="sxs-lookup"><span data-stu-id="69d10-104">**In this article**</span></span>
  
[<span data-ttu-id="69d10-105">Skype for Business Server 2019 サービスが開始されたことを確認する</span><span class="sxs-lookup"><span data-stu-id="69d10-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="69d10-106">Skype for Business Server 2019 コントロールパネルを開く</span><span class="sxs-lookup"><span data-stu-id="69d10-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="69d10-107">従来のトポロジビルダーでトポロジを開かないようにします。</span><span class="sxs-lookup"><span data-stu-id="69d10-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="69d10-108">パイロットプールを展開した後、管理ツールを使用してプール情報を表示し、2つのプールの共存を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d10-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="69d10-109">Skype for Business Server 2019 プールおよび従来のプールの場合は、Skype for Business Server 2019 コントロールパネルツールとトポロジビルダーツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d10-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="69d10-110">Skype for Business Server 2019 サービスが開始されたことを確認する</span><span class="sxs-lookup"><span data-stu-id="69d10-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="69d10-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="69d10-111"></span></span>

1. <span data-ttu-id="69d10-112">Skype for Business Server 2019 フロントエンドサーバーから、管理用の [サービス] アプレットに移動します。</span><span class="sxs-lookup"><span data-stu-id="69d10-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="69d10-113">フロントエンドサーバーで次のサービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="69d10-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="69d10-114">一元ログサービスエージェント</span><span class="sxs-lookup"><span data-stu-id="69d10-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="69d10-115">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="69d10-115">Application Sharing</span></span>
    - <span data-ttu-id="69d10-116">オーディオテストサービス</span><span class="sxs-lookup"><span data-stu-id="69d10-116">Audio Test Service</span></span>
    - <span data-ttu-id="69d10-117">音声/ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="69d10-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="69d10-118">コール パーク</span><span class="sxs-lookup"><span data-stu-id="69d10-118">Call Park</span></span>
    - <span data-ttu-id="69d10-119">会議アナウンス</span><span class="sxs-lookup"><span data-stu-id="69d10-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="69d10-120">会議の応答</span><span class="sxs-lookup"><span data-stu-id="69d10-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="69d10-121">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="69d10-121">Front-End</span></span>
    - <span data-ttu-id="69d10-122">IM 会議</span><span class="sxs-lookup"><span data-stu-id="69d10-122">IM Conferencing</span></span>
    - <span data-ttu-id="69d10-123">仲介</span><span class="sxs-lookup"><span data-stu-id="69d10-123">Mediation</span></span>
    - <span data-ttu-id="69d10-124">レプリカレプリケーターエージェント</span><span class="sxs-lookup"><span data-stu-id="69d10-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="69d10-125">応答グループ</span><span class="sxs-lookup"><span data-stu-id="69d10-125">Response Group</span></span>
    - <span data-ttu-id="69d10-126">Web 会議</span><span class="sxs-lookup"><span data-stu-id="69d10-126">Web Conferencing</span></span>
    - <span data-ttu-id="69d10-127">XMPP の変換ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="69d10-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="69d10-128">Skype for Business Server 2019 コントロールパネルを開く</span><span class="sxs-lookup"><span data-stu-id="69d10-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="69d10-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="69d10-129"></span></span>

<span data-ttu-id="69d10-130">Skype for Business Server 2019 展開のフロントエンドサーバーから、[Skype for Business Server 2019 コントロールパネル] を開いて、従来のプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="69d10-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="69d10-131">手順を繰り返して、Skype for Business Server 2019 プールを開きます。</span><span class="sxs-lookup"><span data-stu-id="69d10-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="69d10-132">Skype for Business Server 2019 で、Skype for Business Server コントロールパネルを使用する前に、Silverlight を Silverlight バージョン5にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d10-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="69d10-133">このトポロジには、レガシーおよび Skype for Business Server 2019 サーバーの役割が含まれています。</span><span class="sxs-lookup"><span data-stu-id="69d10-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="69d10-134">従来のトポロジビルダーでトポロジを開かないようにします。</span><span class="sxs-lookup"><span data-stu-id="69d10-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="69d10-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="69d10-135"></span></span>

<span data-ttu-id="69d10-136">このトポロジを表示するには、Skype for Business Server 2019 Topology Builder を使用します。</span><span class="sxs-lookup"><span data-stu-id="69d10-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="69d10-137">Skype for business server 2019 トポロジビルダーを使用して、Skype for Business Server 2019 と従来のインストールの両方のプールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d10-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

