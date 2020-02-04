---
title: フェデレーション ルートとメディア トラフィックの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cd9cf1c7c61261e4e1a6974498f9f9dff980169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="d663e-102">フェデレーション ルートとメディア トラフィックの構成</span><span class="sxs-lookup"><span data-stu-id="d663e-102">Configure federation routes and media traffic</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d663e-103">_**最終更新日:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="d663e-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="d663e-104">フェデレーションは、2つ以上の SIP ドメイン間の信頼関係であり、別々の組織のユーザーがネットワーク境界を越えて通信することを許可します。</span><span class="sxs-lookup"><span data-stu-id="d663e-104">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="d663e-105">Lync Server 2013 パイロットプールに移行した後、lync Server 2010 エッジサーバーのフェデレーションルートから、Lync Server 2013 Edge サーバーのフェデレーションルートに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d663e-105">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Lync Server 2010 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="d663e-106">次の手順を使用して、フェデレーションルートと、Lync server 2010 エッジサーバーとディレクターから Lync Server 2013 Edge サーバーに、単一サイト展開用のメディアトラフィックルートを移行します。</span><span class="sxs-lookup"><span data-stu-id="d663e-106">Use the following procedures to transition the federation route and the media traffic route from your Lync Server 2010 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d663e-107">フェデレーションルートとメディアトラフィックルートを変更するには、Lync Server 2013 および Lync Server 2010 エッジサーバーのメンテナンスダウンタイムをスケジュールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d663e-107">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Lync Server 2010 Edge Servers.</span></span> <span data-ttu-id="d663e-108">この切り替えプロセス全体は、停止期間中はフェデレーションアクセスを使用できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d663e-108">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="d663e-109">最小限のユーザーアクティビティが想定されている場合は、ダウンタイムのスケジュールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d663e-109">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="d663e-110">また、エンドユーザーに十分な通知も提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d663e-110">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="d663e-111">この停止に応じて計画し、組織内で適切な期待を設定します。</span><span class="sxs-lookup"><span data-stu-id="d663e-111">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d663e-112">従来の Lync Server 2010 Edge サーバーが、アクセスエッジサービス、Web 会議エッジサービス、および A/V Edge サービスに同じ FQDN を使用するように構成されている場合、このセクションの手順はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="d663e-112">If your legacy Lync Server 2010 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="d663e-113">従来の Edge サービスが同じ FQDN を使用するように構成されている場合は、まず、lync server 2010 から Lync Server 2013 にすべてのユーザーを移行してから、lync server 2013 Edge サーバーでフェデレーションを有効にする前に、Lync Server 2010 Edge サーバーを非コミッションにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d663e-113">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Lync Server 2010 to Lync Server 2013, then decommission the Lync Server 2010 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d663e-114">使用している XMPP フェデレーションが Lync Server 2013 Edge サーバー経由でルーティングされている場合、従来の Lync Server 2010 ユーザーは、すべてのユーザーが Lync Server 2013 に移動されるまで XMPP フェデレーションパートナーと通信できません。 XMPP ポリシーと証明書は、構成されている場合、XMPP フェデレーションパートナーは Lync Server 2013 で構成されていますが、最後に DNS エントリが更新されています。</span><span class="sxs-lookup"><span data-stu-id="d663e-114">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Lync Server 2010 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="d663e-115">Lync Server 2013 サイトから従来のフェデレーション関連付けを削除するには</span><span class="sxs-lookup"><span data-stu-id="d663e-115">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="d663e-116">Lync Server 2013 フロントエンドサーバーで、トポロジビルダーで既存のトポロジを開きます。</span><span class="sxs-lookup"><span data-stu-id="d663e-116">On the Lync Server 2013 Front End server, open the existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="d663e-117">左側のウィンドウで、[ **Lync Server**] のすぐ下にある [サイト] ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="d663e-117">In the left pane, navigate to the site node, which is located directly below **Lync Server**.</span></span>

3.  <span data-ttu-id="d663e-118">サイトを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d663e-118">Right-click the site and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="d663e-119">左側のウィンドウで、[**フェデレーションルート**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d663e-119">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="d663e-120">[**サイトフェデレーションルートの割り当て**] で、[ **SIP フェデレーションを有効**にする] チェックボックスをオフにして、従来の Lync Server 2010 環境でフェデレーションルートを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d663e-120">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy Lync Server 2010 environment.</span></span>
    
    <span data-ttu-id="d663e-121">![[プロパティの編集] ダイアログ、[フェデレーションルート] ページ](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "[プロパティの編集] ダイアログ、[フェデレーションルート] ページ")</span><span class="sxs-lookup"><span data-stu-id="d663e-121">![Edit Properties dialog, Federation route page](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>

6.  <span data-ttu-id="d663e-122">[ **OK]** をクリックして、[プロパティの編集] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d663e-122">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="d663e-123">[**トポロジビルダー**] から、トップノードの**Lync サーバー**を選びます。</span><span class="sxs-lookup"><span data-stu-id="d663e-123">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="d663e-124">[**アクション**] メニューの [**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d663e-124">From the **Action** menu, click **Publish Topology**.</span></span>

9.  <span data-ttu-id="d663e-125">[**次へ**] をクリックして発行プロセスを完了し、発行プロセスが完了したら [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d663e-125">Click **Next** to complete the publishing process and then click **Finish** when the publishing process has completed.</span></span>

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="d663e-126">レガシエッジサーバーを非フェデレーションエッジサーバーとして構成するには</span><span class="sxs-lookup"><span data-stu-id="d663e-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="d663e-127">左側のウィンドウで、[ **Lync Server 2010** ] ノードに移動し、[ **Edge プール**] ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="d663e-127">In the left pane, navigate to the **Lync Server 2010** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="d663e-128">エッジサーバーを右クリックし、[プロパティの**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d663e-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="d663e-129">左側のウィンドウで [**全般**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d663e-129">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="d663e-130">[**この Edge プールのフェデレーションを有効にする (ポート 5061)** ] チェックボックスをオフにして、[ **OK]** を選択してページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d663e-130">Clear the **Enable federation for this Edge pool (port 5061)** check box entry and select **OK** to close the page.</span></span>
    
    <span data-ttu-id="d663e-131">![プロパティを編集する、一般に、[フェデレーションを有効にする] をオフにする](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "プロパティを編集する、一般に、[フェデレーションを有効にする] をオフにする")</span><span class="sxs-lookup"><span data-stu-id="d663e-131">![Edit Properties, General, clear Enable federation](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Edit Properties, General, clear Enable federation")</span></span>

5.  <span data-ttu-id="d663e-132">[**操作**] メニューで、[**発行トポロジ**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d663e-132">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="d663e-133">**発行ウィザード**が完了したら、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d663e-133">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="d663e-134">従来のエッジサーバーのフェデレーションが無効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d663e-134">Verify federation for the legacy Edge server is disabled.</span></span>
    
    <span data-ttu-id="d663e-135">![トポロジビルダー、エッジプール、フェデレーションの無効化](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "トポロジビルダー、エッジプール、フェデレーションの無効化")</span><span class="sxs-lookup"><span data-stu-id="d663e-135">![Topology Builder, Edge pool, federation disabled](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Topology Builder, Edge pool, federation disabled")</span></span>

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a><span data-ttu-id="d663e-136">Lync Server 2010 エッジサーバーで証明書を構成するには</span><span class="sxs-lookup"><span data-stu-id="d663e-136">To configure certificates on the Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="d663e-137">従来の Lync Server 2010 エッジサーバーから、秘密キーを使用して外部アクセスプロキシ証明書をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="d663e-137">Export the external Access Proxy certificate, with the private key, from the legacy Lync Server 2010 Edge Server.</span></span>

2.  <span data-ttu-id="d663e-138">Lync Server 2013 エッジサーバー上で、前の手順でアクセスプロキシの外部証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="d663e-138">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="d663e-139">アクセスプロキシの外部証明書を、エッジサーバーの Lync Server 2013 外部インターフェイスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d663e-139">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="d663e-140">Lync Server 2013 エッジサーバーの内部インターフェイス証明書は、信頼できる CA から要求され、割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d663e-140">The internal interface certificate of the Lync Server 2013 Edge Server should be requested from a trusted CA and assigned.</span></span>

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="d663e-141">Lync server 2010 フェデレーションルートを変更して Lync Server 2013 エッジサーバーを使用するには</span><span class="sxs-lookup"><span data-stu-id="d663e-141">To change Lync Server 2010 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="d663e-142">[トポロジビルダー] の左側のウィンドウで、[ **Lync Server 2013** ] ノードに移動し、[ **Edge プール**] ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="d663e-142">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="d663e-143">エッジサーバーを右クリックし、[プロパティの**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d663e-143">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="d663e-144">左側のウィンドウで [**全般**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d663e-144">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="d663e-145">[**この Edge プールのフェデレーションを有効にする (ポート 5061)** ] のチェックボックスエントリをオンにし、[ **OK** ] をクリックしてページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d663e-145">Select the check box entry for **Enable federation for this Edge pool (port 5061)** and then click **OK** to close the page.</span></span>
    
    <span data-ttu-id="d663e-146">![[プロパティの編集] ダイアログの [全般] ページ](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "[プロパティの編集] ダイアログの [全般] ページ")</span><span class="sxs-lookup"><span data-stu-id="d663e-146">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

5.  <span data-ttu-id="d663e-147">[**操作**] メニューで、[**発行トポロジ**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d663e-147">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="d663e-148">**発行ウィザード**が完了したら、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d663e-148">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="d663e-149">**フェデレーション (ポート 5061)** が**有効**に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d663e-149">Verify **Federation (port 5061)** is set to **Enabled**.</span></span>
    
    <span data-ttu-id="d663e-150">![トポロジビルダー、エッジプール、フェデレーションを有効にする](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "トポロジビルダー、エッジプール、フェデレーションを有効にする")</span><span class="sxs-lookup"><span data-stu-id="d663e-150">![Topology Builder, Edge pool, Federation enabled](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Topology Builder, Edge pool, Federation enabled")</span></span>

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a><span data-ttu-id="d663e-151">Lync Server 2013 Edge Server フェデレーションの次ホップを更新するには</span><span class="sxs-lookup"><span data-stu-id="d663e-151">To update Lync Server 2013 Edge Server federation next hop</span></span>

1.  <span data-ttu-id="d663e-152">[トポロジビルダー] の左側のウィンドウで、[ **Lync Server 2013** ] ノードに移動し、[ **Edge プール**] ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="d663e-152">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="d663e-153">ノードを展開し、表示されたエッジサーバーを右クリックして、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d663e-153">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="d663e-154">[**全般**] ページの [**次ホップの選択**] で、ドロップダウンリストから Lync Server 2013 プールを選びます。</span><span class="sxs-lookup"><span data-stu-id="d663e-154">On the **General** page, under **Next hop selection**, select from the drop-down list the Lync Server 2013  pool.</span></span>
    
    <span data-ttu-id="d663e-155">![[プロパティの編集] ダイアログ、[次ホップ] ページ](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "[プロパティの編集] ダイアログ、[次ホップ] ページ")</span><span class="sxs-lookup"><span data-stu-id="d663e-155">![Edit Properties dialog, Next hop page](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Edit Properties dialog, Next hop page")</span></span>

4.  <span data-ttu-id="d663e-156">[ **OK]** をクリックして、[プロパティの編集] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d663e-156">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="d663e-157">[**トポロジビルダー**] から、トップノードの**Lync サーバー**を選びます。</span><span class="sxs-lookup"><span data-stu-id="d663e-157">From **Topology Builder**, select the top node **Lync Server** .</span></span>

6.  <span data-ttu-id="d663e-158">[**アクション**] メニューで、[**トポロジの発行**] をクリックしてウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="d663e-158">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="d663e-159">Lync Server 2013 Edge Server の送信メディアパスを構成するには</span><span class="sxs-lookup"><span data-stu-id="d663e-159">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="d663e-160">[トポロジビルダー] の左側のウィンドウで、[ **Lync Server 2013** ] ノードに移動し、[ **Standard Edition フロントエンドサーバー** ] または [ **Enterprise Edition フロントエンドプール**] の下のプールに移動します。</span><span class="sxs-lookup"><span data-stu-id="d663e-160">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="d663e-161">プールを右クリックし、[プロパティの**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d663e-161">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="d663e-162">[**関連付け**] セクションで、[ **Edge プールを関連付ける (メディアコンポーネント用)** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d663e-162">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>
    
    <span data-ttu-id="d663e-163">![[プロパティの編集]、[全般]、[Edge プールの関連付け]](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "[プロパティの編集]、[全般]、[Edge プールの関連付け]")</span><span class="sxs-lookup"><span data-stu-id="d663e-163">![Edit Properties, General, Associate Edge pool](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>

4.  <span data-ttu-id="d663e-164">ドロップダウンボックスで、Lync Server 2013 エッジサーバーを選びます。</span><span class="sxs-lookup"><span data-stu-id="d663e-164">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>

5.  <span data-ttu-id="d663e-165">[ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d663e-165">Click **OK** to close the **Edit Properties** page.</span></span>

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="d663e-166">Lync Server 2013 Edge Server フェデレーションを有効にするには</span><span class="sxs-lookup"><span data-stu-id="d663e-166">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="d663e-167">[トポロジビルダー] の左側のウィンドウで、[ **Lync Server 2013** ] ノードに移動し、[ **Edge プール**] ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="d663e-167">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="d663e-168">ノードを展開し、表示されたエッジサーバーを右クリックして、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d663e-168">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d663e-169">フェデレーションは、1つのエッジプールに対してのみ有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d663e-169">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="d663e-170">エッジプールが複数ある場合は、フェデレーションエッジプールとして使用するためにいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="d663e-170">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>

    
    </div>

3.  <span data-ttu-id="d663e-171">[**全般**] ページで、[**このエッジプールのフェデレーションを有効にする (Port 5061)** ] 設定がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d663e-171">On the **General** page, verify the **Enable federation for this Edge pool (Port 5061)** setting is checked.</span></span>
    
    <span data-ttu-id="d663e-172">![[プロパティの編集] ダイアログの [全般] ページ](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "[プロパティの編集] ダイアログの [全般] ページ")</span><span class="sxs-lookup"><span data-stu-id="d663e-172">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

4.  <span data-ttu-id="d663e-173">[ **OK]** をクリックして、[プロパティの編集] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d663e-173">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="d663e-174">次に、サイトノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="d663e-174">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="d663e-175">サイトを右クリックし、[プロパティの**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d663e-175">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="d663e-176">左側のウィンドウで、[**フェデレーションルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d663e-176">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="d663e-177">[**サイトフェデレーションルートの割り当て**] で、[ **SIP フェデレーションを有効にする**] を選び、一覧から [Lync server 2013 Edge server] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d663e-177">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>
    
    <span data-ttu-id="d663e-178">![[プロパティの編集]、[フェデレーションルート] ページ](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "[プロパティの編集]、[フェデレーションルート] ページ")</span><span class="sxs-lookup"><span data-stu-id="d663e-178">![Edit Properties, Federation route page](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Edit Properties, Federation route page")</span></span>

9.  <span data-ttu-id="d663e-179">[ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d663e-179">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="d663e-180">複数サイト展開の場合は、各サイトでこの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d663e-180">For multi-site deployments, complete this procedure at each site.</span></span>

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="d663e-181">エッジサーバー構成の変更を公開するには</span><span class="sxs-lookup"><span data-stu-id="d663e-181">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="d663e-182">[**トポロジビルダー**] から、トップノードの**Lync サーバー**を選びます。</span><span class="sxs-lookup"><span data-stu-id="d663e-182">From **Topology Builder**, select the top node **Lync Server** .</span></span>

2.  <span data-ttu-id="d663e-183">[**アクション**] メニューで、[**トポロジの公開**] を選択し、ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="d663e-183">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="d663e-184">展開内のすべてのプールに対して Active Directory のレプリケーションが行われるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="d663e-184">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d663e-185">次のメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="d663e-185">You may see the following message:</span></span><BR><span data-ttu-id="d663e-186"><STRONG>警告: トポロジに複数のフェデレーションエッジサーバーが含まれています。これは、製品の最新バージョンへの移行中に発生する可能性があります。その場合は、1つのエッジサーバーのみがフェデレーションに対してアクティブに使用されます。外部 DNS SRV レコードが適切なエッジサーバーを指していることを確認します。複数のフェデレーションエッジサーバーを展開して同時にアクティブにするには (つまり、移行シナリオではなく)、すべてのフェデレーションパートナーが Lync Server を使用していることを確認します。外部 DNS SRV レコードに、すべてのフェデレーションが有効なエッジサーバーの一覧が表示されていることを確認します。</STRONG></span><span class="sxs-lookup"><span data-stu-id="d663e-186"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="d663e-187">この警告は予期されるものであり、無視しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="d663e-187">This warning is expected and can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="d663e-188">Lync Server 2013 エッジサーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="d663e-188">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="d663e-189">すべての Lync Server 2013 エッジサーバーをオンラインにします。</span><span class="sxs-lookup"><span data-stu-id="d663e-189">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="d663e-190">外部アクセス (通常はポート 443) およびフェデレーション (通常はポート 5061) の SIP トラフィックを、従来のエッジサーバーではなく、Lync Server 2013 エッジサーバーに送信するには、外部ファイアウォールルーティングルールまたはハードウェアロードバランサーの設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="d663e-190">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d663e-191">ハードウェアロードバランサーを持っていない場合は、新しい Lync Server アクセスエッジサーバーに解決するために、フェデレーション用の DNS A レコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d663e-191">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Lync Server Access Edge server.</span></span> <span data-ttu-id="d663e-192">これを最小限の中断で実現するには、外部の Lync server アクセスエッジ FQDN の TLL 値を減らして、新しい Lync Server アクセスエッジをポイントするように DNS が更新されたときに、フェデレーションおよびリモートアクセスがすぐに更新されるようにします。</span><span class="sxs-lookup"><span data-stu-id="d663e-192">To accomplish this with minimum disruption, reduce the TLL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge, federation and remote access will be updated quickly.</span></span>

    
    </div>

3.  <span data-ttu-id="d663e-193">次に、各エッジサーバーコンピューターから**Lync Server アクセスエッジ**を停止します。</span><span class="sxs-lookup"><span data-stu-id="d663e-193">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="d663e-194">各レガシエッジサーバーコンピューターで、[**管理ツール**] の [**サービス**] アプレットを開きます。</span><span class="sxs-lookup"><span data-stu-id="d663e-194">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="d663e-195">[サービス] リストで、[ **Lync Server Access Edge**] を見つけます。</span><span class="sxs-lookup"><span data-stu-id="d663e-195">In the services list, find **Lync Server Access Edge**.</span></span>

6.  <span data-ttu-id="d663e-196">[サービス名] を右クリックし、[**停止**] を選択してサービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="d663e-196">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="d663e-197">[スタートアップの種類を**無効**に設定します。</span><span class="sxs-lookup"><span data-stu-id="d663e-197">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="d663e-198">[ **OK** ] をクリックして、[**プロパティ**] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d663e-198">Click **OK** to close the **Properties** window.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

