---
title: パイロット プールとレガシ プールの共存の確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: レガシ プールとの共存をパイロット プールを確認するプロセスです。
ms.openlocfilehash: ed3809bdde3109bdbd341c42eed0dc1d8cecd11f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875469"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="7ec04-103">パイロット プールとレガシ プールの共存の確認</span><span class="sxs-lookup"><span data-stu-id="7ec04-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="7ec04-104">**この資料に記載されて**</span><span class="sxs-lookup"><span data-stu-id="7ec04-104">**In this article**</span></span>
  
[<span data-ttu-id="7ec04-105">Skype サーバー 2019 のビジネスのサービスが開始されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7ec04-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="7ec04-106">ビジネス サーバー 2019 のコントロール パネルの Skype を開く</span><span class="sxs-lookup"><span data-stu-id="7ec04-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="7ec04-107">従来トポロジ ビルダーでトポロジを開くしようとしていません。</span><span class="sxs-lookup"><span data-stu-id="7ec04-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="7ec04-108">パイロット プールを展開した後は、プールの情報を表示するのには管理ツールを使用して 2 つのプールの共存を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ec04-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="7ec04-109">ビジネス サーバー 2019 のプールとプールの従来の Skype、ビジネス サーバー 2019 コントロール パネルの [トポロジ ビルダー ツールの Skype を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ec04-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="7ec04-110">Skype サーバー 2019 のビジネスのサービスが開始されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7ec04-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="7ec04-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="7ec04-111"></span></span>

1. <span data-ttu-id="7ec04-112">ビジネス 2019 フロント エンド サーバーの Skype、管理 Tools\Services のアプレットに移動します。</span><span class="sxs-lookup"><span data-stu-id="7ec04-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="7ec04-113">フロント エンド サーバー上で次のサービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7ec04-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="7ec04-114">サービス エージェントのログを一元管理</span><span class="sxs-lookup"><span data-stu-id="7ec04-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="7ec04-115">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="7ec04-115">Application Sharing</span></span>
    - <span data-ttu-id="7ec04-116">オーディオ テスト サービス</span><span class="sxs-lookup"><span data-stu-id="7ec04-116">Audio Test Service</span></span>
    - <span data-ttu-id="7ec04-117">オーディオ/ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="7ec04-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="7ec04-118">コール パーク</span><span class="sxs-lookup"><span data-stu-id="7ec04-118">Call Park</span></span>
    - <span data-ttu-id="7ec04-119">会議アナウンス</span><span class="sxs-lookup"><span data-stu-id="7ec04-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="7ec04-120">会議アテンダント</span><span class="sxs-lookup"><span data-stu-id="7ec04-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="7ec04-121">フロント エンド</span><span class="sxs-lookup"><span data-stu-id="7ec04-121">Front-End</span></span>
    - <span data-ttu-id="7ec04-122">IM 会議</span><span class="sxs-lookup"><span data-stu-id="7ec04-122">IM Conferencing</span></span>
    - <span data-ttu-id="7ec04-123">仲介</span><span class="sxs-lookup"><span data-stu-id="7ec04-123">Mediation</span></span>
    - <span data-ttu-id="7ec04-124">レプリカ レプリケーター エージェント</span><span class="sxs-lookup"><span data-stu-id="7ec04-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="7ec04-125">応答グループ</span><span class="sxs-lookup"><span data-stu-id="7ec04-125">Response Group</span></span>
    - <span data-ttu-id="7ec04-126">Web 会議</span><span class="sxs-lookup"><span data-stu-id="7ec04-126">Web Conferencing</span></span>
    - <span data-ttu-id="7ec04-127">XMPP 変換ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="7ec04-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="7ec04-128">ビジネス サーバー 2019 のコントロール パネルの Skype を開く</span><span class="sxs-lookup"><span data-stu-id="7ec04-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="7ec04-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="7ec04-129"></span></span>

<span data-ttu-id="7ec04-130">サーバー 2019 のビジネスを展開するため、Skype でフロント エンド サーバーから、Skype ビジネス サーバー 2019 のコントロール パネルの開き従来のプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ec04-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="7ec04-131">ビジネス サーバー 2019 プールの Skype を開く手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="7ec04-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7ec04-132">ビジネス サーバー 2019 の Skype は、上には、Silverlight ビジネス サーバーのコントロール パネルの Skype を使用する前にバージョン 5 に Silverlight をアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="7ec04-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="7ec04-133">このトポロジには、従来と Skype ビジネス サーバー 2019 サーバーの役割です。</span><span class="sxs-lookup"><span data-stu-id="7ec04-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="7ec04-134">従来トポロジ ビルダーでトポロジを開くしようとしていません。</span><span class="sxs-lookup"><span data-stu-id="7ec04-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="7ec04-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="7ec04-135"></span></span>

<span data-ttu-id="7ec04-136">従来トポロジ ビルダーを使用してトポロジを表示しようとすると、次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="7ec04-136">If you attempt to open the topology using the legacy Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="7ec04-137">ビジネス サーバー 2019 のトポロジ ビルダーの Skype を使用してトポロジを表示のみできます。</span><span class="sxs-lookup"><span data-stu-id="7ec04-137">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="7ec04-138">ビジネス サーバー 2019 の Skype と従来のインストールの両方のプールを作成するには、ビジネス サーバー 2019 のトポロジ ビルダーの Skype を使用しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="7ec04-138">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

