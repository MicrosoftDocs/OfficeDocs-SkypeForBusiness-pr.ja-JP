---
title: フェデレーション ルートとメディア トラフィックの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4542ae02cc72dfbac05dfa982e2fbda7f2924919
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840784"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="aaca3-102">フェデレーション ルートとメディア トラフィックの構成</span><span class="sxs-lookup"><span data-stu-id="aaca3-102">Configure federation routes and media traffic</span></span>

 


<span data-ttu-id="aaca3-103">フェデレーションは、2つ以上の SIP ドメイン間の信頼関係であり、別々の組織のユーザーがネットワーク境界を越えて通信することを許可します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-103">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="aaca3-104">Lync Server 2013 パイロットプールに移行した後、Microsoft Office Communications Server 2007 R2 Edge サーバーのフェデレーションルートから、Lync Server 2013 Edge サーバーのフェデレーションルートに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaca3-104">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Microsoft Office Communications Server 2007 R2 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="aaca3-105">次の手順に従って、フェデレーションルートとメディアトラフィックルートを Office Communications Server 2007 R2 Edge サーバーとディレクターから Lync Server 2013 Edge サーバーに移行して、単一サイト展開を行います。</span><span class="sxs-lookup"><span data-stu-id="aaca3-105">Use the procedures that follow to transition the federation route and the media traffic route from your Office Communications Server 2007 R2 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="aaca3-106">フェデレーションルートとメディアトラフィックルートを変更するには、Lync Server 2013 および Office Communications Server 2007 R2 Edge サーバーのメンテナンスダウンタイムをスケジュールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaca3-106">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Office Communications Server 2007 R2 Edge Servers.</span></span> <span data-ttu-id="aaca3-107">この切り替えプロセス全体は、停止期間中はフェデレーションアクセスを使用できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-107">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="aaca3-108">最小限のユーザーアクティビティが想定されている場合は、ダウンタイムのスケジュールを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaca3-108">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="aaca3-109">また、エンドユーザーに十分な通知も提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaca3-109">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="aaca3-110">この停止に応じて計画し、組織内で適切な期待を設定します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-110">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>




> [!IMPORTANT]  
> <span data-ttu-id="aaca3-111">従来の Office Communications Server 2007 R2 Edge サーバーが、アクセスエッジサービス、Web 会議エッジサービス、および A/V Edge サービスに同じ FQDN を使用するように構成されている場合は、このセクションの手順でフェデレーション設定を Lync サーバーに移行します。2013エッジサーバーはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="aaca3-111">If your legacy Office Communications Server 2007 R2 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section to transition the federation setting to a Lync Server 2013 Edge Server are not supported.</span></span> <span data-ttu-id="aaca3-112">従来のエッジサービスが同じ FQDN を使用するように構成されている場合は、まず、すべてのユーザーを Office Communications Server 2007 R2 から Lync Server 2013 に移行してから、フェデレーションを有効にする前に Office Communications Server 2007 R2 Edge サーバーを非コミッションにする必要があります。Lync Server 2013 エッジサーバー。</span><span class="sxs-lookup"><span data-stu-id="aaca3-112">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Office Communications Server 2007 R2 to Lync Server 2013, then decommission the Office Communications Server 2007 R2 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="aaca3-113">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aaca3-113">For details, see the following topics:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="aaca3-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Lync Server 2013 への残りのユーザーの移動</A></span><span class="sxs-lookup"><span data-stu-id="aaca3-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Move remaining users to Lync Server 2013</A></span></span></P>
> <LI>
> <P><span data-ttu-id="aaca3-115">"サーバーとサーバーの役割を削除する"<A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></span><span class="sxs-lookup"><span data-stu-id="aaca3-115">"Remove Servers and Server Roles" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></span></span></P></LI></UL>




> [!IMPORTANT]  
> <span data-ttu-id="aaca3-116">お使いの XMPP フェデレーションが Lync Server 2013 Edge サーバー経由でルーティングされている場合、従来の Office Communications Server 2007 R2 ユーザーは、すべてのユーザーが Lync Server 2013、XMPP ポリシー、および証明書が構成されていて、[XMPP フェデレーションパートナー] が Lync Server 2013 で構成されていて、最後に DNS エントリが更新されています。</span><span class="sxs-lookup"><span data-stu-id="aaca3-116">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Office Communications Server 2007 R2 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



<span data-ttu-id="aaca3-117">トポロジを正常に発行、有効化、または無効にするには、RTCUniversalServerAdmins および Domain Admins グループのメンバーであるユーザーとしてログインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaca3-117">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="aaca3-118">また、サーバーの役割を追加するための適切なユーザー権限と権限を委任することもできます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-118">It is also possible to delegate the proper user rights and permissions for adding server roles.</span></span> <span data-ttu-id="aaca3-119">詳細については、Standard Edition server または Enterprise Edition server 展開ドキュメントの「 [Lync server 2013 でのセットアップ権限の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aaca3-119">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="aaca3-120">その他の構成変更については、RTCUniversalServerAdmins グループのメンバーシップのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="aaca3-120">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="aaca3-121">Lync Server 2013 サイトから従来のフェデレーション関連付けを削除するには</span><span class="sxs-lookup"><span data-stu-id="aaca3-121">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="aaca3-122">トポロジビルダーを使用して、パイロットプールトポロジを開きます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-122">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="aaca3-123">左側のウィンドウで、サイトノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-123">In the left pane, navigate to the site node.</span></span>

3.  <span data-ttu-id="aaca3-124">サイトを右クリックし、[プロパティの**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-124">Right-click the site, and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="aaca3-125">左側のウィンドウで [**フェデレーションルート**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-125">Select **Federation route** in the left pane.</span></span>

5.  <span data-ttu-id="aaca3-126">[サイトフェデレーションルートの割り当て] で、[ **SIP フェデレーションを有効**にする] の横にあるチェックボックスをオフにして、 **BackCompatSite**経由でフェデレーションルートを無効にします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-126">Under Site federation route assignment, clear the check box next to **Enable SIP federation** to disable the federation route through the **BackCompatSite**.</span></span>
    
    <span data-ttu-id="aaca3-127">![[プロパティの編集] ダイアログ、フェデレーションルート](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "[プロパティの編集] ダイアログ、フェデレーションルート")</span><span class="sxs-lookup"><span data-stu-id="aaca3-127">![Edit Properties dialog, Federation route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Edit Properties dialog, Federation route")</span></span>

6.  <span data-ttu-id="aaca3-128">[ **OK]** をクリックして、[プロパティの編集] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-128">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="aaca3-129">[**トポロジビルダー**] から、トップノードの**Lync サーバー**を選びます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-129">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="aaca3-130">[**アクション**] メニューで、[**トポロジの発行**] をクリックしてウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-130">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="aaca3-131">レガシエッジサーバーを非フェデレーションエッジサーバーとして構成するには</span><span class="sxs-lookup"><span data-stu-id="aaca3-131">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="aaca3-132">**トポロジビルダー**から、[**アクション**] メニューの [ **Office Communications Server 2007 R2 トポロジの結合**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-132">From **Topology Builder**, from the **Action** menu click **Merge Office Communications Server 2007 R2 Topology**.</span></span>

2.  <span data-ttu-id="aaca3-133">[**次へ**] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-133">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="aaca3-134">[ **Edge セットアップの指定**] で、フェデレーション用に現在構成されている**エッジサーバーの内部 FQDN**を選択し、[**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-134">On the **Specify Edge Setup**, select the **Edge Server Internal FQDN** that is currently configured for federation, and then click **Change**.</span></span>
    
    <span data-ttu-id="aaca3-135">![OCS 2007 R2 トポロジの結合、エッジ設定の指定](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "OCS 2007 R2 トポロジの結合、エッジ設定の指定")</span><span class="sxs-lookup"><span data-stu-id="aaca3-135">![Merge OCS 2007 R2 Topology, Specify Edge Setup](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Merge OCS 2007 R2 Topology, Specify Edge Setup")</span></span>

4.  <span data-ttu-id="aaca3-136">[**次へ**] をクリックし、[**外部エッジの指定**] ページに移動するまで既定の設定をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-136">Click **Next** and accept the default settings until you get to the **Specify External Edge** page:</span></span>
    
    <span data-ttu-id="aaca3-137">![トポロジビルダーの外部エッジページを指定する](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "トポロジビルダーの外部エッジページを指定する")</span><span class="sxs-lookup"><span data-stu-id="aaca3-137">![Topology Builder Specify External Edge page](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topology Builder Specify External Edge page")</span></span>

5.  <span data-ttu-id="aaca3-138">[**外部エッジの指定**] で、[**このエッジプールをフェデレーションおよびパブリック IM 接続に使用する**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-138">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box.</span></span> <span data-ttu-id="aaca3-139">これにより、BackCompatSite とのフェデレーション関連付けが削除されます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-139">This will remove the federation association with the BackCompatSite.</span></span>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="aaca3-140">この手順は重要です。</span><span class="sxs-lookup"><span data-stu-id="aaca3-140">This step is important.</span></span> <span data-ttu-id="aaca3-141">従来のフェデレーションの関連付けを削除するには、このオプションをオフにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaca3-141">You must clear this option to remove the legacy federation association.</span></span>



6.  <span data-ttu-id="aaca3-142">[**次へ**] をクリックして、ウィザードの残りのページの既定の設定をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-142">Click **Next** and accept the default settings of the remaining pages of the wizard.</span></span>

7.  <span data-ttu-id="aaca3-143">[**概要**] で、[**次へ**] をクリックしてトポロジのマージを開始します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-143">In **Summary**, click **Next** to begin merging the topologies.</span></span>

8.  <span data-ttu-id="aaca3-144">[**状態**] 列で、値が**成功**していることを確認し、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-144">In the **Status** column, verify that the value is **Success**, and then click **Finish** to close the wizard.</span></span>

9.  <span data-ttu-id="aaca3-145">[**操作**] メニューで、[**発行トポロジ**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-145">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

10. <span data-ttu-id="aaca3-146">**発行ウィザード**が完了したら、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-146">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>
    
    <span data-ttu-id="aaca3-147">![マージ後にサイトが表示されたトポロジビルダー](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "マージ後にサイトが表示されたトポロジビルダー")</span><span class="sxs-lookup"><span data-stu-id="aaca3-147">![Topology Builder with site displayed after merge](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topology Builder with site displayed after merge")</span></span>
    
    <span data-ttu-id="aaca3-148">前の図に示すように、[**サイトフェデレーションルートの割り当て**] の下にある**SIP フェデレーション**は**無効**に設定されています。</span><span class="sxs-lookup"><span data-stu-id="aaca3-148">As shown in the previous figure, the **SIP federation** located under **Site federation route assignment** is set to **Disabled**.</span></span>

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="aaca3-149">Lync Server 2013 エッジサーバーで証明書を構成するには</span><span class="sxs-lookup"><span data-stu-id="aaca3-149">To configure certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="aaca3-150">従来の Office Communications Server 2007 R2 Edge サーバーから、秘密キーを持つ外部アクセスプロキシ証明書をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-150">Export the external Access Proxy certificate, with the private key, from the legacy Office Communications Server 2007 R2 Edge Server.</span></span>

2.  <span data-ttu-id="aaca3-151">Lync Server 2013 エッジサーバー上で、前の手順でアクセスプロキシの外部証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-151">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="aaca3-152">アクセスプロキシの外部証明書を、エッジサーバーの Lync Server 2013 外部インターフェイスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-152">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="aaca3-153">Lync Server 2013 Edge サーバーの内部インターフェイス証明書を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="aaca3-153">The internal interface certificate of the Lync Server 2013 Edge Server should not be changed.</span></span>

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="aaca3-154">Lync Server 2013 エッジサーバーを使用するように Office Communications Server 2007 R2 フェデレーションルートを変更するには</span><span class="sxs-lookup"><span data-stu-id="aaca3-154">To change Office Communications Server 2007 R2 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="aaca3-155">Office Communications Server 2007 R2 Standard Edition サーバーまたはフロントエンドサーバーで、Office Communications Server 2007 R2 管理ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-155">On the Office Communications Server 2007 R2 Standard Edition server or Front End Server, open the Office Communications Server 2007 R2 Administrative tool.</span></span>

2.  <span data-ttu-id="aaca3-156">左側のウィンドウで、最上位のノードを展開し、[**フォレスト**] ノードを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-156">In the left pane, expand the top node, and then right-click the **Forest** node.</span></span> <span data-ttu-id="aaca3-157">[**プロパティ**] を選択し、[**グローバルプロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-157">Select **Properties**, and then click **Global Properties**.</span></span>

3.  <span data-ttu-id="aaca3-158">[**フェデレーション**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-158">Click the **Federation** tab.</span></span>

4.  <span data-ttu-id="aaca3-159">フェデレーションおよびパブリック IM 接続を有効にするには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-159">Select the check box to enable federation and Public IM connectivity.</span></span>

5.  <span data-ttu-id="aaca3-160">Lync Server 2013 エッジサーバーの FQDN を入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-160">Enter the FQDN of the Lync Server 2013 Edge Server, and then click **OK**.</span></span>
    
    <span data-ttu-id="aaca3-161">![OCS グローバルプロパティの [フェデレーション] タブ](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS グローバルプロパティの [フェデレーション] タブ")</span><span class="sxs-lookup"><span data-stu-id="aaca3-161">![OCS Global Properties, Federation tab](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS Global Properties, Federation tab")</span></span>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="aaca3-162">Lync Server 2013 Edge Server フェデレーションを有効にするには</span><span class="sxs-lookup"><span data-stu-id="aaca3-162">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="aaca3-163">[トポロジビルダー] の左側のウィンドウで、[Lync Server 2013 **Edge プール**] ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-163">From Topology Builder, in the left pane, navigate to the Lync Server 2013 **Edge pools** node.</span></span>

2.  <span data-ttu-id="aaca3-164">ノードを展開し、表示されたエッジサーバーを右クリックして、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-164">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="aaca3-165">フェデレーションは、1つのエッジプールに対してのみ有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-165">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="aaca3-166">エッジプールが複数ある場合は、フェデレーションエッジプールとして使用するためにいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-166">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>



3.  <span data-ttu-id="aaca3-167">[**全般**] ページで、[**このエッジプールのフェデレーションを有効にする (Port 5061)** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-167">On the **General** page, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
    <span data-ttu-id="aaca3-168">![プロパティを編集する、一般に、エッジフェデレーションを有効にする](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "プロパティを編集する、一般に、エッジフェデレーションを有効にする")</span><span class="sxs-lookup"><span data-stu-id="aaca3-168">![Edit Properties, General, Enable Edge Federation](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Edit Properties, General, Enable Edge Federation")</span></span>

4.  <span data-ttu-id="aaca3-169">[ **OK]** をクリックして、[プロパティの編集] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-169">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="aaca3-170">次に、サイトノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-170">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="aaca3-171">サイトを右クリックし、[プロパティの**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-171">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="aaca3-172">左側のウィンドウで、[**フェデレーションルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-172">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="aaca3-173">[**サイトフェデレーションルートの割り当て**] で、[ **SIP フェデレーションを有効にする**] を選び、一覧から [Lync server 2013 Edge server] を選びます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-173">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>

9.  <span data-ttu-id="aaca3-174">[ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-174">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="aaca3-175">![[プロパティの編集]、[全般]、[Edge プールの関連付け]](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "[プロパティの編集]、[全般]、[Edge プールの関連付け")]</span><span class="sxs-lookup"><span data-stu-id="aaca3-175">![Edit Properties, General, Associate Edge pool](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>
    
    <span data-ttu-id="aaca3-176">複数サイト展開の場合は、各サイトでこの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-176">For multi-site deployments, complete this procedure at each site.</span></span>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="aaca3-177">Lync Server 2013 Edge Server の送信メディアパスを構成するには</span><span class="sxs-lookup"><span data-stu-id="aaca3-177">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="aaca3-178">[**トポロジビルダー**] から、 **Standard Edition のフロントエンドサーバー**または**Enterprise Edition のフロントエンドプール**の下にある Lync Server 2013 プールに移動します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-178">From **Topology Builder**, navigate to the Lync Server 2013 pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="aaca3-179">プールを右クリックし、[プロパティの**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-179">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="aaca3-180">[**関連付け**] セクションで、[ **Edge プールを関連付ける (メディアコンポーネント用)** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-180">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>

4.  <span data-ttu-id="aaca3-181">ドロップダウンボックスで、Lync Server 2013 エッジサーバーを選びます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-181">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>
    
    <span data-ttu-id="aaca3-182">![[プロパティの編集] ダイアログ、[Edge プールの関連付け]](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "[プロパティの編集] ダイアログ、[Edge プールの関連付け]")</span><span class="sxs-lookup"><span data-stu-id="aaca3-182">![Edit Properties dialog, Associate Edge Pool](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Edit Properties dialog, Associate Edge Pool")</span></span>

5.  <span data-ttu-id="aaca3-183">[ **OK]** をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-183">Click **OK** to close the **Edit Properties** page.</span></span>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="aaca3-184">エッジサーバー構成の変更を公開するには</span><span class="sxs-lookup"><span data-stu-id="aaca3-184">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="aaca3-185">[**トポロジビルダー**] から、トップノードの**Lync サーバー**を選びます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-185">From **Topology Builder**, select the top node **Lync Server**.</span></span>

2.  <span data-ttu-id="aaca3-186">[**アクション**] メニューで、[**トポロジの公開**] を選択し、ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-186">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="aaca3-187">展開内のすべてのプールに対して Active Directory のレプリケーションが行われるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-187">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="aaca3-188">次のメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="aaca3-188">You may see the following message:</span></span><BR><span data-ttu-id="aaca3-189"><STRONG>警告: トポロジに複数のフェデレーションエッジサーバーが含まれています。これは、製品の最新バージョンへの移行中に発生する可能性があります。その場合は、1つのエッジサーバーのみがフェデレーションに対してアクティブに使用されます。外部 DNS SRV レコードが適切なエッジサーバーを指していることを確認します。複数のフェデレーションエッジサーバーを展開して同時にアクティブにするには (つまり、移行シナリオではなく)、すべてのフェデレーションパートナーが Office Communications Server 2007 R2 または Lync Server を使用していることを確認します。外部 DNS SRV レコードに、すべてのフェデレーションが有効なエッジサーバーの一覧が表示されていることを確認します。</STRONG></span><span class="sxs-lookup"><span data-stu-id="aaca3-189"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Office Communications Server 2007 R2 or Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="aaca3-190">この警告は予期されるものであり、無視しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="aaca3-190">This warning is expected and can be safely ignored.</span></span>



## <a name="to-verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="aaca3-191">外部ユーザーのフェデレーションとリモートアクセスを確認するには</span><span class="sxs-lookup"><span data-stu-id="aaca3-191">To verify federation and remote access for external users</span></span>

1.  <span data-ttu-id="aaca3-192">Lync Server 2013 フロントエンドサーバーから、Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-192">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="aaca3-193">フェデレーションとリモートアクセスの状態を確認するには、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-193">To verify the status of federation and remote access, from the command line, type the following:</span></span>
    
        Get-CsAccessEdgeConfiguration

3.  <span data-ttu-id="aaca3-194">フェデレーションおよびリモートアクセスを有効にするには、コマンドラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-194">To enable federation and remote access, from the command line, type the following:</span></span>
    
        Set-CsAccessEdgeConfiguration
    
    <span data-ttu-id="aaca3-195">これらのコマンドレットの詳細については、次のトピックを参照してください。 [CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\))と[CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\))を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aaca3-195">For more information on these cmdlets, see the following topics: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) and [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).</span></span>

4.  <span data-ttu-id="aaca3-196">Lync Server 2013 エッジサーバーをオンラインにしてから、フェデレーションと外部アクセスをテストする前に、レプリケーションが完了するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-196">Wait until replication has completed before bringing the Lync Server 2013 Edge servers online, and testing federation and external access.</span></span>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="aaca3-197">Lync Server 2013 エッジサーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="aaca3-197">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="aaca3-198">すべての Lync Server 2013 エッジサーバーをオンラインにします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-198">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="aaca3-199">外部アクセス (通常はポート 443) およびフェデレーション (通常はポート 5061) の SIP トラフィックを、従来のエッジサーバーではなく、Lync Server 2013 エッジサーバーに送信するには、外部ファイアウォールルーティングルールまたはハードウェアロードバランサーの設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-199">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="aaca3-200">ハードウェアロードバランサーを持っていない場合は、新しい Lync Server アクセスエッジサーバーを解決するために、フェデレーション用の DNS A レコードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaca3-200">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server.</span></span> <span data-ttu-id="aaca3-201">これを最小限の中断で実現するには、外部の Lync Server アクセスエッジ FQDN の TTL 値を減らして、新しい Lync Server アクセスエッジサーバーをポイントするように DNS が更新されると、フェデレーションとリモートアクセスがすぐに更新されるようにします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-201">To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span></span>



3.  <span data-ttu-id="aaca3-202">次に、各エッジサーバーコンピューターから**Lync Server アクセスエッジ**を停止します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-202">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="aaca3-203">各レガシエッジサーバーコンピューターで、[**管理ツール**] の [**サービス**] アプレットを開きます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-203">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="aaca3-204">[サービス] ボックスの一覧で、[ **Office Communications Server アクセスエッジ**] を見つけます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-204">In the services list, find **Office Communications Server Access Edge**.</span></span>

6.  <span data-ttu-id="aaca3-205">[サービス名] を右クリックし、[**停止**] を選択してサービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-205">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="aaca3-206">[スタートアップの種類を**無効**に設定します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-206">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="aaca3-207">[ **OK** ] をクリックして、[**プロパティ**] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="aaca3-207">Click **OK** to close the **Properties** window.</span></span>

## <a name="to-test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="aaca3-208">外部ユーザーと外部アクセスの接続性をテストするには</span><span class="sxs-lookup"><span data-stu-id="aaca3-208">To Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="aaca3-209">少なくとも1つのフェデレーションドメインのユーザー。 Lync Server 2013 上の内部ユーザーと、Office Communications Server 2007 R2 上のユーザー。</span><span class="sxs-lookup"><span data-stu-id="aaca3-209">Users from at least one federated domain, an internal user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="aaca3-210">インスタントメッセージング (IM)、プレゼンス、音声/ビデオ (A/V)、デスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-210">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="aaca3-211">組織がサポートしている各パブリック IM サービスプロバイダーのユーザー (およびプロビジョニングが完了した場合) は、Lync Server 2013 および Office Communications Server 2007 R2 上のユーザーと通信します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-211">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="aaca3-212">匿名ユーザーが会議に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="aaca3-212">Verify anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="aaca3-213">Office Communications Server 2007 R2 でホストされているユーザー 2007 (リモートユーザーアクセス) を使って、Lync Server 2013、および Office Communications Server 2007 R2 上のユーザーとの間で、VPN を使用せずに office communications server R2 でホストされているユーザー。</span><span class="sxs-lookup"><span data-stu-id="aaca3-213">A user hosted on Office Communications Server 2007 R2 using remote user access (logging into Office Communications Server 2007 R2 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="aaca3-214">IM、プレゼンス、A/V、およびデスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-214">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="aaca3-215">Lync server 2013 でホストされているユーザー (イントラネットの外部から Lync server 2013 にログインしていますが、VPN を使用しません)。 Lync Server 2013、および Office Communications Server 2007 R2 上のユーザー。</span><span class="sxs-lookup"><span data-stu-id="aaca3-215">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="aaca3-216">IM、プレゼンス、A/V、およびデスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="aaca3-216">Test IM, presence, A/V, and desktop sharing.</span></span>

