---
title: 従来の環境を確認する
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
description: Skype for Business Server 2019 を共存状態で展開する前に、従来のサービスが構成され、起動していることを確認する必要があります。 Skype for Business Server 2019 パイロットプールを展開する前に、従来の環境に存在する主要なサービスと機能を特定することが重要です。 従来の XMPP 展開を使用して、Microsoft Skype for Business Server 2019 XMPP を共存状態に展開する前に、従来の XMPP サービスが構成されて起動していることを確認し、従来の XMPP 構成がサポートしているフェデレーションパートナーを特定する必要があります。
ms.openlocfilehash: 2600cc2e6f4fac258431bcf505af10d1f8c212fe
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751679"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="ea2b1-105">従来の環境を確認する</span><span class="sxs-lookup"><span data-stu-id="ea2b1-105">Verify the legacy environment</span></span>

<span data-ttu-id="ea2b1-106">Skype for Business Server 2019 を共存状態で展開する前に、従来のサービスが構成され、起動していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="ea2b1-107">Skype for Business Server 2019 パイロットプールを展開する前に、従来の環境に存在する主要なサービスと機能を特定することが重要です。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="ea2b1-108">レガシ XMPP 展開を使用して、Microsoft Skype for Business Server 2019 XMPP を共存状態に展開する前に、従来の xmpp サービスが構成および開始されていることを確認し、従来の XMPP 構成がサポートしているフェデレーションパートナーを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="ea2b1-109">従来の展開を確認するには、次のことが伴います。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="ea2b1-110">従来のサービスが開始されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="ea2b1-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="ea2b1-111">トポロジとユーザーの確認</span><span class="sxs-lookup"><span data-stu-id="ea2b1-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="ea2b1-112">フェデレーションとエッジサーバーの設定の確認</span><span class="sxs-lookup"><span data-stu-id="ea2b1-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="ea2b1-113">XMPP サービスとフェデレーションパートナーを確認する</span><span class="sxs-lookup"><span data-stu-id="ea2b1-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="ea2b1-114">従来のサービスが開始されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="ea2b1-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="ea2b1-115">従来のフロントエンドサーバーから、管理ツール \ サービスアプレットに移動します。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="ea2b1-116">次のサービスがフロントエンド サーバーで実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![フロントエンドサーバーで実行されているサービスの一覧](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="ea2b1-118">Skype for Business Server コントロールパネルで従来のトポロジを確認する</span><span class="sxs-lookup"><span data-stu-id="ea2b1-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ea2b1-119">RTCUniversalServerAdmins グループのメンバーであるか、CsAdministrator または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="ea2b1-120">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ea2b1-121">[**トポロジ**] クリックします。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-121">Select **Topology**.</span></span> <span data-ttu-id="ea2b1-122">従来の展開に含まれるさまざまなサーバーが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![コントロールパネルのトポロジページ](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="ea2b1-124">Skype for Business Server コントロールパネルで従来のユーザーを確認する</span><span class="sxs-lookup"><span data-stu-id="ea2b1-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ea2b1-125">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="ea2b1-126">[**ユーザー**] を選択し、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="ea2b1-127">[**レジストラープール**] 列が、表示されている各ユーザーのレガシプールを指していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![ユーザーを一覧表示するコントロールパネル](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="ea2b1-129">従来のエッジとフェデレーションの設定を確認する</span><span class="sxs-lookup"><span data-stu-id="ea2b1-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="ea2b1-130">トポロジ ビルダーを開始します。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="ea2b1-131">[**既存の展開からトポロジをダウンロードする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="ea2b1-132">ファイル名を選択し、redmond.tbxml ファイルの種類が既定のトポロジを保存します。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="ea2b1-133">[従来のインストール] ノードを展開して、展開に含まれるさまざまなサーバーの役割を確認します。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="ea2b1-134">サイトノードを選択し、[**サイトのフェデレーションルートの割り当て**] の値が設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![トポロジビルダー、サイトのフェデレーションルート](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="ea2b1-136">Standard Edition サーバーまたは Enterprise Edition フロントエンドプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="ea2b1-137">エッジプールが、 **association**の下にあるメディアに対して構成されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![トポロジビルダー、サーバーとプールが表示されている](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="ea2b1-139">エッジプールを選択し、次ホッププールを次**ホップの選択範囲**より下に構成するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![トポロジビルダー、次ホップの選択](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="ea2b1-141">レガシ XMPP フェデレーションパートナーの構成を確認する</span><span class="sxs-lookup"><span data-stu-id="ea2b1-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="ea2b1-142">レガシ XMPP サーバから、管理ツール\サービス アプレットに移動します。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="ea2b1-143">Office Communications Server XMPP Gateway サービスが開始されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea2b1-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Office Communications Server XMPP ゲートウェイサービス](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

