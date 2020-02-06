---
title: 従来の環境を確認する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server 2019 を共存状態で展開する前に、従来のサービスが構成されて開始されていることを確認する必要があります。 Skype for Business Server 2019 パイロットプールを展開する前に、従来の環境に存在する主要サービスと機能を特定することが重要です。 従来の XMPP 展開を使用して、Microsoft Skype for Business Server 2019 XMPP を共存状態で展開する前に、以前の XMPP サービスが構成されて開始されていることを確認し、レガシ XMPP 構成のフェデレーションパートナーを特定する必要があります。サポート.
ms.openlocfilehash: 34c9ecbc4fe9863c09b2648145ff46c1628ef655
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812695"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="7adb5-105">従来の環境を確認する</span><span class="sxs-lookup"><span data-stu-id="7adb5-105">Verify the legacy environment</span></span>

<span data-ttu-id="7adb5-106">Skype for Business Server 2019 を共存状態で展開する前に、従来のサービスが構成されて開始されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7adb5-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="7adb5-107">Skype for Business Server 2019 パイロットプールを展開する前に、従来の環境に存在する主要なサービスと機能を特定することが重要です。</span><span class="sxs-lookup"><span data-stu-id="7adb5-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="7adb5-108">従来の XMPP 展開を使用して、Microsoft Skype for Business Server 2019 XMPP を共存状態で展開する前に、従来の XMPP サービスが構成されて開始されていることを確認し、レガシ XMPP のフェデレーションパートナーを特定する必要があります。構成がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7adb5-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="7adb5-109">従来の展開を確認することには、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="7adb5-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="7adb5-110">従来のサービスが開始されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="7adb5-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="7adb5-111">トポロジとユーザーの確認</span><span class="sxs-lookup"><span data-stu-id="7adb5-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="7adb5-112">フェデレーションとエッジサーバーの設定を確認する</span><span class="sxs-lookup"><span data-stu-id="7adb5-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="7adb5-113">XMPP サービスおよびフェデレーションパートナーを確認する</span><span class="sxs-lookup"><span data-stu-id="7adb5-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="7adb5-114">従来のサービスが開始されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="7adb5-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="7adb5-115">従来のフロントエンドサーバーから、[管理] の [サービス] アプレットに移動します。</span><span class="sxs-lookup"><span data-stu-id="7adb5-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="7adb5-116">フロントエンドサーバーで次のサービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7adb5-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![フロントエンドサーバーで実行されているサービスの一覧](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="7adb5-118">Skype for Business Server コントロールパネルで従来のトポロジを確認する</span><span class="sxs-lookup"><span data-stu-id="7adb5-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="7adb5-119">RTCUniversalServerAdmins グループ、CsAdministrator 管理者ロール、または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="7adb5-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="7adb5-120">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7adb5-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="7adb5-121">[**トポロジ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="7adb5-121">Select **Topology**.</span></span> <span data-ttu-id="7adb5-122">レガシ展開のさまざまなサーバーが一覧に表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7adb5-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![コントロールパネルのトポロジーページ](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="7adb5-124">Skype for Business Server コントロールパネルで従来のユーザーを確認する</span><span class="sxs-lookup"><span data-stu-id="7adb5-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="7adb5-125">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7adb5-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="7adb5-126">[**ユーザー**] を選択し、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7adb5-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="7adb5-127">**レジストラー pool**列が、表示されている各ユーザーのレガシープールをポイントしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7adb5-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![コントロールパネルのユーザの一覧](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="7adb5-129">従来のエッジとフェデレーションの設定を確認する</span><span class="sxs-lookup"><span data-stu-id="7adb5-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="7adb5-130">トポロジビルダーを起動します。</span><span class="sxs-lookup"><span data-stu-id="7adb5-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="7adb5-131">[**既存の展開からトポロジをダウンロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7adb5-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="7adb5-132">ファイル名を選択し、tbxml ファイルの種類が設定されたトポロジを保存します。</span><span class="sxs-lookup"><span data-stu-id="7adb5-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="7adb5-133">展開内のさまざまなサーバーの役割を表示するために、[従来のインストール] ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="7adb5-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="7adb5-134">サイトノードを選択し、[**サイトフェデレーションルートの割り当て**] の値が設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7adb5-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![トポロジビルダー、サイトフェデレーションルート](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="7adb5-136">Standard Edition Server または Enterprise Edition のフロントエンドプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="7adb5-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="7adb5-137">**アソシエーション**の下にあるメディアにエッジプールが構成されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7adb5-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![サーバーとプールを表示するトポロジビルダー](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="7adb5-139">エッジプールを選択して、次ホッププールが**次ホップの選択**の下に構成されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7adb5-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![トポロジビルダー、次ホップの選択](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="7adb5-141">従来の XMPP フェデレーションパートナーの構成を確認する</span><span class="sxs-lookup"><span data-stu-id="7adb5-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="7adb5-142">従来の XMPP サーバーから、[管理] の [サービス] アプレットに移動します。</span><span class="sxs-lookup"><span data-stu-id="7adb5-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="7adb5-143">Office Communications Server XMPP ゲートウェイサービスが開始されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7adb5-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Office Communications Server XMPP ゲートウェイサービス](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

