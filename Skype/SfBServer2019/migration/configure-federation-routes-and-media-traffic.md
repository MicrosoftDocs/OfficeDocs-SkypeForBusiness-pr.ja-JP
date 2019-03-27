---
title: フェデレーション ルートとメディア トラフィックの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: フェデレーションとは、ネットワークの境界を越えて通信するために別の組織でユーザーを許可する 2 つまたは複数の SIP ドメイン間の信頼関係です。 パイロット プールに移行した後する必要がありますへの移行から、Skype のフェデレーション ルートには、前バージョン エッジ サーバーのフェデレーション ルートからビジネス サーバー 2019 エッジ サーバーにします。
ms.openlocfilehash: 607d98c3c831ae9fd911b9fd2782490dcfb0e4f4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880229"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="ade64-104">フェデレーション ルートとメディア トラフィックの構成</span><span class="sxs-lookup"><span data-stu-id="ade64-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="ade64-105">フェデレーションとは、ネットワークの境界を越えて通信するために別の組織でユーザーを許可する 2 つまたは複数の SIP ドメイン間の信頼関係です。</span><span class="sxs-lookup"><span data-stu-id="ade64-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="ade64-106">パイロット プールに移行した後する必要がありますへの移行から、Skype のフェデレーション ルートへの以前のバージョンのエッジ トランスポート サーバーのフェデレーション ルートからビジネス サーバー 2019 エッジ サーバーにします。</span><span class="sxs-lookup"><span data-stu-id="ade64-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="ade64-107">単一サイト展開のビジネス サーバー 2019 のエッジ サーバーのフェデレーション ルートと、Skype を以前のバージョンのエッジ サーバーとディレクターからのメディア トラフィックのルートに移行するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="ade64-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ade64-108">フェデレーション ルートとメディア トラフィックの経路を変更するには、ビジネス サーバー 2019 およびエッジ トランスポート サーバーの以前のバージョンの Skype のメンテナンス時のダウンタイムをスケジュールすることが必要です。</span><span class="sxs-lookup"><span data-stu-id="ade64-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="ade64-109">この全体の移行のプロセスもフェデレーション アクセスはしないことを示します使用可能なシステム停止の間。</span><span class="sxs-lookup"><span data-stu-id="ade64-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="ade64-110">最小限のユーザーの利用状況が予想される時期の時間のダウンタイムをスケジュールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade64-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="ade64-111">エンド ・ ユーザーに十分な通知を提供することもする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade64-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="ade64-112">この障害とは、適当な計画を立てて、組織内で期待します。</span><span class="sxs-lookup"><span data-stu-id="ade64-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="ade64-113">アクセス エッジ サービス、Web 会議エッジ サービス、および A の同じ FQDN を使用するのには、従来のエッジ サーバーが構成されている場合と、音声ビデオ エッジ サービスでは、このセクションの手順はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ade64-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="ade64-114">同じ FQDN を使用する従来のエッジ サービスの構成の場合、すべてのユーザーを移行し、ビジネス 2019 エッジ サーバーは、Skype でのフェデレーションを有効にする前に以前のバージョンのエッジ サーバーを非コミッションに最初必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade64-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="ade64-115">XMPP フェデレーションは、Skype を通じてビジネス 2019 エッジ サーバーにルーティングされている場合、前のバージョンのユーザーことはできませんすべてのユーザーが Skype をビジネス サーバー 2019、XMPP のポリシーに移動されるまでに、XMPP フェデレーション パートナーと通信して証明書が構成されている、XMPP フェデレーション パートナーがビジネス サーバーの 2019 の Skype で構成されて、最後に、DNS のエントリが更新されました。</span><span class="sxs-lookup"><span data-stu-id="ade64-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="ade64-116">ビジネス サーバー 2019 サイトの Skype からの従来の連合の関連付けを削除するには</span><span class="sxs-lookup"><span data-stu-id="ade64-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="ade64-117">ビジネス サーバー 2019 のフロント エンド サーバーの Skype、トポロジ ビルダーで既存のトポロジを開きます。</span><span class="sxs-lookup"><span data-stu-id="ade64-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="ade64-118">左側のペインでは、 **Skype**のすぐ下にある [サイト] ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="ade64-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="ade64-119">サイトを右クリックし、 **[プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade64-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="ade64-120">左側のウィンドウでは、**フェデレーション ルート**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ade64-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="ade64-121">[**サイトのフェデレーション ルートの割り当て**では、従来の環境でのフェデレーション ルートを無効にする**フェデレーションの SIP を有効にする**チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="ade64-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="ade64-122">プロパティの編集] ページを閉じます **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade64-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="ade64-123">**トポロジ ビルダー**では、 **Skype**ビジネス サーバーの最上位ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="ade64-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="ade64-124">**[操作**] メニューから **[トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade64-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="ade64-125">**次**発行のプロセスを完了する] をクリックし、発行プロセスが完了したら [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade64-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="ade64-126">エッジ、非フェデレーション サーバーとして、従来のエッジ サーバーを構成するのには</span><span class="sxs-lookup"><span data-stu-id="ade64-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="ade64-127">左側のウィンドウで、従来のインストール] ノードにし、**プールのエッジ**のノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="ade64-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="ade64-128">エッジ サーバーを右クリックし、 **[プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade64-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="ade64-129">左側のペインで、[**全般**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ade64-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="ade64-130">**このエッジ プール (ポート 5061) のフェデレーションを有効にする**] チェック ボックスをオフにし、ページを閉じるには、 **[ok]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ade64-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="ade64-131">**[操作**] メニューからは、**公開トポロジ**を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade64-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="ade64-132">**発行ウィザード**を完了すると、ウィザードを終了するのには**完了**ををクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade64-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="ade64-133">トポロジ ビルダーで既存のエッジ サーバーのフェデレーションが無効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ade64-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="ade64-134">レガシ エッジ サーバーに証明書を構成するのには</span><span class="sxs-lookup"><span data-stu-id="ade64-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="ade64-135">従来のエッジ サーバーの秘密キーで、外部アクセス プロキシ証明書をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ade64-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="ade64-136">ビジネス サーバー 2019 エッジ サーバー、およびインポートの Skype にアクセス プロキシの外部証明書の前の手順から。</span><span class="sxs-lookup"><span data-stu-id="ade64-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="ade64-137">エッジ サーバーの外部インターフェイスをビジネス サーバー 2019 の Skype にアクセス プロキシの外部証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ade64-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="ade64-138">ビジネス 2019 エッジ サーバーの Skype の内部インターフェイスの証明書は信頼された CA から要求され、割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade64-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="ade64-139">ビジネス 2019 エッジ サーバーの Skype を使用するフェデレーション ルートを以前のバージョンを変更するのには</span><span class="sxs-lookup"><span data-stu-id="ade64-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="ade64-140">トポロジ ビルダーでは、左側のウィンドウで、**ビジネス サーバー 2019 の Skype**ノード、**エッジ プール**] を移動します。</span><span class="sxs-lookup"><span data-stu-id="ade64-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="ade64-141">エッジ サーバーを右クリックし、 **[プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade64-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="ade64-142">左側のペインで、[**全般**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ade64-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="ade64-143">**(ポート 5061) エッジ プールのフェデレーションを有効にする**のチェック ボックスをオンにし、ページを閉じるには、 **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade64-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="ade64-144">**[操作**] メニューからは、**公開トポロジ**を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade64-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="ade64-145">**発行ウィザード**を完了すると、ウィザードを終了するのには**完了**ををクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade64-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="ade64-146">**フェデレーション (ポート 5061)** は、トポロジ ビルダーで **[有効**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ade64-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="ade64-147">ビジネス 2019 エッジ サーバーのフェデレーションの次ホップの Skype を更新するには</span><span class="sxs-lookup"><span data-stu-id="ade64-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="ade64-148">トポロジ ビルダーでは、左側のウィンドウで、**ビジネス サーバー 2019 の Skype**ノード、**エッジ プール**] を移動します。</span><span class="sxs-lookup"><span data-stu-id="ade64-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="ade64-149">ノードを展開し、一覧に、エッジ サーバーを右クリックし、 **[プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade64-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="ade64-150">[**全般**] ページの [**次ホップの選択**] で、ビジネス サーバー 2019 プールの Skype をドロップ ダウン リストから選択します。</span><span class="sxs-lookup"><span data-stu-id="ade64-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="ade64-151">プロパティの編集] ページを閉じます **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade64-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="ade64-152">**トポロジ ビルダー**では、 **Skype**ビジネス サーバーの最上位ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="ade64-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="ade64-153">**[操作**] メニューから [**トポロジの公開**] をクリックし、ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="ade64-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="ade64-154">Skype をビジネス 2019 エッジ サーバーの外部メディアのパスを構成するのには</span><span class="sxs-lookup"><span data-stu-id="ade64-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="ade64-155">トポロジ ビルダーでは、左側のウィンドウで、 **Skype**ビジネス サーバー 2019 のノードにし、**標準のエディションのフロント エンド サーバー**または**エンタープライズ エディションのフロント エンド プール**の下のプールを移動します。</span><span class="sxs-lookup"><span data-stu-id="ade64-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="ade64-156">プールを右クリックし、 **[プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade64-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="ade64-157">[**関連付け**] セクションで、 **(メディア コンポーネント) に関連付けるエッジ プール**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="ade64-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="ade64-158">ドロップ ダウン ボックスからビジネス 2019 エッジ サーバーは、Skype を選択します。</span><span class="sxs-lookup"><span data-stu-id="ade64-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="ade64-159">**プロパティの編集**] ページを閉じます **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade64-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="ade64-160">Skype ビジネス 2019 エッジ サーバーのフェデレーションを有効にするのには</span><span class="sxs-lookup"><span data-stu-id="ade64-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="ade64-161">トポロジ ビルダーでは、左側のウィンドウで、**ビジネス サーバー 2019 の Skype**ノード、**エッジ プール**] を移動します。</span><span class="sxs-lookup"><span data-stu-id="ade64-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="ade64-162">ノードを展開し、一覧に、エッジ サーバーを右クリックし、 **[プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade64-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ade64-163">フェデレーションは、1 つのエッジ プールにのみ有効にできます。</span><span class="sxs-lookup"><span data-stu-id="ade64-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="ade64-164">複数のエッジ プールがある場合は場合、は、フェデレーションのエッジのプールとして使用する 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="ade64-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="ade64-165">[**全般**] ページで、[**このエッジ プール (ポート 5061) のフェデレーションを有効にする**] チェック ボックスが選択されているを確認します。</span><span class="sxs-lookup"><span data-stu-id="ade64-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="ade64-166">プロパティの編集] ページを閉じます **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade64-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="ade64-167">サイト] ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="ade64-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="ade64-168">サイトを右クリックし、 **[プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade64-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="ade64-169">左側のウィンドウでは、**フェデレーション ルート**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade64-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="ade64-170">**サイトのフェデレーション ルートの割り当て**、[**フェデレーションの SIP を有効にする**を選択し、一覧から、Skype ビジネス サーバー 2019 エッジ サーバーの一覧のします。</span><span class="sxs-lookup"><span data-stu-id="ade64-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="ade64-171">**プロパティの編集**] ページを閉じます **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade64-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="ade64-172">マルチサイト展開では、サイトごとにこの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ade64-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="ade64-173">エッジ サーバーの構成の変更を発行するには</span><span class="sxs-lookup"><span data-stu-id="ade64-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="ade64-174">**トポロジ ビルダー**では、 **Skype**ビジネス サーバーの最上位ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="ade64-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="ade64-175">**[操作**] メニューからは、**トポロジの公開**を選択し、ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="ade64-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="ade64-176">Active Directory のレプリケーションを展開内のすべてのプールを実行するを待ちます。</span><span class="sxs-lookup"><span data-stu-id="ade64-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ade64-177">次のメッセージが表示ことがあります:**の警告: トポロジに複数のエッジ サーバー フェデレーションにはが含まれています。これは、製品の最新のバージョンへの移行中に発生します。その場合は、フェデレーションのエッジ サーバーの 1 つだけをアクティブに使用がします。外部の DNS SRV レコードは、適切なエッジ サーバーを指していることを確認します。複数のフェデレーションにエッジ サーバーを展開する場合 (つまり、いない移行シナリオ)、同時にアクティブでは、すべてのフェデレーション パートナーがビジネス サーバー用に Skype を使用していることを確認します。すべてのフェデレーションを有効になっているエッジ トランスポート サーバーを外部の DNS SRV レコードが表示されていることを確認します**。</span><span class="sxs-lookup"><span data-stu-id="ade64-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="ade64-178">この警告は、予想され、安全に無視することができます。</span><span class="sxs-lookup"><span data-stu-id="ade64-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="ade64-179">Skype をビジネス 2019 エッジ サーバー用に構成するには</span><span class="sxs-lookup"><span data-stu-id="ade64-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="ade64-180">オンラインに、Skype のビジネス サーバー 2019 エッジ サーバーにします。</span><span class="sxs-lookup"><span data-stu-id="ade64-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="ade64-181">外部ファイアウォールのルーティング ルールや外部アクセス用の SIP トラフィックを送信するハードウェア ロード バランサーの設定を更新する (通常はポート 443) とフェデレーション (通常はポート 5061) ビジネス 2019 エッジ サーバー、レガシ エッジ サーバーではなくの Skype にします。</span><span class="sxs-lookup"><span data-stu-id="ade64-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ade64-182">ハードウェア ロード バランサーがない場合は、フェデレーションのビジネス サーバーのアクセス エッジ サーバーの新しい Skype を解決するのには DNS の A レコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ade64-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="ade64-183">これを行うため、最小限の中断で、値が小さく TLL 外部 Skype のビジネス サーバーのアクセス エッジの FQDN をフェデレーションとリモート アクセスが迅速に更新するビジネス サーバーのアクセス エッジ用の新しい Skype を指すように DNS が更新されると、ようにします。</span><span class="sxs-lookup"><span data-stu-id="ade64-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="ade64-184">各エッジ サーバーのコンピューターからの**ビジネス サーバーのアクセス エッジの Skype**を停止します。</span><span class="sxs-lookup"><span data-stu-id="ade64-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="ade64-185">各レガシ エッジ サーバーのコンピューターから、 **[管理ツール**] から [**サービス**] アプレットを開きます。</span><span class="sxs-lookup"><span data-stu-id="ade64-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="ade64-186">サービスの一覧で、**ビジネス サーバーのアクセス エッジの Skype**を検索します。</span><span class="sxs-lookup"><span data-stu-id="ade64-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="ade64-187">サービス名を右クリックし、**停止**サービスを停止するします。</span><span class="sxs-lookup"><span data-stu-id="ade64-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="ade64-188">**無効に**するには、スタートアップの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="ade64-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="ade64-189">**[プロパティ**] ウィンドウを閉じます **[ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ade64-189">Click **OK** to close the **Properties** window.</span></span> 
    

