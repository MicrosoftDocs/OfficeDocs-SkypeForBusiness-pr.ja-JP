---
title: フェデレーション ルートとメディア トラフィックを構成する
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
description: フェデレーションとは、別々の組織のユーザーがネットワーク境界を越えて通信することを許可する、複数の SIP ドメイン間での信頼関係のことです。 パイロットプールに移行した後、以前のバージョンのエッジサーバーのフェデレーションルートから、Skype for Business Server 2019 エッジサーバーのフェデレーションルートに移行する必要があります。
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754037"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="2a976-104">フェデレーション ルートとメディア トラフィックを構成する</span><span class="sxs-lookup"><span data-stu-id="2a976-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="2a976-105">フェデレーションとは、別々の組織のユーザーがネットワーク境界を越えて通信することを許可する、複数の SIP ドメイン間での信頼関係のことです。</span><span class="sxs-lookup"><span data-stu-id="2a976-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="2a976-106">パイロットプールに移行した後、以前のバージョンのエッジサーバーのフェデレーションルートから、Skype for Business Server 2019 エッジサーバーのフェデレーションルートに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a976-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="2a976-107">次の手順を使用して、フェデレーションルートと、以前のバージョンのエッジサーバーとディレクターから、単一サイト展開用の Skype for Business Server 2019 エッジサーバーへのメディアトラフィックルートを移行します。</span><span class="sxs-lookup"><span data-stu-id="2a976-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2a976-108">フェデレーションルートとメディアトラフィックルートを変更するには、Skype for Business Server 2019 および以前のバージョンのエッジサーバーのメンテナンスダウンタイムをスケジュールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a976-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="2a976-109">また、この移行プロセスで機能が停止している間は、フェデレーション アクセスも使用できません。</span><span class="sxs-lookup"><span data-stu-id="2a976-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="2a976-110">ダウンタイムは、ユーザー アクティビティが最も少ない時間帯に予定してください。</span><span class="sxs-lookup"><span data-stu-id="2a976-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="2a976-111">また、ダウンタイムが発生することをエンド ユーザーに知らせる必要もあります。</span><span class="sxs-lookup"><span data-stu-id="2a976-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="2a976-112">組織の事情に応じて停止を計画し、適切に対応してください。</span><span class="sxs-lookup"><span data-stu-id="2a976-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2a976-113">従来のエッジサーバーが、アクセスエッジサービス、Web 会議エッジサービス、および音声ビデオエッジサービスに同じ FQDN を使用するように構成されている場合、このセクションの手順はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2a976-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="2a976-114">従来のエッジサービスが同じ FQDN を使用するように構成されている場合は、最初にすべてのユーザーを移行してから、以前のバージョンのエッジサーバーを使用停止してから、Skype for Business Server 2019 エッジサーバーでフェデレーションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a976-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2a976-115">XMPP フェデレーションが Skype for Business Server 2019 エッジサーバーを経由してルーティングされている場合、以前のバージョンのユーザーは、すべてのユーザーが Skype for Business Server 2019、XMPP ポリシーと証明書が構成されるまで、xmpp フェデレーションパートナーと通信できません。 xmpp フェデレーションパートナーは Skype for Business Server の2019で構成されています、最後に DNS エントリが更新されています。</span><span class="sxs-lookup"><span data-stu-id="2a976-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="2a976-116">Skype for Business Server 2019 サイトから従来のフェデレーションの関連付けを削除するには</span><span class="sxs-lookup"><span data-stu-id="2a976-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="2a976-117">Skype for Business Server 2019 フロントエンドサーバーで、トポロジビルダーで既存のトポロジを開きます。</span><span class="sxs-lookup"><span data-stu-id="2a976-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="2a976-118">左側のウィンドウで、[ **Skype For Business Server**] のすぐ下にあるサイトノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="2a976-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="2a976-119">サイトを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a976-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="2a976-120">左ウィンドウで、[**フェデレーション ルート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a976-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="2a976-121">[**サイトのフェデレーションルートの割り当て**] で、[ **SIP フェデレーションの有効化**] チェックボックスをオフにして、従来の環境を経由したフェデレーションルートを無効にします。</span><span class="sxs-lookup"><span data-stu-id="2a976-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="2a976-122">[**OK**] をクリックして、[プロパティの編集] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2a976-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="2a976-123">[**トポロジビルダー**] で、最上位ノードの [ **Skype for business Server**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a976-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="2a976-124">[**アクション**] メニューの [**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a976-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="2a976-125">[**次へ**] をクリックして公開プロセスを完了し、公開プロセスが完了したら [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a976-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="2a976-126">従来のエッジ サーバーをフェデレーションされていないエッジ サーバーとして構成するには</span><span class="sxs-lookup"><span data-stu-id="2a976-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="2a976-127">左側のウィンドウで、従来のインストールノードに移動してから、[**エッジプール**] ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="2a976-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="2a976-128">エッジ サーバーを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a976-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="2a976-129">左ウィンドウの [**全般**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a976-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="2a976-130">[**このエッジプールのフェデレーションを有効にする (ポート 5061)** ] チェックボックスをオフにして、[ **OK]** を選択してページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2a976-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="2a976-131">[**操作**] メニューで [**トポロジの公開**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a976-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="2a976-132">**公開ウィザード**の実行が完了したら、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2a976-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="2a976-133">トポロジビルダーで、従来のエッジサーバーのフェデレーションが無効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2a976-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="2a976-134">従来のエッジサーバーで証明書を構成するには</span><span class="sxs-lookup"><span data-stu-id="2a976-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="2a976-135">従来のエッジサーバーから、秘密キーを使用して外部アクセスプロキシ証明書をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="2a976-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="2a976-136">Skype for Business Server 2019 エッジサーバーで、前の手順でアクセスプロキシの外部証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="2a976-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="2a976-137">エッジサーバーの Skype for Business Server 2019 外部インターフェイスにアクセスプロキシの外部証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2a976-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="2a976-138">Skype for Business Server 2019 エッジサーバーの内部インターフェイス証明書は、信頼できる CA から要求され、割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a976-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="2a976-139">Skype for Business Server 2019 エッジサーバーを使用するように以前のバージョンのフェデレーションルートを変更するには</span><span class="sxs-lookup"><span data-stu-id="2a976-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="2a976-140">トポロジビルダーの左側のウィンドウで、[ **Skype For Business Server 2019** ] ノード、[**エッジプール**] ノードの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="2a976-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="2a976-141">エッジ サーバーを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a976-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="2a976-142">左ウィンドウの [**全般**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a976-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="2a976-143">[**このエッジプールのフェデレーションを有効にする (ポート 5061)**] のチェックボックスをオンにして、[ **OK** ] をクリックしてページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2a976-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="2a976-144">[**操作**] メニューで [**トポロジの公開**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a976-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="2a976-145">**公開ウィザード**の実行が完了したら、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2a976-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="2a976-146">トポロジビルダーで**フェデレーション (ポート 5061)** が**有効**に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2a976-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="2a976-147">Skype for Business Server 2019 エッジサーバーのフェデレーションの次ホップを更新するには</span><span class="sxs-lookup"><span data-stu-id="2a976-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="2a976-148">トポロジビルダーの左側のウィンドウで、[ **Skype For Business Server 2019** ] ノード、[**エッジプール**] ノードの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="2a976-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="2a976-149">ノードを展開し、一覧内のエッジ サーバーを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a976-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="2a976-150">[**全般**] ページの [**次ホップの選択**] で、ドロップダウンリストから [Skype for business Server 2019] プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="2a976-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="2a976-151">[**OK**] をクリックして、[プロパティの編集] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2a976-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="2a976-152">[**トポロジビルダー**] で、最上位ノードの [ **Skype for business Server**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a976-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="2a976-153">[**操作**] メニューの [**トポロジの公開**] をクリックし、ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="2a976-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="2a976-154">Skype for Business Server 2019 エッジサーバーの送信メディアパスを構成するには</span><span class="sxs-lookup"><span data-stu-id="2a976-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="2a976-155">トポロジビルダーの左側のウィンドウで、[ **Skype For Business Server 2019** ] ノードに移動してから、[ **Standard Edition フロントエンドサーバー** ] または [ **Enterprise Edition フロントエンドプール**] の下にあるプールに移動します。</span><span class="sxs-lookup"><span data-stu-id="2a976-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="2a976-156">プールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a976-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="2a976-157">[**関連付け**] セクションで、[**エッジ プールの関連付け (メディア コンポーネント用)**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2a976-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="2a976-158">ドロップダウンボックスから、[Skype for Business Server 2019 エッジサーバー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a976-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="2a976-159">[**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2a976-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="2a976-160">Skype for Business Server 2019 エッジサーバーのフェデレーションを有効にするには</span><span class="sxs-lookup"><span data-stu-id="2a976-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="2a976-161">トポロジビルダーの左側のウィンドウで、[ **Skype For Business Server 2019** ] ノード、[**エッジプール**] ノードの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="2a976-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="2a976-162">ノードを展開し、一覧内のエッジ サーバーを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a976-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="2a976-163">フェデレーションは、単一のエッジプールに対してのみ有効にできます。</span><span class="sxs-lookup"><span data-stu-id="2a976-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="2a976-164">エッジ プールが複数ある場合は、フェデレーション エッジ プールとして使用するエッジ プールを 1 つ選択してください。</span><span class="sxs-lookup"><span data-stu-id="2a976-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="2a976-165">[**全般**] ページで、[**このエッジプールのフェデレーションを有効にする (ポート 5061)** ] チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2a976-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="2a976-166">[**OK**] をクリックして、[プロパティの編集] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2a976-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="2a976-167">サイトノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="2a976-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="2a976-168">サイトを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a976-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="2a976-169">左ウィンドウで、[**フェデレーション ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a976-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="2a976-170">[**サイトのフェデレーションルートの割り当て**] で、[ **SIP フェデレーションの有効化**] を選択してから、リストから [Skype For Business server 2019 エッジサーバー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a976-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="2a976-171">[**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2a976-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="2a976-172">マルチサイト展開の場合は、この手順をサイトごとに実行します。</span><span class="sxs-lookup"><span data-stu-id="2a976-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="2a976-173">エッジ サーバーの構成の変更を公開するには</span><span class="sxs-lookup"><span data-stu-id="2a976-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="2a976-174">[**トポロジビルダー**] で、最上位ノードの [ **Skype for business Server**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a976-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="2a976-175">[**操作**] メニューの [**トポロジの公開**] を選択し、ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="2a976-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="2a976-176">展開内のすべてのプールに対して Active Directory のレプリケーションが発生するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="2a976-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2a976-177">次のメッセージが表示されることがあります。**警告: このトポロジには、複数のフェデレーションエッジサーバーが含まれています。これは、より新しいバージョンの製品への移行中に発生する可能性があります。その場合、フェデレーションに対してアクティブに使用されるエッジサーバーは1つだけです。外部 DNS SRV レコードが正しいエッジサーバーを指していることを確認します。複数のフェデレーションエッジサーバーが同時にアクティブになるように展開する (つまり、移行シナリオではない) 場合は、すべてのフェデレーションパートナーが Skype for Business Server を使用していることを確認してください。外部 DNS SRV レコードに、フェデレーションが有効になっているすべてのエッジサーバーがリスト**されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2a976-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="2a976-178">この警告は予期されるものであり、無視してもかまいません。</span><span class="sxs-lookup"><span data-stu-id="2a976-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="2a976-179">Skype for Business Server 2019 エッジサーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="2a976-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="2a976-180">すべての Skype for Business Server 2019 エッジサーバーをオンラインにします。</span><span class="sxs-lookup"><span data-stu-id="2a976-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="2a976-181">外部ファイアウォールのルーティングルールまたはロードバランサー機器の設定を更新して、外部アクセス (通常はポート 443) およびフェデレーション (通常はポート 5061) の SIP トラフィックを、従来のエッジサーバーではなく、Skype for Business Server の2019エッジサーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="2a976-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2a976-182">ロードバランサー機器を使用していない場合は、新しい Skype for Business Server アクセスエッジサーバーに解決するために、フェデレーション用の DNS A レコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a976-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="2a976-183">これを最小限の中断で完了させるには、外部 Skype for business Server アクセスエッジの FQDN の TLL 値を小さくします。これにより、新しい Skype for business Server アクセスエッジをポイントするように DNS が更新されると、フェデレーションとリモートアクセスがすぐに更新されるようになります。</span><span class="sxs-lookup"><span data-stu-id="2a976-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="2a976-184">各エッジサーバーコンピューターから**Skype For Business Server アクセスエッジ**を停止します。</span><span class="sxs-lookup"><span data-stu-id="2a976-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="2a976-185">従来の各エッジサーバーコンピューターから、[**管理ツール**] から [**サービス**] アプレットを開きます。</span><span class="sxs-lookup"><span data-stu-id="2a976-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="2a976-186">[サービス] の一覧で、[ **Skype For Business Server アクセスエッジ**] を見つけます。</span><span class="sxs-lookup"><span data-stu-id="2a976-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="2a976-187">サービス名を右クリックし、[**停止**] を選択してサービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="2a976-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="2a976-188">スタートアップの種類を [**無効**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="2a976-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="2a976-189">[**OK**] をクリックして、[**プロパティ**] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2a976-189">Click **OK** to close the **Properties** window.</span></span> 
    

