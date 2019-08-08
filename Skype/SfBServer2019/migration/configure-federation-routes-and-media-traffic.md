---
title: フェデレーション ルートとメディア トラフィックの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: フェデレーションは、2つ以上の SIP ドメイン間の信頼関係であり、別々の組織のユーザーがネットワーク境界を越えて通信することを許可します。 パイロットプールに移行した後、以前のバージョンのエッジサーバーのフェデレーションルートから、Skype for Business Server 2019 エッジサーバーのフェデレーションルートに移行する必要があります。
ms.openlocfilehash: 50c10a4dced237e59c8dad12b5bdee1ef7d970fe
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239363"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="36ebb-104">フェデレーション ルートとメディア トラフィックの構成</span><span class="sxs-lookup"><span data-stu-id="36ebb-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="36ebb-105">フェデレーションは、2つ以上の SIP ドメイン間の信頼関係であり、別々の組織のユーザーがネットワーク境界を越えて通信することを許可します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="36ebb-106">パイロットプールに移行した後、以前のバージョンのエッジサーバーのフェデレーションルートから、Skype for Business Server 2019 エッジサーバーのフェデレーションルートに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36ebb-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="36ebb-107">次の手順を使用して、フェデレーションルートと、以前のバージョンのエッジサーバーとディレクターからのメディアトラフィックルートを、単一サイト展開用の Skype for Business Server 2019 エッジサーバーに移行します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="36ebb-108">フェデレーションルートとメディアトラフィックルートを変更するには、Skype for Business Server 2019 と以前のバージョンのエッジサーバーの保守のダウンタイムをスケジュールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="36ebb-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="36ebb-109">この切り替えプロセス全体は、停止期間中はフェデレーションアクセスを使用できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="36ebb-110">最小限のユーザーアクティビティが想定されている場合は、ダウンタイムのスケジュールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36ebb-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="36ebb-111">また、エンドユーザーに十分な通知も提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36ebb-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="36ebb-112">この停止に応じて計画し、組織内で適切な期待を設定します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="36ebb-113">従来の Edge Server が、アクセスエッジサービス、Web 会議エッジサービス、および A/V Edge サービスに同じ FQDN を使用するように構成されている場合、このセクションの手順はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="36ebb-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="36ebb-114">従来のエッジサービスが同じ FQDN を使用するように構成されている場合は、まずすべてのユーザーを移行した後、以前のバージョンのエッジサーバーを廃止してから Skype for Business Server 2019 Edge サーバーでフェデレーションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="36ebb-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="36ebb-115">使用している XMPP フェデレーションが Skype for Business Server 2019 Edge サーバー経由でルーティングされている場合、以前のバージョンのユーザーは、すべてのユーザーが Skype for Business Server 2019、XMPP ポリシー、および証明書が構成され、XMPP フェデレーションパートナーが Skype for Business Server 2019 で構成されています。最後に、DNS エントリが更新されています。</span><span class="sxs-lookup"><span data-stu-id="36ebb-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="36ebb-116">Skype for Business Server 2019 サイトから従来のフェデレーション関連付けを削除するには</span><span class="sxs-lookup"><span data-stu-id="36ebb-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="36ebb-117">Skype for Business Server 2019 フロントエンドサーバーで、トポロジビルダーで既存のトポロジを開きます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="36ebb-118">左側のウィンドウで、[ **Skype For Business Server**] のすぐ下にある [サイト] ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="36ebb-119">サイトを右クリックし、[プロパティの**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36ebb-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="36ebb-120">左側のウィンドウで、[**フェデレーションルート**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="36ebb-121">[**サイトフェデレーションルートの割り当て**] で、[ **SIP フェデレーションを有効**にする] チェックボックスをオフにして、従来の環境でフェデレーションルートを無効にします。</span><span class="sxs-lookup"><span data-stu-id="36ebb-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="36ebb-122">[ **OK]** をクリックして、[プロパティの編集] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="36ebb-123">[**トポロジビルダー**] で、トップノードの**Skype for business Server**を選びます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="36ebb-124">[**アクション**] メニューの [**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36ebb-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="36ebb-125">[**次へ**] をクリックして発行プロセスを完了し、発行プロセスが完了したら [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36ebb-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="36ebb-126">レガシエッジサーバーを非フェデレーションエッジサーバーとして構成するには</span><span class="sxs-lookup"><span data-stu-id="36ebb-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="36ebb-127">左側のウィンドウで、従来のインストールノードに移動し、[ **Edge プール**] ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="36ebb-128">エッジサーバーを右クリックし、[プロパティの**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36ebb-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="36ebb-129">左側のウィンドウで [**全般**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="36ebb-130">[**この Edge プールのフェデレーションを有効にする (ポート 5061)** ] チェックボックスをオフにし、[ **OK** ] を選択してページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="36ebb-131">[**操作**] メニューで、[**発行トポロジ**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36ebb-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="36ebb-132">**発行ウィザード**が完了したら、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="36ebb-133">トポロジビルダーで、従来のエッジサーバーのフェデレーションが無効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="36ebb-134">従来のエッジサーバーで証明書を構成するには</span><span class="sxs-lookup"><span data-stu-id="36ebb-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="36ebb-135">外部アクセスプロキシ証明書を、レガシエッジサーバーから秘密キー付きでエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="36ebb-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="36ebb-136">Skype for Business Server 2019 Edge サーバーで、前の手順でアクセスプロキシの外部証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="36ebb-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="36ebb-137">アクセスプロキシの外部証明書を、エッジサーバーの Skype for Business Server 2019 外部インターフェイスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="36ebb-138">Skype for Business Server 2019 Edge サーバーの内部インターフェイス証明書は、信頼できる CA から要求され、割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="36ebb-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="36ebb-139">以前のバージョンのフェデレーションルートを変更して、Skype for Business Server 2019 Edge Server を使用するには</span><span class="sxs-lookup"><span data-stu-id="36ebb-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="36ebb-140">[トポロジビルダー] の左側のウィンドウで、[ **Skype For Business Server 2019** ] ノードに移動し、[ **Edge プール**] ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="36ebb-141">エッジサーバーを右クリックし、[プロパティの**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36ebb-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="36ebb-142">左側のウィンドウで [**全般**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="36ebb-143">**このエッジプール (ポート 5061) の [フェデレーションを有効にする**] チェックボックスをオンにし、[ **OK** ] をクリックしてページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="36ebb-144">[**操作**] メニューで、[**発行トポロジ**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36ebb-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="36ebb-145">**発行ウィザード**が完了したら、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="36ebb-146">[トポロジビルダー] で [**フェデレーション (ポート 5061)** ] が [**有効**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="36ebb-147">Skype for Business Server 2019 Edge Server フェデレーションの次ホップを更新するには</span><span class="sxs-lookup"><span data-stu-id="36ebb-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="36ebb-148">[トポロジビルダー] の左側のウィンドウで、[ **Skype For Business Server 2019** ] ノードに移動し、[ **Edge プール**] ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="36ebb-149">ノードを展開し、表示されたエッジサーバーを右クリックして、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36ebb-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="36ebb-150">[**全般**] ページの [**次のホップの選択**] で、ドロップダウンリストから [Skype for business Server 2019 プール] を選びます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="36ebb-151">[ **OK]** をクリックして、[プロパティの編集] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="36ebb-152">[**トポロジビルダー**] で、トップノードの**Skype for business Server**を選びます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="36ebb-153">[**アクション**] メニューで、[**トポロジの発行**] をクリックしてウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="36ebb-154">Skype for Business Server 2019 Edge Server の送信メディアパスを構成するには</span><span class="sxs-lookup"><span data-stu-id="36ebb-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="36ebb-155">[Topology Builder] の左側のウィンドウで、[ **Skype For Business Server 2019** ] ノードに移動し、[ **Standard Edition フロントエンドサーバー** ] または [ **Enterprise Edition フロントエンドプール**] の下のプールに移動します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="36ebb-156">プールを右クリックし、[プロパティの**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36ebb-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="36ebb-157">[**関連付け**] セクションで、[ **Edge プールを関連付ける (メディアコンポーネント用)** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="36ebb-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="36ebb-158">ドロップダウンボックスで、Skype for Business Server 2019 Edge サーバーを選びます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="36ebb-159">[ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="36ebb-160">Skype for Business Server 2019 Edge Server federation を有効にするには</span><span class="sxs-lookup"><span data-stu-id="36ebb-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="36ebb-161">[トポロジビルダー] の左側のウィンドウで、[ **Skype For Business Server 2019** ] ノードに移動し、[ **Edge プール**] ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="36ebb-162">ノードを展開し、表示されたエッジサーバーを右クリックして、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36ebb-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="36ebb-163">フェデレーションは、1つのエッジプールに対してのみ有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="36ebb-164">エッジプールが複数ある場合は、フェデレーションエッジプールとして使用するためにいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="36ebb-165">[**全般**] ページで、[**このエッジプールのフェデレーションを有効にする (Port 5061)** ] チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="36ebb-166">[ **OK]** をクリックして、[プロパティの編集] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="36ebb-167">サイトノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="36ebb-168">サイトを右クリックし、[プロパティの**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36ebb-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="36ebb-169">左側のウィンドウで、[**フェデレーションルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36ebb-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="36ebb-170">[**サイトフェデレーションルートの割り当て**] で、[ **SIP フェデレーションを有効にする**] を選び、一覧から [Skype For Business Server 2019 Edge server] を選びます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="36ebb-171">[ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="36ebb-172">複数サイト展開の場合は、各サイトでこの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="36ebb-173">エッジサーバー構成の変更を公開するには</span><span class="sxs-lookup"><span data-stu-id="36ebb-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="36ebb-174">[**トポロジビルダー**] で、トップノードの**Skype for business Server**を選びます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="36ebb-175">[**アクション**] メニューで、[**トポロジの公開**] を選択し、ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="36ebb-176">展開内のすべてのプールに対して Active Directory のレプリケーションが行われるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="36ebb-177">次のメッセージが表示されることがあります:**警告: トポロジに複数のフェデレーションエッジサーバーが含まれています。これは、製品の最新バージョンへの移行中に発生する可能性があります。その場合は、1つのエッジサーバーのみがフェデレーションに対してアクティブに使用されます。外部 DNS SRV レコードが適切なエッジサーバーを指していることを確認します。複数のフェデレーションエッジサーバーを展開して同時にアクティブにするには (つまり、移行シナリオではなく)、すべてのフェデレーションパートナーが Skype for Business Server を使用していることを確認します。外部 DNS SRV レコードに、すべてのフェデレーションが有効なエッジサーバーの一覧が表示されていることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="36ebb-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="36ebb-178">この警告は予期されるものであり、無視しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="36ebb-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="36ebb-179">Skype for Business Server 2019 エッジサーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="36ebb-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="36ebb-180">すべての Skype for Business Server 2019 Edge サーバーをオンラインにします。</span><span class="sxs-lookup"><span data-stu-id="36ebb-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="36ebb-181">外部アクセス (通常はポート 443) およびフェデレーション (通常はポート 5061) の SIP トラフィックを、従来のエッジサーバーではなく、Skype for Business Server 2019 Edge サーバーに送信するには、外部ファイアウォールルーティングルールまたはハードウェアロードバランサーの設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="36ebb-182">ハードウェアロードバランサーを持っていない場合は、新しい Skype for Business Server アクセスエッジサーバーに解決するために、フェデレーション用の DNS A レコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36ebb-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="36ebb-183">これを最小限の中断で実現するには、外部の Skype for business Server アクセスエッジ FQDN の TLL 値を減らして、新しい Skype for Business Server アクセスエッジをポイントするように DNS が更新されたときに、フェデレーションおよびリモートアクセスがすぐに更新されるようにします。</span><span class="sxs-lookup"><span data-stu-id="36ebb-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="36ebb-184">各エッジサーバーコンピューターから**Skype For Business Server へのアクセスエッジ**を停止します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="36ebb-185">各レガシエッジサーバーコンピューターで、[**管理ツール**] の [**サービス**] アプレットを開きます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="36ebb-186">[サービス] リストで、[ **Skype For Business Server アクセスエッジ**] を見つけます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="36ebb-187">[サービス名] を右クリックし、[**停止**] を選択してサービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="36ebb-188">[スタートアップの種類を**無効**に設定します。</span><span class="sxs-lookup"><span data-stu-id="36ebb-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="36ebb-189">[ **OK** ] をクリックして、[**プロパティ**] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="36ebb-189">Click **OK** to close the **Properties** window.</span></span> 
    

