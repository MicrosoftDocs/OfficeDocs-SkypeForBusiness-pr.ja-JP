---
title: フェデレーション ルートとメディア トラフィックを構成する
description: フェデレーションルートとメディアトラフィックを構成します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de26f472bddc504ff79e427b5243587f27020c3d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542983"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="07fab-103">フェデレーション ルートとメディア トラフィックを構成する</span><span class="sxs-lookup"><span data-stu-id="07fab-103">Configure federation routes and media traffic</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07fab-104">_**トピックの最終更新日:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="07fab-104">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="07fab-105">フェデレーションとは、別々の組織のユーザーがネットワーク境界を越えて通信することを許可する、複数の SIP ドメイン間での信頼関係のことです。</span><span class="sxs-lookup"><span data-stu-id="07fab-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="07fab-106">Lync Server 2013 パイロットプールに移行した後、lync server 2010 エッジサーバーのフェデレーションルートから Lync Server 2013 エッジサーバーのフェデレーションルートに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07fab-106">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Lync Server 2010 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="07fab-107">次の手順を使用して、Lync Server 2010 エッジサーバーおよびディレクターから Lync server 2013 エッジサーバーへのフェデレーションルートとメディアトラフィックルートを、単一サイト展開用に移行します。</span><span class="sxs-lookup"><span data-stu-id="07fab-107">Use the following procedures to transition the federation route and the media traffic route from your Lync Server 2010 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="07fab-108">フェデレーションルートとメディアトラフィックルートを変更するには、Lync Server 2013 および Lync Server 2010 エッジサーバーの保守のダウンタイムをスケジュールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="07fab-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Lync Server 2010 Edge Servers.</span></span> <span data-ttu-id="07fab-109">また、この移行プロセスで機能が停止している間は、フェデレーション アクセスも使用できません。</span><span class="sxs-lookup"><span data-stu-id="07fab-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="07fab-110">ダウンタイムは、ユーザー アクティビティが最も少ない時間帯に予定してください。</span><span class="sxs-lookup"><span data-stu-id="07fab-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="07fab-111">また、ダウンタイムが発生することをエンド ユーザーに知らせる必要もあります。</span><span class="sxs-lookup"><span data-stu-id="07fab-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="07fab-112">組織の事情に応じて停止を計画し、適切に対応してください。</span><span class="sxs-lookup"><span data-stu-id="07fab-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="07fab-113">従来の Lync Server 2010 エッジサーバーが、アクセスエッジサービス、Web 会議エッジサービス、および音声ビデオエッジサービスに同じ FQDN を使用するように構成されている場合、このセクションの手順はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="07fab-113">If your legacy Lync Server 2010 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="07fab-114">従来のエッジサービスが同じ FQDN を使用するように構成されている場合は、まず、すべてのユーザーを Lync server 2010 から Lync Server 2013 に移行してから、lync server の2013エッジサーバーでフェデレーションを有効にする前に、Lync server 2010 エッジサーバーを使用停止にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="07fab-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Lync Server 2010 to Lync Server 2013, then decommission the Lync Server 2010 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="07fab-115">XMPP フェデレーションが Lync server 2013 エッジサーバーを経由してルーティングされる場合、レガシ Lync Server 2010 ユーザーは、すべてのユーザーが Lync Server 2013 に移動され、XMPP ポリシーと証明書が構成され、XMPP フェデレーションパートナーが Lync Server 2013 で構成され、最後に DNS エントリが更新されるまで、XMPP フェデレーションパートナーと通信できません</span><span class="sxs-lookup"><span data-stu-id="07fab-115">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Lync Server 2010 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="07fab-116">Lync Server 2013 サイトから従来のフェデレーションの関連付けを削除するには</span><span class="sxs-lookup"><span data-stu-id="07fab-116">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="07fab-117">Lync Server 2013 フロントエンドサーバーで、トポロジビルダーで既存のトポロジを開きます。</span><span class="sxs-lookup"><span data-stu-id="07fab-117">On the Lync Server 2013 Front End server, open the existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="07fab-118">左ウィンドウで、**Lync Server** のすぐ下にあるサイト ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="07fab-118">In the left pane, navigate to the site node, which is located directly below **Lync Server**.</span></span>

3.  <span data-ttu-id="07fab-119">サイトを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07fab-119">Right-click the site and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="07fab-120">左ウィンドウで、[**フェデレーション ルート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="07fab-120">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="07fab-121">[ **サイトのフェデレーションルートの割り当て**] で、[ **SIP フェデレーションの有効化** ] チェックボックスをオフにして、従来の Lync Server 2010 環境を経由したフェデレーションルートを無効にします。</span><span class="sxs-lookup"><span data-stu-id="07fab-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy Lync Server 2010 environment.</span></span>
    
    <span data-ttu-id="07fab-122">![[プロパティの編集] ダイアログ、[フェデレーションルート] ページ](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "[プロパティの編集] ダイアログ、[フェデレーションルート] ページ")</span><span class="sxs-lookup"><span data-stu-id="07fab-122">![Edit Properties dialog, Federation route page](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>

6.  <span data-ttu-id="07fab-123">[**OK**] をクリックして、[プロパティの編集] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="07fab-123">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="07fab-124">[**トポロジ ビルダー**] で、最上位ノードの [**Lync Server**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="07fab-124">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="07fab-125">[**アクション**] メニューの [**トポロジの公開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07fab-125">From the **Action** menu, click **Publish Topology**.</span></span>

9.  <span data-ttu-id="07fab-126">[**次へ**] をクリックして公開プロセスを完了し、公開プロセスが完了したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07fab-126">Click **Next** to complete the publishing process and then click **Finish** when the publishing process has completed.</span></span>

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="07fab-127">従来のエッジ サーバーをフェデレーションされていないエッジ サーバーとして構成するには</span><span class="sxs-lookup"><span data-stu-id="07fab-127">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="07fab-128">左ウィンドウで、[**Lync Server 2010**] ノード、[**エッジ プール**] ノードの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="07fab-128">In the left pane, navigate to the **Lync Server 2010** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="07fab-129">エッジ サーバーを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07fab-129">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="07fab-130">左ウィンドウの [**全般**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="07fab-130">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="07fab-131">[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] チェック ボックス エントリをオフにし、[**OK**] をクリックしてページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="07fab-131">Clear the **Enable federation for this Edge pool (port 5061)** check box entry and select **OK** to close the page.</span></span>
    
    <span data-ttu-id="07fab-132">![プロパティの編集、全般、クリアフェデレーションの有効化](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "プロパティの編集、全般、クリアフェデレーションの有効化")</span><span class="sxs-lookup"><span data-stu-id="07fab-132">![Edit Properties, General, clear Enable federation](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Edit Properties, General, clear Enable federation")</span></span>

5.  <span data-ttu-id="07fab-133">[**操作**] メニューで [**トポロジの公開**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07fab-133">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="07fab-134">**公開ウィザード**の実行が完了したら、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="07fab-134">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="07fab-135">従来のエッジ サーバーのフェデレーションが無効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="07fab-135">Verify federation for the legacy Edge server is disabled.</span></span>
    
    <span data-ttu-id="07fab-136">![トポロジビルダー、エッジプール、フェデレーション無効化](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "トポロジビルダー、エッジプール、フェデレーション無効化")</span><span class="sxs-lookup"><span data-stu-id="07fab-136">![Topology Builder, Edge pool, federation disabled](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Topology Builder, Edge pool, federation disabled")</span></span>

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a><span data-ttu-id="07fab-137">Lync Server 2010 エッジ サーバーで証明書を構成するには</span><span class="sxs-lookup"><span data-stu-id="07fab-137">To configure certificates on the Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="07fab-138">従来の Lync Server 2010 エッジサーバーから、秘密キーを使用して外部アクセスプロキシ証明書をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="07fab-138">Export the external Access Proxy certificate, with the private key, from the legacy Lync Server 2010 Edge Server.</span></span>

2.  <span data-ttu-id="07fab-139">Lync Server 2013 エッジサーバーで、前の手順でアクセスプロキシの外部証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="07fab-139">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="07fab-140">エッジサーバーの Lync Server 2013 外部インターフェイスにアクセスプロキシの外部証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="07fab-140">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="07fab-141">Lync Server 2013 エッジサーバーの内部インターフェイス証明書は、信頼できる CA から要求され、割り当てられる必要があります。</span><span class="sxs-lookup"><span data-stu-id="07fab-141">The internal interface certificate of the Lync Server 2013 Edge Server should be requested from a trusted CA and assigned.</span></span>

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="07fab-142">Lync Server 2013 エッジ サーバーを使用するように Lync Server 2010 のフェデレーション ルートを変更するには</span><span class="sxs-lookup"><span data-stu-id="07fab-142">To change Lync Server 2010 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="07fab-143">トポロジ ビルダーの左ウィンドウで、[**Lync Server 2013**] ノード、[**エッジ プール**] ノードの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="07fab-143">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="07fab-144">エッジ サーバーを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07fab-144">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="07fab-145">左ウィンドウの [**全般**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="07fab-145">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="07fab-146">[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] のチェック ボックス エントリをオンにし、[**OK**] をクリックしてページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="07fab-146">Select the check box entry for **Enable federation for this Edge pool (port 5061)** and then click **OK** to close the page.</span></span>
    
    <span data-ttu-id="07fab-147">![[プロパティの編集] ダイアログの [全般] ページ](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "[プロパティの編集] ダイアログの [全般] ページ")</span><span class="sxs-lookup"><span data-stu-id="07fab-147">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

5.  <span data-ttu-id="07fab-148">[**操作**] メニューで [**トポロジの公開**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07fab-148">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="07fab-149">**公開ウィザード**の実行が完了したら、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="07fab-149">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="07fab-150">[**フェデレーション (ポート 5061)**] が [**有効**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="07fab-150">Verify **Federation (port 5061)** is set to **Enabled**.</span></span>
    
    <span data-ttu-id="07fab-151">![トポロジビルダー、エッジプール、フェデレーションの有効化](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "トポロジビルダー、エッジプール、フェデレーションの有効化")</span><span class="sxs-lookup"><span data-stu-id="07fab-151">![Topology Builder, Edge pool, Federation enabled](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Topology Builder, Edge pool, Federation enabled")</span></span>

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a><span data-ttu-id="07fab-152">Lync Server 2013 エッジ サーバーのフェデレーションの次ホップを更新するには</span><span class="sxs-lookup"><span data-stu-id="07fab-152">To update Lync Server 2013 Edge Server federation next hop</span></span>

1.  <span data-ttu-id="07fab-153">トポロジ ビルダーの左ウィンドウで、[**Lync Server 2013**] ノード、[**エッジ プール**] ノードの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="07fab-153">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="07fab-154">ノードを展開し、一覧内のエッジ サーバーを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07fab-154">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="07fab-155">[ **全般** ] ページの [ **次ホップの選択**] で、ドロップダウンリストから [Lync Server 2013] プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="07fab-155">On the **General** page, under **Next hop selection**, select from the drop-down list the Lync Server 2013  pool.</span></span>
    
    <span data-ttu-id="07fab-156">![[プロパティの編集] ダイアログ、[次ホップ] ページ](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "[プロパティの編集] ダイアログ、[次ホップ] ページ")</span><span class="sxs-lookup"><span data-stu-id="07fab-156">![Edit Properties dialog, Next hop page](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Edit Properties dialog, Next hop page")</span></span>

4.  <span data-ttu-id="07fab-157">[**OK**] をクリックして、[プロパティの編集] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="07fab-157">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="07fab-158">[ **トポロジビルダー**] で、最上位ノードの [ **Lync Server** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="07fab-158">From **Topology Builder**, select the top node **Lync Server** .</span></span>

6.  <span data-ttu-id="07fab-159">[**操作**] メニューで、[**トポロジの公開**] をクリックし、ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="07fab-159">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="07fab-160">Lync Server 2013 エッジ サーバーの送信メディア パスを構成するには</span><span class="sxs-lookup"><span data-stu-id="07fab-160">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="07fab-161">トポロジビルダーの左側のウィンドウで、[ **Lync Server 2013** ] ノードに移動してから、[ **Standard Edition フロントエンドサーバー** ] または [ **Enterprise Edition フロントエンドプール**] の下にあるプールに移動します。</span><span class="sxs-lookup"><span data-stu-id="07fab-161">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="07fab-162">プールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07fab-162">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="07fab-163">[**関連付け**] セクションで、[**エッジ プールの関連付け (メディア コンポーネント用)**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="07fab-163">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>
    
    <span data-ttu-id="07fab-164">![プロパティの編集、全般、エッジプールの関連付け](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "プロパティの編集、全般、エッジプールの関連付け")</span><span class="sxs-lookup"><span data-stu-id="07fab-164">![Edit Properties, General, Associate Edge pool](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>

4.  <span data-ttu-id="07fab-165">ドロップダウンボックスから、Lync Server 2013 エッジサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="07fab-165">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>

5.  <span data-ttu-id="07fab-166">[**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="07fab-166">Click **OK** to close the **Edit Properties** page.</span></span>

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="07fab-167">Lync Server 2013 エッジ サーバーのフェデレーションを有効にするには</span><span class="sxs-lookup"><span data-stu-id="07fab-167">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="07fab-168">トポロジ ビルダーの左ウィンドウで、[**Lync Server 2013**] ノード、[**エッジ プール**] ノードの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="07fab-168">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="07fab-169">ノードを展開し、一覧内のエッジ サーバーを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07fab-169">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="07fab-170">フェデレーションは、単一のエッジプールに対してのみ有効にできます。</span><span class="sxs-lookup"><span data-stu-id="07fab-170">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="07fab-171">エッジ プールが複数ある場合は、フェデレーション エッジ プールとして使用するエッジ プールを 1 つ選択してください。</span><span class="sxs-lookup"><span data-stu-id="07fab-171">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>

    
    </div>

3.  <span data-ttu-id="07fab-172">[**全般**] ページで、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] 設定がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="07fab-172">On the **General** page, verify the **Enable federation for this Edge pool (Port 5061)** setting is checked.</span></span>
    
    <span data-ttu-id="07fab-173">![[プロパティの編集] ダイアログの [全般] ページ](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "[プロパティの編集] ダイアログの [全般] ページ")</span><span class="sxs-lookup"><span data-stu-id="07fab-173">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

4.  <span data-ttu-id="07fab-174">[**OK**] をクリックして、[プロパティの編集] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="07fab-174">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="07fab-175">次に、サイト ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="07fab-175">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="07fab-176">サイトを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07fab-176">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="07fab-177">左ウィンドウで、[**フェデレーション ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07fab-177">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="07fab-178">[ **サイトのフェデレーションルートの割り当て**] で [ **SIP フェデレーションの有効化**] を選択し、一覧から [Lync server 2013 エッジサーバー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="07fab-178">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>
    
    <span data-ttu-id="07fab-179">![[プロパティの編集]、[フェデレーションルート] ページ](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "[プロパティの編集]、[フェデレーションルート] ページ")</span><span class="sxs-lookup"><span data-stu-id="07fab-179">![Edit Properties, Federation route page](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Edit Properties, Federation route page")</span></span>

9.  <span data-ttu-id="07fab-180">[**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="07fab-180">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="07fab-181">マルチサイト展開の場合は、この手順をサイトごとに実行します。</span><span class="sxs-lookup"><span data-stu-id="07fab-181">For multi-site deployments, complete this procedure at each site.</span></span>

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="07fab-182">エッジ サーバーの構成の変更を公開するには</span><span class="sxs-lookup"><span data-stu-id="07fab-182">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="07fab-183">[ **トポロジビルダー**] で、最上位ノードの [ **Lync Server** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="07fab-183">From **Topology Builder**, select the top node **Lync Server** .</span></span>

2.  <span data-ttu-id="07fab-184">[**操作**] メニューの [**トポロジの公開**] を選択し、ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="07fab-184">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="07fab-185">展開内のすべてのプールに対して Active Directory のレプリケーションが発生するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="07fab-185">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="07fab-186">次のメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="07fab-186">You may see the following message:</span></span><BR><span data-ttu-id="07fab-187"><STRONG>警告: 複数のフェデレーション エッジ サーバーがトポロジに含まれています。この状態は、新しいバージョンの製品への移行中に発生することがあります。その場合、1 つのエッジ サーバーのみがフェデレーション用に実際に使用されます。外部 DNS SRV レコードが正しいエッジ サーバーを指していることを確認してください。複数のフェデレーション エッジ サーバーを (移行シナリオ以外で) 同時にアクティブにして展開する場合は、すべてのフェデレーション パートナーが Lync Server を使用していることを確認してください。また、外部 DNS SRV レコードにすべてのフェデレーション対応エッジ サーバーがリストされていることを確認してください。</STRONG></span><span class="sxs-lookup"><span data-stu-id="07fab-187"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="07fab-188">この警告は予期されるものであり、無視してもかまいません。</span><span class="sxs-lookup"><span data-stu-id="07fab-188">This warning is expected and can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="07fab-189">Lync Server 2013 エッジ サーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="07fab-189">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="07fab-190">すべての Lync Server 2013 エッジサーバーをオンラインにします。</span><span class="sxs-lookup"><span data-stu-id="07fab-190">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="07fab-191">外部ファイアウォールのルーティングルールまたはロードバランサー機器の設定を更新して、外部アクセス (通常はポート 443) およびフェデレーション (通常はポート 5061) の SIP トラフィックを従来のエッジサーバーではなく Lync Server 2013 エッジサーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="07fab-191">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="07fab-p105">ハードウェア ロード バランサーがない場合は、フェデレーションの DNS A レコードを更新して、新しい Lync Server アクセス エッジ サーバーに解決する必要があります。混乱を最小限に抑えながらこれを実行するには、外部 Lync Server アクセス エッジ FQDN の TLL 値を減らして、DNS が新しい Lync Server アクセス エッジを指すように更新されたらフェデレーションとリモート アクセスが迅速に更新されるようにします。</span><span class="sxs-lookup"><span data-stu-id="07fab-p105">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Lync Server Access Edge server. To accomplish this with minimum disruption, reduce the TLL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge, federation and remote access will be updated quickly.</span></span>

    
    </div>

3.  <span data-ttu-id="07fab-194">次に、各エッジサーバーコンピューターから **Lync Server アクセスエッジ** を停止します。</span><span class="sxs-lookup"><span data-stu-id="07fab-194">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="07fab-195">従来の各エッジサーバーコンピューターから、[**管理ツール**] から [**サービス**] アプレットを開きます。</span><span class="sxs-lookup"><span data-stu-id="07fab-195">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="07fab-196">サービス リストで、[**Lync Server アクセス エッジ**] を見つけます。</span><span class="sxs-lookup"><span data-stu-id="07fab-196">In the services list, find **Lync Server Access Edge**.</span></span>

6.  <span data-ttu-id="07fab-197">サービス名を右クリックし、[**停止**] を選択してサービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="07fab-197">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="07fab-198">スタートアップの種類を [**無効**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="07fab-198">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="07fab-199">[**OK**] をクリックして、[**プロパティ**] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="07fab-199">Click **OK** to close the **Properties** window.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

