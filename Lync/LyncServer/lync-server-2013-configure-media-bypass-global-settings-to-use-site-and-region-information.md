---
title: サイトと地域の情報を使用するためのメディアバイパスグローバル設定の構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4104a8892fd613b788862cf8a90db5fbef6c9f85
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152099"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a><span data-ttu-id="75006-102">サイトと地域の情報を使用するように Lync Server 2013 でメディアバイパスグローバル設定を構成する</span><span class="sxs-lookup"><span data-stu-id="75006-102">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75006-103">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="75006-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="75006-104">ここでは、仲介サーバーをバイパスするためのメディアを必要とする特定のサイトまたはサービス用に、仲介サーバーからピア (公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、またはインターネット テレフォニー サービス プロバイダー (ITSP) でのセッション ボーダー コントローラー (SBC)) へのトランク接続用のメディア バイパスが構成済みであることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="75006-104">This topic assumes that you have already configured media bypass for any trunk connections from the Mediation Server to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="75006-105">また、このトピックでは、「lync server <A href="lync-server-2013-create-or-modify-a-network-region.md">2013 でのネットワーク地域の作成</A>または変更」、「lync server <A href="lync-server-2013-create-or-modify-a-network-site.md">2013 でのネットワークサイトの作成または変更</A>」、および「lync server 2013 でのネットワークサイトへの<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">サブネットの関連付け</A>」の手順に従って、実行したネットワーク地域、ネットワークサイト、およびサブネット構成に一致するすべての中央サイトと</span><span class="sxs-lookup"><span data-stu-id="75006-105">This topic also assumes that you have defined all central sites and branch sites in Topology Builder in a way that matches the network region, network site, and subnet configuration that you performed according to the steps in <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>, and <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="75006-106">一致しない場合、メディア バイパスは成功しません。</span><span class="sxs-lookup"><span data-stu-id="75006-106">If they do not match, then media bypass will not succeed.</span></span>



</div>

<span data-ttu-id="75006-p102">ピアに関連付けられている個々のトランク接続でメディア パイパスを有効にするほか、グローバル設定も構成する必要があります。ここでのステップを使用してメディア バイパスのグローバル設定を構成する場合は、次の状況の一方または両方が構成に影響を与えることが前提となります。</span><span class="sxs-lookup"><span data-stu-id="75006-p102">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also configure global settings. If you use the steps in this topic to configure global settings for media bypass, the assumption is that one or both of the following situations affects your configuration:</span></span>

  - <span data-ttu-id="75006-109">Lync Server エンドポイントと、トランク接続でメディアバイパスを構成したすべてのピアとの間の接続が良好では*ありません*。</span><span class="sxs-lookup"><span data-stu-id="75006-109">You *do not* have good connectivity between Lync Server endpoints and any peers for which you configured media bypass on the trunk connection.</span></span>

  - <span data-ttu-id="75006-110">帯域幅管理の通話受付管理 (CAC) が有効です。</span><span class="sxs-lookup"><span data-stu-id="75006-110">Call admission control (CAC) for bandwidth management is enabled.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="75006-111">通話受付管理とメディアバイパスの両方の考慮事項の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-media-bypass-and-mediation-server.md">media バイパスおよび仲介2013サーバーのメディアバイパスと仲介サーバー</A> 」の「PSTN 接続の通話受付管理」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="75006-111">For details about the considerations for both call admission control and media bypass, see the "Call Admission Control of PSTN Connections" section in <A href="lync-server-2013-media-bypass-and-mediation-server.md">Media bypass and Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

<span data-ttu-id="75006-p103">ネットワーク地域およびネットワーク サイトの情報は、通話受付管理とメディア バイパスの高度なエンタープライズ VoIP 機能の間で (双方が有効な場合に) 共有されます。したがって、通話受付管理を構成済みの場合は、次の手順を使用してサイトと地域の情報をメディア バイパス用に特に編集する必要はありません。ネットワーク地域およびサイトで通話受付管理を構成しておらず、メディア バイパスの設定を変更したい場合は、この手順のステップを実行します。</span><span class="sxs-lookup"><span data-stu-id="75006-p103">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span>

<span data-ttu-id="75006-115">または、バイパスを決定するためにサイトと地域の情報を使用し、通話受付管理を有効にすることを意図していない場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="75006-115">Or, follow these steps if you want to use site and region information in making the bypass decision, but have no intention of enabling call admission control.</span></span> <span data-ttu-id="75006-116">このような場合は、「 [Lync Server 2013 でのネットワークサイト間ポリシーの作成](lync-server-2013-create-network-intersite-policies.md)」で説明されているように、帯域幅制限リンクをネットワークサイト間ポリシーで表現する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75006-116">In such a case, bandwidth restricted links will still need to be represented through network intersite policies, as described in [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span></span> <span data-ttu-id="75006-117">この例では、通話受付管理が有効になっていないため、実際の帯域幅制限は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="75006-117">The actual bandwidth constraints are not as important in this case, because call admission control has not been enabled.</span></span> <span data-ttu-id="75006-118">代わりに、これらのリンクを使用して、帯域幅制限を持たないサブネットを指定して、メディアバイパスを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="75006-118">Instead, these links are used to partition subnets to specify those that have no bandwidth limits and can, therefore, employ media bypass.</span></span> <span data-ttu-id="75006-119">通話受付管理とメディアバイパスが両方とも有効になっている場合は、この設定が true であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="75006-119">Note that this is also true when call admission control and media bypass are both enabled.</span></span>

<span data-ttu-id="75006-120">さらに、バイパスを適切に動作させるには、トポロジビルダーで定義されているサイトと、ネットワーク地域およびネットワークサイトを構成するときに定義されているように、サイト間で一貫性を保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="75006-120">Furthermore, for bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="75006-121">たとえば、PSTN ゲートウェイのみを展開するようにトポロジビルダーで定義したブランチサイトがある場合は、ブランチサイトのユーザーが pstn 通話を pstn 経由でルーティングできるようにするエンタープライズ Voip ポリシーを構成する必要があります。ブランチサイトのゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="75006-121">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="75006-122">メディア バイパスのサイトおよび地域情報を構成するには</span><span class="sxs-lookup"><span data-stu-id="75006-122">To Configure Site and Region Information for Media Bypass</span></span>

1.  <span data-ttu-id="75006-123">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="75006-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="75006-124">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75006-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="75006-125">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75006-125">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="75006-126">表の [**グローバル**] 構成をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="75006-126">Double-click the **Global** configuration in the table.</span></span>

4.  <span data-ttu-id="75006-127">[**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="75006-127">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="75006-128">[**サイトと地域の構成を使用する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75006-128">Click **Use sites and region configuration**.</span></span>

6.  <span data-ttu-id="75006-129">必要に応じて、[**マップされていないサイトのバイパスを有効にする**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="75006-129">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="75006-p107">このチェック ボックスは、帯域幅制限のない同一地域に関連付けられた 1 つまたは複数の大規模なサイト (大規模なセントラル サイトなど) があり、帯域幅制限がある同一地域に関連付けられたいくつかのブランチ サイトもある場合のみオンにします。マップされていないサイトのバイパスを有効にすると、すべてのサイトに関連付けられたすべてのサブネットを指定する必要がなく、ブランチ サイトに関連付けられたサブネットのみを指定するため、構成が効率的になります。通話受付管理が有効な場合は、このチェック ボックスをオンにしないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="75006-p107">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span>

    
    </div>

7.  <span data-ttu-id="75006-133">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75006-133">Click **Commit**.</span></span>

<span data-ttu-id="75006-134">次に、「 [Lync Server 2013 でのメディアバイパスのためにサブネットをネットワーク](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)サイトに関連付ける」の説明に従って、ネットワークサイトにサブネットを追加します。</span><span class="sxs-lookup"><span data-stu-id="75006-134">Next, add subnets to the network site, as described in [Associate subnets with network sites for media bypass in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span></span> <span data-ttu-id="75006-135">(サブネットをネットワークサイトに関連付けるための実際の手順については、「 [Lync Server 2013 でサブネットをネットワークサイトに関連付ける](lync-server-2013-associate-a-subnet-with-a-network-site.md)」を参照してください)。すべてのサブネットをネットワークサイトに関連付けると、メディアバイパスの展開が完了します。</span><span class="sxs-lookup"><span data-stu-id="75006-135">(The actual procedures for associating subnets with network sites are described in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) After you associate all subnets with network sites, media bypass deployment is complete.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="75006-136">ネットワーク地域とネットワーク サイトを作成していない場合は、メディア バイパスを展開する前にこれらを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75006-136">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="75006-137">詳細については、「lync <A href="lync-server-2013-create-or-modify-a-network-region.md">server 2013 でネットワーク地域を作成または変更</A>する」および「 <A href="lync-server-2013-create-or-modify-a-network-site.md">lync server 2013 でネットワークサイトを作成または変更</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75006-137">For details, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A> and <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="75006-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="75006-138">See Also</span></span>


[<span data-ttu-id="75006-139">Lync Server 2013 でのメディアバイパスのためにサブネットをネットワークサイトに関連付ける</span><span class="sxs-lookup"><span data-stu-id="75006-139">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

