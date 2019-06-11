---
title: 'Lync Server 2013: 高度なエンタープライズ Voip 機能のネットワーク設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d633d111e9df09cde57b91f32f4592b7f80c9f26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="3e7d8-102">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e7d8-102">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e7d8-103">_**最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="3e7d8-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="3e7d8-104">Lync Server には、通話受付制御 (CAC)、緊急サービス (E9)、メディアバイパスという3つの高度なエンタープライズ Voip 機能があります。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-104">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="3e7d8-105">これらの機能は、ネットワークサイトを使用して、Lync Server トポロジのネットワーク領域、ネットワークサイト、および各サブネットの特定の構成要件を共有します。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-105">These features share certain configuration requirements for network regions, network sites, and association of each subnet in the Lync Server topology with a network site.</span></span> <span data-ttu-id="3e7d8-106">これらの機能の展開の計画について詳しくは、以下をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-106">For details about planning for deployment of these features, see:</span></span>

  - [<span data-ttu-id="3e7d8-107">Lync Server 2013 での通話受付管理の計画</span><span class="sxs-lookup"><span data-stu-id="3e7d8-107">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="3e7d8-108">Lync Server 2013 での緊急サービス (E9-1-1) の計画</span><span class="sxs-lookup"><span data-stu-id="3e7d8-108">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="3e7d8-109">Lync Server 2013 でのメディア バイパスの計画</span><span class="sxs-lookup"><span data-stu-id="3e7d8-109">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

<span data-ttu-id="3e7d8-110">これらの各機能の展開の詳細については、展開ドキュメントの「 [Lync Server 2013 での高度なエンタープライズ voip 機能の展開](lync-server-2013-deploying-advanced-enterprise-voice-features.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-110">For details about deploying each of these features, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) in the Deployment documentation.</span></span>

<span data-ttu-id="3e7d8-111">このトピックでは、3つの高度なエンタープライズボイス機能すべてに共通する構成要件の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-111">This topic provides an overview of the configuration requirements that are common to all three advanced Enterprise Voice features.</span></span>

<div>

## <a name="network-regions"></a><span data-ttu-id="3e7d8-112">ネットワーク地域</span><span class="sxs-lookup"><span data-stu-id="3e7d8-112">Network Regions</span></span>

<span data-ttu-id="3e7d8-113">ネットワーク地域は、通話受付管理 (CAC)、E9-1-1、およびメディア バイパスの構成でのみ使用されるネットワーク ハブまたはネットワーク バックボーンです。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-113">A network region is a network hub or network backbone used only in the configuration of call admission control (CAC), E9-1-1, and media bypass.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3e7d8-114">ネットワーク領域は、Lync Server のダイヤルイン会議領域と同じではありません。これは、ダイヤルイン会議アクセス番号を1つまたは複数の Lync Server ダイヤルプランに関連付けるために必要となります。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-114">Network regions are not the same as Lync Server dial-in conferencing regions, which are required to associate dial-in conferencing access numbers with one or more Lync Server dial plans.</span></span> <span data-ttu-id="3e7d8-115">ダイヤルイン会議の地域の詳細については、計画ドキュメントの「 <A href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 でのダイヤルイン会議の要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-115">For details about dial-in conferencing regions, see <A href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="3e7d8-116">CAC では、すべてのネットワーク領域に、その地域内のメディアトラフィックを管理する関連付けられた Lync Server セントラルサイトが必要です (つまり、構成したポリシーに基づいて、リアルタイムの音声またはビデオセッションが可能かどうかに関する決定が行われます)。確立されます)。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-116">CAC requires that every network region have an associated Lync Server central site, which manages media traffic within the region (that is, it makes decisions based on policies that you have configured, regarding whether or not a real-time audio or video session can be established).</span></span> <span data-ttu-id="3e7d8-117">Lync Server のセントラルサイトは、地理的な場所を示すのではなく、プールまたは一連のプールとして構成されているサーバーの論理グループを表します。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-117">Lync Server central sites do not represent geographical locations, but rather logical groups of servers that are configured as a pool or a set of pools.</span></span> <span data-ttu-id="3e7d8-118">セントラルサイトの詳細については、計画ドキュメントの「 [Lync Server 2013 のリファレンストポロジ](lync-server-2013-reference-topologies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-118">For details about central sites, see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="3e7d8-119">[サポートされているトポロジ](lync-server-2013-supported-topologies.md)については、サポートドキュメントの「Lync Server 2013」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-119">Also see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md) in the Supportability documentation.</span></span>

<span data-ttu-id="3e7d8-120">ネットワークの領域を構成するには、Lync Server コントロールパネルの [**ネットワーク構成**] セクションの [**地域**] タブを使用するか、または、**新しい (** Csnetworkregion) lync Server 管理シェルを実行します。 \*\*\*\* cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3e7d8-120">To configure a network region, you can either use the **Regions** tab on the **Network Configuration** section of Lync Server Control Panel, or run the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="3e7d8-121">手順については、展開ドキュメントの「 [Lync server 2013 でネットワーク領域を作成または変更](lync-server-2013-create-or-modify-a-network-region.md)する」を参照するか、「Lync Server 管理シェルのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-121">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

<span data-ttu-id="3e7d8-122">同じネットワーク領域の定義は、3つの高度なエンタープライズ音声機能によって共有されます。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-122">The same network region definitions are shared by all three advanced Enterprise Voice features.</span></span> <span data-ttu-id="3e7d8-123">いずれかの機能にネットワーク地域を既に作成している場合、他の機能に新しいネットワーク地域を作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-123">If you have already created network regions for one feature, you do not need to create new network regions for the other features.</span></span> <span data-ttu-id="3e7d8-124">ただし、機能固有の設定を適用するために、既存のネットワーク地域定義を変更することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-124">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="3e7d8-125">たとえば、E9-1-1 (関連付けられた中央サイトは不要) にネットワーク地域を作成しており、通話受付管理を後で展開する場合、中央サイトを指定するには、各ネットワーク地域定義を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-125">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and, later, you deploy call admission control, you must modify each of the network region definitions to specify a central site.</span></span>

<span data-ttu-id="3e7d8-126">Lync Server のセントラルサイトをネットワーク領域と関連付けるには、Lync Server コントロールパネルの [**ネットワーク構成**] セクションを使用するか、または**新しい**csnetworkregion を実行するか、またはをセットアップして、[セントラルサイト名] を指定します。 \*\*\*\* Lync Server Management Shell コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-126">To associate a Lync Server central site with a network region, you specify the central site name, either by using the **Network Configuration** section of Lync Server Control Panel, or by running the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="3e7d8-127">手順については、展開ドキュメントの「 [Lync server 2013 でネットワーク領域を作成または変更](lync-server-2013-create-or-modify-a-network-region.md)する」を参照するか、「Lync Server 管理シェルのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-127">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="network-sites"></a><span data-ttu-id="3e7d8-128">ネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="3e7d8-128">Network Sites</span></span>

<span data-ttu-id="3e7d8-p107">ネットワーク サイトは、ブランチ オフィス、支社、本社などの地理的場所を表します。各ネットワーク サイトは、特定のネットワーク地域に関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-p107">A network site represents a geographical location, such as a branch office, a regional office, or a main office. Each network site must be associated with a specific network region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3e7d8-131">ネットワークサイトは、高度なエンタープライズ Voip 機能によってのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-131">Network sites are used only by the advanced Enterprise Voice features.</span></span> <span data-ttu-id="3e7d8-132">Lync Server トポロジで構成したブランチサイトとは異なります。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-132">They are not the same as the branch sites that you configure in your Lync Server topology.</span></span> <span data-ttu-id="3e7d8-133">ブランチサイトの詳細については、計画ドキュメントの「 <A href="lync-server-2013-reference-topologies.md">Lync Server 2013 のリファレンストポロジ</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-133">For details about branch sites, see <A href="lync-server-2013-reference-topologies.md">Reference topologies in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="3e7d8-134"><A href="lync-server-2013-supported-topologies.md">サポートされているトポロジ</A>については、サポートドキュメントの「Lync Server 2013」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-134">Also see <A href="lync-server-2013-supported-topologies.md">Supported topologies in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="3e7d8-135">ネットワークサイトを構成し、ネットワーク領域に関連付けるには、Lync Server コントロールパネルの [**ネットワーク構成**] セクションを使用するか、または Lync Server 管理シェルの [**新しい-** csnetworksite] または [ **Set-csnetworksite** ] を実行します。cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3e7d8-135">To configure a network site and associate it with a network region, you can either use the **Network Configuration** section of Lync Server Control Panel, or run the Lync Server Management Shell **New-CsNetworkSite** or **Set-CsNetworkSite** cmdlets.</span></span> <span data-ttu-id="3e7d8-136">詳細については、展開ドキュメントの「 [Lync server 2013 でネットワークサイトを作成または変更](lync-server-2013-create-or-modify-a-network-site.md)する」を参照するか、「Lync Server 管理シェルのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-136">For details, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="3e7d8-137">IP サブネットの特定</span><span class="sxs-lookup"><span data-stu-id="3e7d8-137">Identify IP Subnets</span></span>

<span data-ttu-id="3e7d8-p110">ネットワーク管理者と連携して各ネットワーク サイトに割り当てる IP サブネットを決定する必要があります。ネットワーク管理者が既に IP サブネットをネットワーク地域およびネットワーク サイトに分類している場合、作業は大幅に簡略化されます。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-p110">For each network site, you will need to work with your network administrator to determine which IP subnets are assigned to each network site. If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="3e7d8-p111">この例では、North America 地域の New York サイトに 172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24 の IP サブネットを割り当てることができます。通常はデトロイトで仕事をしている Bob が、トレーニングのためにニューヨークのオフィスに出張する場合、コンピューターを起動してネットワークに接続すると、New York に割り当てられている 4 つの範囲のいずれか (172.29.80.103 など) の IP アドレスがコンピューターで取得されます。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-p111">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York—for example, 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="3e7d8-142">サーバー上のネットワーク構成中に指定された IP サブネットは、メディアのバイパスに適切に使用するために、クライアントコンピューターによって提供される形式と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-142">The IP subnets specified during network configuration on the server must match the format that is provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="3e7d8-143">Lync クライアントはローカルの IP アドレスを受け取り、関連付けられたサブネットマスクで IP アドレスをマスクします。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-143">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="3e7d8-144">各クライアントに関連付けられているバイパス ID を判断するとき、レジストラーは、各ネットワークサイトに関連付けられた IP サブネットの一覧と、完全一致のためにクライアントによって提供されるサブネットとを比較します。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-144">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet that is provided by the client for an exact match.</span></span> <span data-ttu-id="3e7d8-145">このため、サーバー上のネットワーク構成中に入力されたサブネットは、仮想サブネットではなく実際のサブネットであることが重要です。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-145">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="3e7d8-146">(通話受付制御を展開して、メディアをバイパスしない場合は、仮想サブネットを構成しても、通話受付制御が適切に機能します)。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-146">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="3e7d8-147">たとえば、ip アドレスが255.255.255.0 の IP アドレスが172.29.81.57 のコンピューターで Lync クライアントがサインインすると、サブネット172.29.81.0 に関連付けられているバイパス ID が要求されます。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-147">For example, if a Lync client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, it will request the bypass ID that is associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="3e7d8-148">クライアントが仮想サブネットに属していても、サブネットが 172.29.0.0/16 として定義される場合、レジストラーは 172.29.81.0 のサブネットのみを検索するため、これを一致とは見なしません。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-148">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="3e7d8-149">そのため、管理者は、Lync クライアント (静的または動的ホスト構成プロトコル (DHCP) によって、ネットワーク構成中にサブネットでプロビジョニングされる) とまったく同じサブネットを入力することが重要です。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-149">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration, either statically or by Dynamic Host Configuration Protocol (DHCP).)</span></span>



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a><span data-ttu-id="3e7d8-150">サブネットとネットワーク サイトの関連付け</span><span class="sxs-lookup"><span data-stu-id="3e7d8-150">Associating Subnets with Network Sites</span></span>

<span data-ttu-id="3e7d8-151">エンタープライズ ネットワーク内のすべてのサブネットは、ネットワーク サイトに関連付ける必要があります (つまり、すべてのサブネットを地理的場所に関連付ける必要があります)。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-151">Every subnet in the enterprise network must be associated with a network site (that is, every subnet needs to be associated with a geographic location).</span></span> <span data-ttu-id="3e7d8-152">サブネットの関連付けを使用すると、高度なエンタープライズボイス機能で、エンドポイントを地理的に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-152">This association of subnets enables the advanced Enterprise Voice features to locate the endpoints geographically.</span></span> <span data-ttu-id="3e7d8-153">たとえば、エンドポイントを見つけることにより、CAC では、ネットワーク サイトとの間で送受信されるリアルタイムの音声およびビデオのデータ フローを調整できます。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-153">For example, locating the endpoints enables CAC to regulate the flow of real-time audio and video data going to and from the network site.</span></span>

<span data-ttu-id="3e7d8-154">サブネットとネットワークサイトを関連付けるには、Lync Server コントロールパネルの [**ネットワーク構成**] セクションを使用するか、または Lync Server 管理シェルを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-154">To associate subnets with network sites, you can either use the **Network Configuration** section of Lync Server Control Panel, or you can use the Lync Server Management Shell.</span></span> <span data-ttu-id="3e7d8-155">手順については、「展開ドキュメントの[Lync server 2013 でのサブネットのネットワークサイト](lync-server-2013-associate-a-subnet-with-a-network-site.md)への関連付け」を参照するか、「Lync Server 管理シェルのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e7d8-155">For instructions, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3e7d8-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e7d8-156">See Also</span></span>


[<span data-ttu-id="3e7d8-157">Lync Server 2013 での通話受付管理の計画</span><span class="sxs-lookup"><span data-stu-id="3e7d8-157">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="3e7d8-158">Lync Server 2013 での緊急サービス (E9-1-1) の計画</span><span class="sxs-lookup"><span data-stu-id="3e7d8-158">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[<span data-ttu-id="3e7d8-159">Lync Server 2013 でのメディア バイパスの計画</span><span class="sxs-lookup"><span data-stu-id="3e7d8-159">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

