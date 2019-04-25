---
title: レガシー環境を確認します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 共存状態でのビジネス サーバー 2019 の Skype を導入する前に従来のサービスを構成および開始されたことを確認する必要があります。 重要なサービスと、Skype のビジネス サーバー 2019 パイロット プールを展開する前に、従来の環境に存在する機能を特定するのには重要です。 Microsoft Skype を展開する、従来の XMPP 展開との共存状態でのビジネス サーバー 2019 XMPP の前に従来の XMPP サービスを構成および開始を確認し、XMPP の従来の構成は、どちらのフェデレーション パートナーを識別する必要があります。サポートします。
ms.openlocfilehash: 0f9812efe966d72eba1eeead9d74780f2ba16661
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235115"
---
# <a name="verify-the-legacy-environment"></a><span data-ttu-id="59b73-105">レガシー環境を確認します。</span><span class="sxs-lookup"><span data-stu-id="59b73-105">Verify the legacy environment</span></span>

<span data-ttu-id="59b73-106">共存状態でのビジネス サーバー 2019 の Skype を導入する前に従来のサービスを構成および開始されたことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59b73-106">Before deploying Skype for Business Server 2019 in a coexistence state, you need to verify that legacy services have been configured and started.</span></span> <span data-ttu-id="59b73-107">重要なサービスと、Skype のビジネス サーバー 2019 パイロット プールを展開する前に、従来の環境に存在する機能を特定するのには重要です。</span><span class="sxs-lookup"><span data-stu-id="59b73-107">It is important to identify key services and features that exist in your legacy environment prior to deploying a Skype for Business Server 2019 pilot pool.</span></span> <span data-ttu-id="59b73-108">Microsoft Skype を展開する、従来の XMPP 展開との共存状態でのビジネス サーバー 2019 XMPP の前に従来の XMPP サービスを構成および開始することを確認し、フェデレーション パートナーの従来の XMPP の先を識別する必要があります。構成をサポートします。</span><span class="sxs-lookup"><span data-stu-id="59b73-108">Before deploying Microsoft Skype for Business Server 2019 XMPP in a coexistence state with a legacy XMPP deployment, you need to verify that the legacy XMPP services have been configured and started, and identify which federated partner the legacy XMPP configuration is supporting.</span></span> <span data-ttu-id="59b73-109">以下が必要です、従来の展開を確認します。</span><span class="sxs-lookup"><span data-stu-id="59b73-109">Verifying your legacy deployment entails the following:</span></span>
  
- <span data-ttu-id="59b73-110">従来のサービスが開始されているを確認します。</span><span class="sxs-lookup"><span data-stu-id="59b73-110">Verifying that the legacy services are started</span></span>
    
- <span data-ttu-id="59b73-111">トポロジとユーザーを確認します。</span><span class="sxs-lookup"><span data-stu-id="59b73-111">Reviewing the topology and users</span></span>
    
- <span data-ttu-id="59b73-112">フェデレーションおよびエッジ サーバーの設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="59b73-112">Verifying the federation and Edge server settings</span></span>
    
- <span data-ttu-id="59b73-113">XMPP サービスとフェデレーション パートナーの確認</span><span class="sxs-lookup"><span data-stu-id="59b73-113">Verifying XMPP services and federated partners</span></span>
    
## <a name="verify-that-legacy-services-are-started"></a><span data-ttu-id="59b73-114">従来のサービスが開始されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="59b73-114">Verify that legacy services are started</span></span>

1. <span data-ttu-id="59b73-115">従来のフロント エンド サーバー、管理 Tools\Services のアプレットに移動します。</span><span class="sxs-lookup"><span data-stu-id="59b73-115">From the legacy Front End Server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="59b73-116">フロント エンド サーバー上で次のサービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="59b73-116">Verify that the following services are running on the Front End Server:</span></span>
    
     ![フロント エンド サーバーで実行されているサービスの一覧](../media/migration_lyncserver_config_w14_services.jpg)
  
## <a name="review-the-legacy-topology-in-skype-for-business-server-control-panel"></a><span data-ttu-id="59b73-118">ビジネス サーバーのコントロール パネルの Skype で従来のトポロジを確認します。</span><span class="sxs-lookup"><span data-stu-id="59b73-118">Review the legacy topology in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="59b73-119">RTCUniversalServerAdmins グループ、CsAdministrator 管理者ロール、または CsUserAdministrator 管理者ロールのメンバーであるアカウントを使用して、フロントエンド サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="59b73-119">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="59b73-120">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="59b73-120">Open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="59b73-121">**トポロジ**を選択します。</span><span class="sxs-lookup"><span data-stu-id="59b73-121">Select **Topology**.</span></span> <span data-ttu-id="59b73-122">従来配置内のさまざまなサーバーの一覧が表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="59b73-122">Verify that the various servers in your legacy deployment are listed.</span></span>
    
     ![コントロール パネルのトポロジのページ](../media/migration_lyncserver_2010_topology.JPG)
  
## <a name="review-legacy-users-in-skype-for-business-server-control-panel"></a><span data-ttu-id="59b73-124">ビジネス サーバーのコントロール パネルの Skype で従来のユーザーを確認します。</span><span class="sxs-lookup"><span data-stu-id="59b73-124">Review legacy users in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="59b73-125">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="59b73-125">Open the Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="59b73-126">**ユーザー**を選択し、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59b73-126">Select **Users**, and then click **Find**.</span></span>
    
3. <span data-ttu-id="59b73-127">**レジストラー プール**] 列が表示されている各ユーザーの従来のプールを指していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="59b73-127">Verify that the **Registrar Pool** column points to the legacy pool for each user listed.</span></span> 
    
     ![コントロール パネルのユーザーを一覧表示](../media/migration_lyncserver_2010_allusers.JPG)
  
## <a name="verify-legacy-edge-and-federation-settings"></a><span data-ttu-id="59b73-129">従来のエッジとフェデレーションの設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="59b73-129">Verify legacy Edge and federation settings</span></span>

1. <span data-ttu-id="59b73-130">トポロジ ビルダーを起動します。</span><span class="sxs-lookup"><span data-stu-id="59b73-130">Start Topology Builder.</span></span>
    
2. <span data-ttu-id="59b73-131">**既存の展開からのトポロジのダウンロード**を選択します。</span><span class="sxs-lookup"><span data-stu-id="59b73-131">Select **Download Topology from existing deployment**.</span></span>
    
3. <span data-ttu-id="59b73-132">ファイルの名前を選択し、.tbxml ファイルの既定の種類のトポロジを保存します。</span><span class="sxs-lookup"><span data-stu-id="59b73-132">Choose a file name, and save the topology with the default .tbxml file type.</span></span>
    
4. <span data-ttu-id="59b73-133">展開におけるさまざまなサーバーの役割を明らかにするには、バージョンのインストール] ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="59b73-133">Expand the legacy installs node to reveal the various server roles in the deployment.</span></span>
    
5. <span data-ttu-id="59b73-134">サイト] ノードを選択し、**サイトのフェデレーション ルートの割り当て**の値が設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="59b73-134">Select the site node and verify that a **Site federation route assignment** value is set.</span></span> 
    
     ![トポロジ ビルダーでは、サイトのフェデレーション ルート](../media/migration_lyncserver_w14_federation.jpg)
  
6. <span data-ttu-id="59b73-136">Standard Edition Server または Enterprise Edition フロント エンド プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="59b73-136">Select the Standard Edition Server or Enterprise Edition front end pool.</span></span> <span data-ttu-id="59b73-137">メディア**関連**の下に、エッジ プールが構成されているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="59b73-137">Determine whether an Edge pool has been configured for media below **Associations**.</span></span> 
    
     ![サーバーとプールを表示するトポロジ ビルダー](../media/migration_lyncserver_w14_edgepool_media.jpg)
  
7. <span data-ttu-id="59b73-139">エッジ プールを選択し、**次ホップの選択範囲**の下に次ホップ プールが構成されているかどうかを特定します。</span><span class="sxs-lookup"><span data-stu-id="59b73-139">Select the Edge pool and identify whether a Next hop pool is configured below **Next hop selection**.</span></span>
    
     ![トポロジ ビルダーでは、次ホップの選択](../media/migration_lyncserver_w14_nexthop.jpg)
  
## <a name="verify-legacy-xmpp-federated-partner-configuration"></a><span data-ttu-id="59b73-141">従来の XMPP フェデレーション パートナーの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="59b73-141">Verify legacy XMPP federated partner Configuration</span></span>

1. <span data-ttu-id="59b73-142">従来の XMPP サーバー管理用の Tools\Services のアプレットに移動します。</span><span class="sxs-lookup"><span data-stu-id="59b73-142">From the legacy XMPP server, navigate to the Administrative Tools\Services applet.</span></span>
    
2. <span data-ttu-id="59b73-143">Office 通信サーバーの XMPP ゲートウェイ サービスが開始されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="59b73-143">Verify that the Office Communications Server XMPP Gateway service is started.</span></span> 
    
     ![Office 通信サーバー XMPP ゲートウェイ サービス](../media/migration_lyncserver_15_xmpp_legacyservicesstarted.JPG)
  

