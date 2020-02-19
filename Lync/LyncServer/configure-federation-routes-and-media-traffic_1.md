---
title: フェデレーション ルートとメディア トラフィックを構成する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fc7359a21d60c0c77028491af9fccdf21991c58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136094"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="daf16-102">フェデレーション ルートとメディア トラフィックを構成する</span><span class="sxs-lookup"><span data-stu-id="daf16-102">Configure federation routes and media traffic</span></span>

 


<span data-ttu-id="daf16-103">フェデレーションとは、別々の組織のユーザーがネットワーク境界を越えて通信することを許可する、複数の SIP ドメイン間での信頼関係のことです。</span><span class="sxs-lookup"><span data-stu-id="daf16-103">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="daf16-104">Lync Server 2013 パイロットプールに移行した後、Microsoft Office Communications Server 2007 R2 エッジサーバーのフェデレーションルートから Lync Server 2013 エッジサーバーのフェデレーションルートに移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="daf16-104">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Microsoft Office Communications Server 2007 R2 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="daf16-105">次の手順を使用して、Office Communications Server 2007 R2 エッジサーバーとディレクターから Lync Server 2013 エッジサーバーにフェデレーションルートとメディアトラフィックルートを移行し、単一サイトを展開します。</span><span class="sxs-lookup"><span data-stu-id="daf16-105">Use the procedures that follow to transition the federation route and the media traffic route from your Office Communications Server 2007 R2 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="daf16-106">フェデレーションルートとメディアトラフィックルートを変更するには、Lync Server 2013 および Office Communications Server 2007 R2 エッジサーバーのメンテナンスダウンタイムをスケジュールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="daf16-106">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Office Communications Server 2007 R2 Edge Servers.</span></span> <span data-ttu-id="daf16-107">また、この移行プロセスで機能が停止している間は、フェデレーション アクセスも使用できません。</span><span class="sxs-lookup"><span data-stu-id="daf16-107">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="daf16-108">ダウンタイムは、ユーザー アクティビティが最も少ない時間帯に予定してください。</span><span class="sxs-lookup"><span data-stu-id="daf16-108">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="daf16-109">また、ダウンタイムが発生することをエンド ユーザーに知らせる必要もあります。</span><span class="sxs-lookup"><span data-stu-id="daf16-109">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="daf16-110">組織の事情に応じて停止を計画し、適切に対応してください。</span><span class="sxs-lookup"><span data-stu-id="daf16-110">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>




> [!IMPORTANT]  
> <span data-ttu-id="daf16-111">従来の Office Communications Server 2007 R2 エッジサーバーが、アクセスエッジサービス、Web 会議エッジサービス、および音声ビデオエッジサービスに同じ FQDN を使用するように構成されている場合、このセクションの手順を使用して、フェデレーション設定を Lync Server 2013 エッジサーバーに移行することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="daf16-111">If your legacy Office Communications Server 2007 R2 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section to transition the federation setting to a Lync Server 2013 Edge Server are not supported.</span></span> <span data-ttu-id="daf16-112">従来のエッジサービスが同じ FQDN を使用するように構成されている場合は、まず、すべてのユーザーを Office Communications Server 2007 R2 から Lync Server 2013 に移行してから、Office Communications Server 2007 R2 エッジサーバーを使用停止してフェデレーションを有効にする必要があります。Lync Server 2013 エッジサーバー。</span><span class="sxs-lookup"><span data-stu-id="daf16-112">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Office Communications Server 2007 R2 to Lync Server 2013, then decommission the Office Communications Server 2007 R2 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="daf16-113">詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="daf16-113">For details, see the following topics:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="daf16-114"><A href="move-remaining-users-to-lync-server-2013_1.md">残りのユーザーを Lync Server 2013 に移動する</A></span><span class="sxs-lookup"><span data-stu-id="daf16-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Move remaining users to Lync Server 2013</A></span></span></P>
> <LI>
> <P><span data-ttu-id="daf16-115">「サーバーとサーバーの役割を削除する」<A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></span><span class="sxs-lookup"><span data-stu-id="daf16-115">"Remove Servers and Server Roles" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></span></span></P></LI></UL>




> [!IMPORTANT]  
> <span data-ttu-id="daf16-116">XMPP フェデレーションが Lync server 2013 エッジサーバーを経由してルーティングされている場合、従来の Office Communications Server 2007 R2 ユーザーは、すべてのユーザーが Lync Server 2013、XMPP ポリシー、および証明書が構成され、XMPP フェデレーションパートナーが Lync Server 2013 で構成されており、最後に DNS エントリが更新されています。</span><span class="sxs-lookup"><span data-stu-id="daf16-116">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Office Communications Server 2007 R2 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



<span data-ttu-id="daf16-117">サーバーの役割を追加または削除するときにトポロジを正常に公開、有効化、または無効化するには、RTCUniversalServerAdmins および Domain Admins グループのメンバーであるユーザーとしてログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="daf16-117">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="daf16-118">サーバーの役割を追加する適切なユーザー権限とアクセス許可を委任することもできます。</span><span class="sxs-lookup"><span data-stu-id="daf16-118">It is also possible to delegate the proper user rights and permissions for adding server roles.</span></span> <span data-ttu-id="daf16-119">詳細については、「Standard Edition サーバーまたは Enterprise Edition server 展開ドキュメント」の「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="daf16-119">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="daf16-120">他の構成変更の場合は、RTCUniversalServerAdmins グループのメンバーシップのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="daf16-120">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="daf16-121">Lync Server 2013 サイトから従来のフェデレーションの関連付けを削除するには</span><span class="sxs-lookup"><span data-stu-id="daf16-121">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="daf16-122">トポロジ ビルダーを使用してパイロット プールを開きます。</span><span class="sxs-lookup"><span data-stu-id="daf16-122">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="daf16-123">左ウィンドウで、サイト ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="daf16-123">In the left pane, navigate to the site node.</span></span>

3.  <span data-ttu-id="daf16-124">サイトを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="daf16-124">Right-click the site, and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="daf16-125">左ウィンドウの [**フェデレーション ルート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="daf16-125">Select **Federation route** in the left pane.</span></span>

5.  <span data-ttu-id="daf16-126">[サイトのフェデレーション ルートの割り当て] で、[**SIP フェデレーションの有効化**] の横のチェック ボックスをオフにして、[**BackCompatSite**] を経由するフェデレーション　ルートを無効にします。</span><span class="sxs-lookup"><span data-stu-id="daf16-126">Under Site federation route assignment, clear the check box next to **Enable SIP federation** to disable the federation route through the **BackCompatSite**.</span></span>
    
    <span data-ttu-id="daf16-127">![[プロパティの編集] ダイアログ、フェデレーションルート](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "[プロパティの編集] ダイアログ、フェデレーションルート")</span><span class="sxs-lookup"><span data-stu-id="daf16-127">![Edit Properties dialog, Federation route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Edit Properties dialog, Federation route")</span></span>

6.  <span data-ttu-id="daf16-128">[**OK**] をクリックして、[プロパティの編集] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="daf16-128">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="daf16-129">[**トポロジ ビルダー**] で、最上位ノードの [**Lync Server**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="daf16-129">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="daf16-130">[**操作**] メニューの [**トポロジの公開**] をクリックし、ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="daf16-130">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="daf16-131">従来のエッジ サーバーをフェデレーションされていないエッジ サーバーとして構成するには</span><span class="sxs-lookup"><span data-stu-id="daf16-131">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="daf16-132">[**トポロジ ビルダー**] の [**操作**] メニューの [**Office Communications Server 2007 R2 トポロジのマージ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="daf16-132">From **Topology Builder**, from the **Action** menu click **Merge Office Communications Server 2007 R2 Topology**.</span></span>

2.  <span data-ttu-id="daf16-133">[**次へ**] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="daf16-133">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="daf16-134">[**エッジ セットアップの指定**] で、フェデレーションに現在構成されている [**エッジ サーバーの内部 FQDN**] を選択し、[**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="daf16-134">On the **Specify Edge Setup**, select the **Edge Server Internal FQDN** that is currently configured for federation, and then click **Change**.</span></span>
    
    <span data-ttu-id="daf16-135">![OCS 2007 R2 トポロジのマージ、エッジセットアップの指定](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "OCS 2007 R2 トポロジのマージ、エッジセットアップの指定")</span><span class="sxs-lookup"><span data-stu-id="daf16-135">![Merge OCS 2007 R2 Topology, Specify Edge Setup](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Merge OCS 2007 R2 Topology, Specify Edge Setup")</span></span>

4.  <span data-ttu-id="daf16-136">[**次へ**] をクリックし、[**外部エッジの指定**] ページが表示されるまで既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="daf16-136">Click **Next** and accept the default settings until you get to the **Specify External Edge** page:</span></span>
    
    <span data-ttu-id="daf16-137">![トポロジビルダー、外部エッジページの指定](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "トポロジビルダー、外部エッジページの指定")</span><span class="sxs-lookup"><span data-stu-id="daf16-137">![Topology Builder Specify External Edge page](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topology Builder Specify External Edge page")</span></span>

5.  <span data-ttu-id="daf16-p105">[ \*\*外部エッジの指定 \*\*] で、[ \*\*このエッジ プールは、フェデレーションとパブリック IM 接続に使用します \*\*] チェック ボックスをオフにします。このチェック ボックスをオフにすると、BackCompatSite とのフェデレーションの関連付けが削除されます。</span><span class="sxs-lookup"><span data-stu-id="daf16-p105">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box. This will remove the federation association with the BackCompatSite.</span></span>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="daf16-p106">この手順は重要です。従来のフェデレーションの関連付けを削除するには、このチェック ボックスをオフにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="daf16-p106">This step is important. You must clear this option to remove the legacy federation association.</span></span>



6.  <span data-ttu-id="daf16-142">[**次へ**] をクリックし、ウィザードの残りのページで既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="daf16-142">Click **Next** and accept the default settings of the remaining pages of the wizard.</span></span>

7.  <span data-ttu-id="daf16-143">[**概要**] で、[**次へ**] をクリックしてトポロジのマージを開始します。</span><span class="sxs-lookup"><span data-stu-id="daf16-143">In **Summary**, click **Next** to begin merging the topologies.</span></span>

8.  <span data-ttu-id="daf16-144">[**状態**] 列で、値が "**成功**" になっていることを確認し、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="daf16-144">In the **Status** column, verify that the value is **Success**, and then click **Finish** to close the wizard.</span></span>

9.  <span data-ttu-id="daf16-145">[**操作**] メニューで [**トポロジの公開**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="daf16-145">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

10. <span data-ttu-id="daf16-146">**公開ウィザード**の実行が完了したら、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="daf16-146">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>
    
    <span data-ttu-id="daf16-147">![マージ後にサイトが表示されたトポロジビルダー](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "マージ後にサイトが表示されたトポロジビルダー")</span><span class="sxs-lookup"><span data-stu-id="daf16-147">![Topology Builder with site displayed after merge](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topology Builder with site displayed after merge")</span></span>
    
    <span data-ttu-id="daf16-148">前の図に示したように、[ **サイトのフェデレーション ルートの割り当て**] の [**SIP federation**] (SIP フェデレーション) は [**無効**] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="daf16-148">As shown in the previous figure, the **SIP federation** located under **Site federation route assignment** is set to **Disabled**.</span></span>

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="daf16-149">Lync Server 2013 エッジ サーバーで証明書を構成するには</span><span class="sxs-lookup"><span data-stu-id="daf16-149">To configure certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="daf16-150">従来の Office Communications Server 2007 R2 エッジサーバーから、秘密キーを使用して外部アクセスプロキシ証明書をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="daf16-150">Export the external Access Proxy certificate, with the private key, from the legacy Office Communications Server 2007 R2 Edge Server.</span></span>

2.  <span data-ttu-id="daf16-151">Lync Server 2013 エッジサーバーで、前の手順でアクセスプロキシの外部証明書をインポートします。</span><span class="sxs-lookup"><span data-stu-id="daf16-151">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="daf16-152">エッジサーバーの Lync Server 2013 外部インターフェイスにアクセスプロキシの外部証明書を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="daf16-152">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="daf16-153">Lync Server 2013 エッジサーバーの内部インターフェイス証明書は変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="daf16-153">The internal interface certificate of the Lync Server 2013 Edge Server should not be changed.</span></span>

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="daf16-154">Office Communications Server 2007 R2 フェデレーション ルートを変更して Lync Server 2013 エッジ サーバーを使用するには</span><span class="sxs-lookup"><span data-stu-id="daf16-154">To change Office Communications Server 2007 R2 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="daf16-155">Office Communications Server 2007 R2 Standard Edition サーバーまたはフロントエンドサーバーで、Office Communications Server 2007 R2 管理ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="daf16-155">On the Office Communications Server 2007 R2 Standard Edition server or Front End Server, open the Office Communications Server 2007 R2 Administrative tool.</span></span>

2.  <span data-ttu-id="daf16-p107">左ウィンドウで、最上位ノードを展開し、[ \*\*フォレスト \*\*] ノードを右クリックします。[ \*\*プロパティ \*\*] を選択し、[ \*\*グローバル プロパティ \*\*] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="daf16-p107">In the left pane, expand the top node, and then right-click the **Forest** node. Select **Properties**, and then click **Global Properties**.</span></span>

3.  <span data-ttu-id="daf16-158">[**フェデレーション**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="daf16-158">Click the **Federation** tab.</span></span>

4.  <span data-ttu-id="daf16-159">チェック ボックスをオンにして、フェデレーションとパブリック IM 接続を有効にします。</span><span class="sxs-lookup"><span data-stu-id="daf16-159">Select the check box to enable federation and Public IM connectivity.</span></span>

5.  <span data-ttu-id="daf16-160">Lync Server 2013 エッジサーバーの FQDN を入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="daf16-160">Enter the FQDN of the Lync Server 2013 Edge Server, and then click **OK**.</span></span>
    
    <span data-ttu-id="daf16-161">![OCS の [グローバルプロパティ]、[フェデレーション] タブ](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS の [グローバルプロパティ]、[フェデレーション] タブ")</span><span class="sxs-lookup"><span data-stu-id="daf16-161">![OCS Global Properties, Federation tab](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS Global Properties, Federation tab")</span></span>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="daf16-162">Lync Server 2013 エッジ サーバーのフェデレーションを有効にするには</span><span class="sxs-lookup"><span data-stu-id="daf16-162">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="daf16-163">トポロジビルダーの左側のウィンドウで、[Lync Server 2013**エッジプール**] ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="daf16-163">From Topology Builder, in the left pane, navigate to the Lync Server 2013 **Edge pools** node.</span></span>

2.  <span data-ttu-id="daf16-164">ノードを展開し、一覧内のエッジ サーバーを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="daf16-164">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="daf16-165">フェデレーションは、単一のエッジプールに対してのみ有効にできます。</span><span class="sxs-lookup"><span data-stu-id="daf16-165">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="daf16-166">エッジ プールが複数ある場合は、フェデレーション エッジ プールとして使用するエッジ プールを 1 つ選択してください。</span><span class="sxs-lookup"><span data-stu-id="daf16-166">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>



3.  <span data-ttu-id="daf16-167">[**全般**] ページで、[**このエッジ プールのフェデレーションの有効化 (ポート 5061)**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="daf16-167">On the **General** page, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
    <span data-ttu-id="daf16-168">![プロパティを編集、全般、エッジフェデレーションを有効にする](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "プロパティを編集、全般、エッジフェデレーションを有効にする")</span><span class="sxs-lookup"><span data-stu-id="daf16-168">![Edit Properties, General, Enable Edge Federation](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Edit Properties, General, Enable Edge Federation")</span></span>

4.  <span data-ttu-id="daf16-169">[**OK**] をクリックして、[プロパティの編集] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="daf16-169">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="daf16-170">次に、サイト ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="daf16-170">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="daf16-171">サイトを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="daf16-171">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="daf16-172">左ウィンドウで、[**フェデレーション ルート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="daf16-172">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="daf16-173">[**サイトのフェデレーションルートの割り当て**] で [ **SIP フェデレーションの有効化**] を選択し、一覧から [Lync server 2013 エッジサーバー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="daf16-173">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>

9.  <span data-ttu-id="daf16-174">[**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="daf16-174">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="daf16-175">![プロパティの編集、全般、エッジプールの関連付け](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "プロパティの編集、全般、エッジプールの関連付け")</span><span class="sxs-lookup"><span data-stu-id="daf16-175">![Edit Properties, General, Associate Edge pool](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>
    
    <span data-ttu-id="daf16-176">マルチサイト展開の場合は、この手順をサイトごとに実行します。</span><span class="sxs-lookup"><span data-stu-id="daf16-176">For multi-site deployments, complete this procedure at each site.</span></span>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="daf16-177">Lync Server 2013 エッジ サーバーの送信メディア パスを構成するには</span><span class="sxs-lookup"><span data-stu-id="daf16-177">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="daf16-178">**トポロジビルダー**で、[ **Standard Edition フロントエンドサーバー** ] または [ **Enterprise Edition フロントエンドプール**] の下にある Lync Server 2013 プールに移動します。</span><span class="sxs-lookup"><span data-stu-id="daf16-178">From **Topology Builder**, navigate to the Lync Server 2013 pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="daf16-179">プールを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="daf16-179">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="daf16-180">[**関連付け**] セクションで、[**エッジ プールの関連付け (メディア コンポーネント用)**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="daf16-180">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>

4.  <span data-ttu-id="daf16-181">ドロップダウンボックスから、Lync Server 2013 エッジサーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="daf16-181">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>
    
    <span data-ttu-id="daf16-182">![[プロパティの編集] ダイアログ、エッジプールの関連付け](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "[プロパティの編集] ダイアログ、エッジプールの関連付け")</span><span class="sxs-lookup"><span data-stu-id="daf16-182">![Edit Properties dialog, Associate Edge Pool](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Edit Properties dialog, Associate Edge Pool")</span></span>

5.  <span data-ttu-id="daf16-183">[**OK**] をクリックして、[**プロパティの編集**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="daf16-183">Click **OK** to close the **Edit Properties** page.</span></span>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="daf16-184">エッジ サーバーの構成の変更を公開するには</span><span class="sxs-lookup"><span data-stu-id="daf16-184">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="daf16-185">[**トポロジ ビルダー**] で、最上位ノードの [**Lync Server**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="daf16-185">From **Topology Builder**, select the top node **Lync Server**.</span></span>

2.  <span data-ttu-id="daf16-186">[**操作**] メニューの [**トポロジの公開**] を選択し、ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="daf16-186">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="daf16-187">展開内のすべてのプールに対して Active Directory のレプリケーションが発生するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="daf16-187">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="daf16-188">次のメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="daf16-188">You may see the following message:</span></span><BR><span data-ttu-id="daf16-189"><STRONG>警告: 複数のフェデレーション エッジ サーバーがトポロジに含まれています。この状態は、最新バージョンの製品への移行中に発生することがあります。その場合、1 つのエッジ サーバーのみがフェデレーション用に実際に使用されます。外部 DNS SRV レコードが正しいエッジ サーバーを指していることを確認してください。複数のフェデレーション エッジ サーバーを (移行シナリオ以外で) 同時にアクティブにして展開する場合は、すべてのフェデレーション パートナーが Office Communications Server 2007 R2 または Lync Server を使用していることを確認してください。また、外部 DNS SRV レコードにすべてのフェデレーション対応エッジ サーバーがリストされていることを確認してください。 </STRONG></span><span class="sxs-lookup"><span data-stu-id="daf16-189"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Office Communications Server 2007 R2 or Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="daf16-190">この警告は予期されるものであり、無視してもかまいません。</span><span class="sxs-lookup"><span data-stu-id="daf16-190">This warning is expected and can be safely ignored.</span></span>



## <a name="to-verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="daf16-191">外部ユーザーのフェデレーションとリモート アクセスを確認するには</span><span class="sxs-lookup"><span data-stu-id="daf16-191">To verify federation and remote access for external users</span></span>

1.  <span data-ttu-id="daf16-192">Lync Server 2013 フロントエンドサーバーから、Lync Server 管理シェルを開きます。</span><span class="sxs-lookup"><span data-stu-id="daf16-192">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="daf16-193">フェデレーションとリモート アクセスの状態を確認するには、コマンド ラインから次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="daf16-193">To verify the status of federation and remote access, from the command line, type the following:</span></span>
    
        Get-CsAccessEdgeConfiguration

3.  <span data-ttu-id="daf16-194">フェデレーションとリモート アクセスを有効化するには、コマンド ラインから次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="daf16-194">To enable federation and remote access, from the command line, type the following:</span></span>
    
        Set-CsAccessEdgeConfiguration
    
    <span data-ttu-id="daf16-195">これらのコマンドレットの詳細については、以下のトピックを参照してください。 [set-csaccessedgeconfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\))および[set-csaccessedgeconfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="daf16-195">For more information on these cmdlets, see the following topics: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) and [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\)).</span></span>

4.  <span data-ttu-id="daf16-196">Lync Server 2013 エッジサーバーをオンラインにし、フェデレーションと外部アクセスをテストする前に、レプリケーションが完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="daf16-196">Wait until replication has completed before bringing the Lync Server 2013 Edge servers online, and testing federation and external access.</span></span>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="daf16-197">Lync Server 2013 エッジ サーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="daf16-197">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="daf16-198">すべての Lync Server 2013 エッジサーバーをオンラインにします。</span><span class="sxs-lookup"><span data-stu-id="daf16-198">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="daf16-199">外部ファイアウォールのルーティングルールまたはロードバランサー機器の設定を更新して、外部アクセス (通常はポート 443) およびフェデレーション (通常はポート 5061) の SIP トラフィックを従来のエッジサーバーではなく Lync Server 2013 エッジサーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="daf16-199">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="daf16-p109">ロード バランサ機器がない場合は、フェデレーションの DNS A レコードを更新して、新しい Lync Server アクセス エッジ サーバーを解決する必要があります。中断を最低限にしてこれを行うためには、外部の Lync Server アクセス エッジ FQDN の TTL 値を下げておきます。すると、DNS が更新されて新しい Lync Server アクセス エッジ サーバーを示すようになったとき、フェデレーションとリモート アクセスが速やかに更新されます。</span><span class="sxs-lookup"><span data-stu-id="daf16-p109">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server. To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span></span>



3.  <span data-ttu-id="daf16-202">次に、各エッジサーバーコンピューターから**Lync Server アクセスエッジ**を停止します。</span><span class="sxs-lookup"><span data-stu-id="daf16-202">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="daf16-203">従来の各エッジサーバーコンピューターから、[**管理ツール**] から [**サービス**] アプレットを開きます。</span><span class="sxs-lookup"><span data-stu-id="daf16-203">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="daf16-204">サービス リストで、[**Office Communications Server アクセス エッジ**] を見つけます。</span><span class="sxs-lookup"><span data-stu-id="daf16-204">In the services list, find **Office Communications Server Access Edge**.</span></span>

6.  <span data-ttu-id="daf16-205">サービス名を右クリックし、[**停止**] を選択してサービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="daf16-205">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="daf16-206">スタートアップの種類を [**無効**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="daf16-206">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="daf16-207">[**OK**] をクリックして、[**プロパティ**] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="daf16-207">Click **OK** to close the **Properties** window.</span></span>

## <a name="to-test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="daf16-208">外部ユーザーの接続と外部アクセスをテストするには</span><span class="sxs-lookup"><span data-stu-id="daf16-208">To Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="daf16-209">少なくとも1つのフェデレーションドメインのユーザー。 Lync Server 2013 上の内部ユーザーと Office Communications Server 2007 R2 のユーザー。</span><span class="sxs-lookup"><span data-stu-id="daf16-209">Users from at least one federated domain, an internal user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="daf16-210">インスタント メッセージング (IM)、プレゼンス、音声ビデオ (A/V)、およびデスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="daf16-210">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="daf16-211">組織がサポート (およびプロビジョニングが完了) している各パブリック IM サービスプロバイダーのユーザーが、Lync Server 2013 上のユーザーおよび Office Communications Server 2007 R2 上のユーザーと通信します。</span><span class="sxs-lookup"><span data-stu-id="daf16-211">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="daf16-212">匿名ユーザーが会議に参加できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daf16-212">Verify anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="daf16-213">リモートユーザーアクセスを使用して Office Communications Server 2007 R2 でホストされているユーザー (Office Communications Server 2007 R2 から VPN を使用しない)、Lync Server 2013 のユーザー、および Office Communications Server 2007 R2 上のユーザー。</span><span class="sxs-lookup"><span data-stu-id="daf16-213">A user hosted on Office Communications Server 2007 R2 using remote user access (logging into Office Communications Server 2007 R2 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="daf16-214">IM、プレゼンス、A/V、およびデスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="daf16-214">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="daf16-215">Lync server 2013 上のユーザーと、Office Communications Server 2007 R2 上のユーザーとのリモートユーザーアクセスを使用して、Lync server 2013 でホストされているユーザー (イントラネットの外部からの Lync Server 2013 へのログイン、および VPN を使用しない)。</span><span class="sxs-lookup"><span data-stu-id="daf16-215">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="daf16-216">IM、プレゼンス、A/V、およびデスクトップ共有をテストします。</span><span class="sxs-lookup"><span data-stu-id="daf16-216">Test IM, presence, A/V, and desktop sharing.</span></span>

