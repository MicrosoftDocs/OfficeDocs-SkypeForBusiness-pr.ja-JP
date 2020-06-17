---
title: パイロット プールとレガシ プールの共存の確認
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: パイロットプールとレガシプールの共存を確認するプロセス。
ms.openlocfilehash: e9fe944c03c88aad2ca2b40f0e995842363e7a85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751659"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="f95d1-103">パイロット プールとレガシ プールの共存の確認</span><span class="sxs-lookup"><span data-stu-id="f95d1-103">Verify pilot pool coexistence with legacy pool</span></span>

 <span data-ttu-id="f95d1-104">**この記事の内容**</span><span class="sxs-lookup"><span data-stu-id="f95d1-104">**In this article**</span></span>
  
[<span data-ttu-id="f95d1-105">Skype for Business Server 2019 サービスが開始されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="f95d1-105">Verify that Skype for Business Server 2019 services have started</span></span>](#sectionSection0)
  
[<span data-ttu-id="f95d1-106">Skype for Business Server 2019 コントロールパネルを開く</span><span class="sxs-lookup"><span data-stu-id="f95d1-106">Open the Skype for Business Server 2019 Control Panel</span></span>](#sectionSection1)
  
[<span data-ttu-id="f95d1-107">従来のトポロジビルダーでトポロジを開かないようにします。</span><span class="sxs-lookup"><span data-stu-id="f95d1-107">Don't attempt to open the topology in the legacy Topology Builder</span></span>](#sectionSection2)
  
<span data-ttu-id="f95d1-108">パイロット プールを展開した後、プール情報を表示するための管理ツールを使用して、2 つのプールの共存を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f95d1-108">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="f95d1-109">Skype for Business Server 2019 プールおよび従来のプールの場合は、Skype for Business Server 2019 コントロールパネルおよびトポロジビルダーのツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f95d1-109">For the Skype for Business Server 2019 pools and legacy pools, you must use the Skype for Business Server 2019 Control Panel and Topology Builder tools.</span></span> 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a><span data-ttu-id="f95d1-110">Skype for Business Server 2019 サービスが開始されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="f95d1-110">Verify that Skype for Business Server 2019 services have started</span></span>
<span data-ttu-id="f95d1-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="f95d1-111"><a name="sectionSection0"> </a></span></span>

1. <span data-ttu-id="f95d1-112">Skype for Business Server 2019 フロントエンドサーバーから、管理ツール \ サービスアプレットに移動します。</span><span class="sxs-lookup"><span data-stu-id="f95d1-112">From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="f95d1-113">次のサービスがフロントエンド サーバーで実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f95d1-113">Verify that the following services are running on the Front End Server:</span></span>

    - <span data-ttu-id="f95d1-114">集中ログサービスエージェント</span><span class="sxs-lookup"><span data-stu-id="f95d1-114">Centralized Logging Service Agent</span></span>
    - <span data-ttu-id="f95d1-115">アプリケーション共有</span><span class="sxs-lookup"><span data-stu-id="f95d1-115">Application Sharing</span></span>
    - <span data-ttu-id="f95d1-116">オーディオテストサービス</span><span class="sxs-lookup"><span data-stu-id="f95d1-116">Audio Test Service</span></span>
    - <span data-ttu-id="f95d1-117">音声ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="f95d1-117">Audio/Video Conferencing</span></span>
    - <span data-ttu-id="f95d1-118">コール パーク</span><span class="sxs-lookup"><span data-stu-id="f95d1-118">Call Park</span></span>
    - <span data-ttu-id="f95d1-119">会議アナウンス</span><span class="sxs-lookup"><span data-stu-id="f95d1-119">Conferencing Announcement</span></span>
    - <span data-ttu-id="f95d1-120">会議アテンダント</span><span class="sxs-lookup"><span data-stu-id="f95d1-120">Conferencing Attendant</span></span>
    - <span data-ttu-id="f95d1-121">フロントエンド</span><span class="sxs-lookup"><span data-stu-id="f95d1-121">Front-End</span></span>
    - <span data-ttu-id="f95d1-122">IM 会議</span><span class="sxs-lookup"><span data-stu-id="f95d1-122">IM Conferencing</span></span>
    - <span data-ttu-id="f95d1-123">仲介</span><span class="sxs-lookup"><span data-stu-id="f95d1-123">Mediation</span></span>
    - <span data-ttu-id="f95d1-124">レプリカレプリケーターエージェント</span><span class="sxs-lookup"><span data-stu-id="f95d1-124">Replica Replicator Agent</span></span>
    - <span data-ttu-id="f95d1-125">応答グループ</span><span class="sxs-lookup"><span data-stu-id="f95d1-125">Response Group</span></span>
    - <span data-ttu-id="f95d1-126">Web 会議</span><span class="sxs-lookup"><span data-stu-id="f95d1-126">Web Conferencing</span></span>
    - <span data-ttu-id="f95d1-127">XMPP 変換ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="f95d1-127">XMPP Translating Gateway</span></span>

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a><span data-ttu-id="f95d1-128">Skype for Business Server 2019 コントロールパネルを開く</span><span class="sxs-lookup"><span data-stu-id="f95d1-128">Open the Skype for Business Server 2019 Control Panel</span></span>
<span data-ttu-id="f95d1-129"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="f95d1-129"><a name="sectionSection1"> </a></span></span>

<span data-ttu-id="f95d1-130">Skype for business Server 2019 展開のフロントエンドサーバーから、[Skype for Business Server 2019 コントロールパネル] を開き、従来のプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f95d1-130">From the Front End Server in your Skype for Business Server 2019 deployment, open the Skype for Business Server 2019 Control Panel and select the legacy pool.</span></span> <span data-ttu-id="f95d1-131">手順を繰り返して、Skype for Business Server 2019 プールを開きます。</span><span class="sxs-lookup"><span data-stu-id="f95d1-131">Repeat the procedure to open the Skype for Business Server 2019 pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f95d1-132">Skype for business Server 2019 では、Skype for Business Server コントロールパネルを使用する前に silverlight バージョン5にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f95d1-132">On Skype for Business Server 2019, you must upgrade Silverlight to Silverlight version 5 prior to using the Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="f95d1-133">このトポロジには、レガシおよび Skype for Business Server 2019 のサーバーの役割が含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f95d1-133">This topology now includes legacy and Skype for Business Server 2019 server roles.</span></span> 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a><span data-ttu-id="f95d1-134">従来のトポロジビルダーでトポロジを開かないようにします。</span><span class="sxs-lookup"><span data-stu-id="f95d1-134">Don't attempt to open the topology in the legacy Topology Builder</span></span>
<span data-ttu-id="f95d1-135"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="f95d1-135"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="f95d1-136">このトポロジは、Skype for Business Server 2019 トポロジビルダーを使用してのみ表示できます。</span><span class="sxs-lookup"><span data-stu-id="f95d1-136">The topology can only be viewed using Skype for Business Server 2019 Topology Builder.</span></span> <span data-ttu-id="f95d1-137">Skype for business server 2019 トポロジビルダーを使用して、Skype for business Server 2019 と従来のインストールの両方のプールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f95d1-137">The Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.</span></span>

  

