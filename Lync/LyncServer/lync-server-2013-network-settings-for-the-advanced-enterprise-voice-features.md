---
title: 'Lync Server 2013: 高度なエンタープライズ Voip 機能のネットワーク設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 340a1902137b6c675b154ef9ccf3d9fbcc882e88
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="f7776-102">Lync Server 2013 の高度なエンタープライズ Voip 機能のネットワーク設定</span><span class="sxs-lookup"><span data-stu-id="f7776-102">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7776-103">_**トピックの最終更新日:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="f7776-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="f7776-104">Lync Server には、通話受付管理 (CAC)、緊急サービス (E9-1-1)、メディアバイパスという3つの高度なエンタープライズ Voip 機能があります。</span><span class="sxs-lookup"><span data-stu-id="f7776-104">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="f7776-105">これらの機能は、ネットワーク地域、ネットワークサイト、および Lync Server トポロジ内の各サブネットとネットワークサイトとの関連付けについて、特定の構成要件を共有します。</span><span class="sxs-lookup"><span data-stu-id="f7776-105">These features share certain configuration requirements for network regions, network sites, and association of each subnet in the Lync Server topology with a network site.</span></span> <span data-ttu-id="f7776-106">これらの機能の展開の計画の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7776-106">For details about planning for deployment of these features, see:</span></span>

  - [<span data-ttu-id="f7776-107">Lync Server 2013 での通話受付管理の計画</span><span class="sxs-lookup"><span data-stu-id="f7776-107">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="f7776-108">Lync Server 2013 での緊急サービス (E9-1-1) の計画</span><span class="sxs-lookup"><span data-stu-id="f7776-108">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="f7776-109">Lync Server 2013 でのメディアバイパスの計画</span><span class="sxs-lookup"><span data-stu-id="f7776-109">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

<span data-ttu-id="f7776-110">これらの各機能の展開の詳細については、「展開」のドキュメントの「 [Advanced Enterprise Voice features In Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7776-110">For details about deploying each of these features, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) in the Deployment documentation.</span></span>

<span data-ttu-id="f7776-111">このトピックでは、3つの高度なエンタープライズ Voip 機能すべてに共通する構成要件の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7776-111">This topic provides an overview of the configuration requirements that are common to all three advanced Enterprise Voice features.</span></span>

<div>

## <a name="network-regions"></a><span data-ttu-id="f7776-112">ネットワーク地域</span><span class="sxs-lookup"><span data-stu-id="f7776-112">Network Regions</span></span>

<span data-ttu-id="f7776-113">ネットワーク地域は、通話受付管理 (CAC)、E9-1-1、およびメディア バイパスの構成でのみ使用されるネットワーク ハブまたはネットワーク バックボーンです。</span><span class="sxs-lookup"><span data-stu-id="f7776-113">A network region is a network hub or network backbone used only in the configuration of call admission control (CAC), E9-1-1, and media bypass.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7776-114">ネットワーク地域は、Lync server のダイヤルイン会議の地域と同じではありません。これは、ダイヤルイン会議アクセス番号を1つまたは複数の Lync Server ダイヤルプランに関連付けるために必要です。</span><span class="sxs-lookup"><span data-stu-id="f7776-114">Network regions are not the same as Lync Server dial-in conferencing regions, which are required to associate dial-in conferencing access numbers with one or more Lync Server dial plans.</span></span> <span data-ttu-id="f7776-115">ダイヤルイン会議の地域の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 のダイヤルイン会議の要件</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7776-115">For details about dial-in conferencing regions, see <A href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="f7776-116">CAC では、すべてのネットワーク地域に Lync Server 中央サイトが関連付けられていることが必要です。これは、地域内のメディアトラフィックを管理します (つまり、構成したポリシーに基づいて、リアルタイムの音声またはビデオセッションであるかどうかに関する決定を行います)。確立されます)。</span><span class="sxs-lookup"><span data-stu-id="f7776-116">CAC requires that every network region have an associated Lync Server central site, which manages media traffic within the region (that is, it makes decisions based on policies that you have configured, regarding whether or not a real-time audio or video session can be established).</span></span> <span data-ttu-id="f7776-117">Lync Server 中央サイトは、地理的な場所ではなく、プールまたはプールのセットとして構成されたサーバーの論理グループを表します。</span><span class="sxs-lookup"><span data-stu-id="f7776-117">Lync Server central sites do not represent geographical locations, but rather logical groups of servers that are configured as a pool or a set of pools.</span></span> <span data-ttu-id="f7776-118">中央サイトの詳細については、「計画」のドキュメントの「 [Reference トポロジ In Lync Server 2013](lync-server-2013-reference-topologies.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7776-118">For details about central sites, see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="f7776-119">また、「サポート」のドキュメントの「 [Lync Server 2013 でサポートされるトポロジ](lync-server-2013-supported-topologies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7776-119">Also see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md) in the Supportability documentation.</span></span>

<span data-ttu-id="f7776-120">ネットワーク地域を構成するには、Lync Server コントロールパネルの [**ネットワーク構成**] セクションの [**地域**] タブを使用するか、または**新しい-Csnetworkregion**または**Set-csnetworkregion** Lync Server 管理シェルコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7776-120">To configure a network region, you can either use the **Regions** tab on the **Network Configuration** section of Lync Server Control Panel, or run the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="f7776-121">手順については、「展開」のドキュメントの「 [Lync server 2013 でネットワーク地域を作成または変更](lync-server-2013-create-or-modify-a-network-region.md)する」または「Lync Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7776-121">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

<span data-ttu-id="f7776-122">同じネットワーク地域定義は、3つの高度なエンタープライズ Voip 機能によって共有されます。</span><span class="sxs-lookup"><span data-stu-id="f7776-122">The same network region definitions are shared by all three advanced Enterprise Voice features.</span></span> <span data-ttu-id="f7776-123">いずれかの機能にネットワーク地域を既に作成している場合、他の機能に新しいネットワーク地域を作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f7776-123">If you have already created network regions for one feature, you do not need to create new network regions for the other features.</span></span> <span data-ttu-id="f7776-124">ただし、機能固有の設定を適用するために、既存のネットワーク地域定義を変更することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7776-124">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="f7776-125">たとえば、E9-1-1 (関連付けられた中央サイトは不要) にネットワーク地域を作成しており、通話受付管理を後で展開する場合、中央サイトを指定するには、各ネットワーク地域定義を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7776-125">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and, later, you deploy call admission control, you must modify each of the network region definitions to specify a central site.</span></span>

<span data-ttu-id="f7776-126">Lync Server 中央サイトをネットワーク地域に関連付けるには、[Lync Server コントロールパネル] の [**ネットワーク構成**] セクションを使用するか、または**新しい-Csnetworkregion**または**Set-Csnetworkregion** Lync Server 管理シェルコマンドレットを実行して、中央サイト名を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7776-126">To associate a Lync Server central site with a network region, you specify the central site name, either by using the **Network Configuration** section of Lync Server Control Panel, or by running the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="f7776-127">手順については、「展開」のドキュメントの「 [Lync server 2013 でネットワーク地域を作成または変更](lync-server-2013-create-or-modify-a-network-region.md)する」または「Lync Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7776-127">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="network-sites"></a><span data-ttu-id="f7776-128">ネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="f7776-128">Network Sites</span></span>

<span data-ttu-id="f7776-p107">ネットワーク サイトは、ブランチ オフィス、支社、本社などの地理的場所を表します。各ネットワーク サイトは、特定のネットワーク地域に関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7776-p107">A network site represents a geographical location, such as a branch office, a regional office, or a main office. Each network site must be associated with a specific network region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7776-131">ネットワークサイトは、高度なエンタープライズ Voip 機能によってのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="f7776-131">Network sites are used only by the advanced Enterprise Voice features.</span></span> <span data-ttu-id="f7776-132">これらは、Lync Server トポロジで構成したブランチサイトとは異なります。</span><span class="sxs-lookup"><span data-stu-id="f7776-132">They are not the same as the branch sites that you configure in your Lync Server topology.</span></span> <span data-ttu-id="f7776-133">ブランチサイトの詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-reference-topologies.md">Reference トポロジ In Lync Server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7776-133">For details about branch sites, see <A href="lync-server-2013-reference-topologies.md">Reference topologies in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="f7776-134">また、「サポート」のドキュメントの「 <A href="lync-server-2013-supported-topologies.md">Lync Server 2013 でサポートされるトポロジ</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7776-134">Also see <A href="lync-server-2013-supported-topologies.md">Supported topologies in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="f7776-135">ネットワークサイトを構成してネットワーク地域に関連付けるには、Lync Server コントロールパネルの [**ネットワーク構成**] セクションを使用するか、Lync Server 管理シェルの**新しい-Csnetworksite**または**Set-csnetworksite**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7776-135">To configure a network site and associate it with a network region, you can either use the **Network Configuration** section of Lync Server Control Panel, or run the Lync Server Management Shell **New-CsNetworkSite** or **Set-CsNetworkSite** cmdlets.</span></span> <span data-ttu-id="f7776-136">詳細については、「展開」のドキュメントの「 [Create or modify a network site 2013](lync-server-2013-create-or-modify-a-network-site.md) 」または「Lync Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7776-136">For details, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="f7776-137">IP サブネットの特定</span><span class="sxs-lookup"><span data-stu-id="f7776-137">Identify IP Subnets</span></span>

<span data-ttu-id="f7776-p110">ネットワーク管理者と連携して各ネットワーク サイトに割り当てる IP サブネットを決定する必要があります。ネットワーク管理者が既に IP サブネットをネットワーク地域およびネットワーク サイトに分類している場合、作業は大幅に簡略化されます。</span><span class="sxs-lookup"><span data-stu-id="f7776-p110">For each network site, you will need to work with your network administrator to determine which IP subnets are assigned to each network site. If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="f7776-p111">この例では、North America 地域の New York サイトに 172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24 の IP サブネットを割り当てることができます。通常はデトロイトで仕事をしている Bob が、トレーニングのためにニューヨークのオフィスに出張する場合、コンピューターを起動してネットワークに接続すると、New York に割り当てられている 4 つの範囲のいずれか (172.29.80.103 など) の IP アドレスがコンピューターで取得されます。</span><span class="sxs-lookup"><span data-stu-id="f7776-p111">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York—for example, 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="f7776-142">サーバー上のネットワーク構成中に指定された IP サブネットは、メディアバイパスに適切に使用するために、クライアントコンピューターから提供される形式と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7776-142">The IP subnets specified during network configuration on the server must match the format that is provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="f7776-143">Lync クライアントは、ローカルの IP アドレスを取得し、関連付けられたサブネットマスクを使用して IP アドレスをマスクします。</span><span class="sxs-lookup"><span data-stu-id="f7776-143">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="f7776-144">各クライアントに関連付けられているバイパス ID を決定するとき、レジストラーは、各ネットワークサイトに関連付けられた IP サブネットと、完全一致のためにクライアントによって提供されたサブネットとを比較します。</span><span class="sxs-lookup"><span data-stu-id="f7776-144">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet that is provided by the client for an exact match.</span></span> <span data-ttu-id="f7776-145">このため、サーバー上のネットワーク構成中に入力されたサブネットは、仮想サブネットではなく実際のサブネットであることが重要です。</span><span class="sxs-lookup"><span data-stu-id="f7776-145">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="f7776-146">(通話受付管理を展開し、メディアバイパスを展開しない場合、仮想サブネットを構成していても、通話受付管理が適切に機能します。)</span><span class="sxs-lookup"><span data-stu-id="f7776-146">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="f7776-147">たとえば、IP サブネットマスクが255.255.255.0 の172.29.81.57 の IP アドレスを持つコンピューター上で Lync クライアントがサインインすると、サブネット172.29.81.0 に関連付けられているバイパス ID が要求されます。</span><span class="sxs-lookup"><span data-stu-id="f7776-147">For example, if a Lync client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, it will request the bypass ID that is associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="f7776-148">クライアントが仮想サブネットに属していても、サブネットが 172.29.0.0/16 として定義される場合、レジストラーは 172.29.81.0 のサブネットのみを検索するため、これを一致とは見なしません。</span><span class="sxs-lookup"><span data-stu-id="f7776-148">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="f7776-149">そのため、管理者は、(静的または動的ホスト構成プロトコル (DHCP) によってネットワーク構成中にサブネットでプロビジョニングされた) Lync クライアントによって提供されるとおりにサブネットを入力することが重要です。</span><span class="sxs-lookup"><span data-stu-id="f7776-149">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration, either statically or by Dynamic Host Configuration Protocol (DHCP).)</span></span>



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a><span data-ttu-id="f7776-150">サブネットとネットワーク サイトの関連付け</span><span class="sxs-lookup"><span data-stu-id="f7776-150">Associating Subnets with Network Sites</span></span>

<span data-ttu-id="f7776-151">エンタープライズ ネットワーク内のすべてのサブネットは、ネットワーク サイトに関連付ける必要があります (つまり、すべてのサブネットを地理的場所に関連付ける必要があります)。</span><span class="sxs-lookup"><span data-stu-id="f7776-151">Every subnet in the enterprise network must be associated with a network site (that is, every subnet needs to be associated with a geographic location).</span></span> <span data-ttu-id="f7776-152">このサブネットの関連付けにより、高度なエンタープライズ Voip 機能がエンドポイントを地理的に特定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f7776-152">This association of subnets enables the advanced Enterprise Voice features to locate the endpoints geographically.</span></span> <span data-ttu-id="f7776-153">たとえば、エンドポイントを見つけることにより、CAC では、ネットワーク サイトとの間で送受信されるリアルタイムの音声およびビデオのデータ フローを調整できます。</span><span class="sxs-lookup"><span data-stu-id="f7776-153">For example, locating the endpoints enables CAC to regulate the flow of real-time audio and video data going to and from the network site.</span></span>

<span data-ttu-id="f7776-154">サブネットをネットワークサイトに関連付けるには、Lync Server コントロールパネルの [**ネットワーク構成**] セクションを使用するか、または Lync Server 管理シェルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7776-154">To associate subnets with network sites, you can either use the **Network Configuration** section of Lync Server Control Panel, or you can use the Lync Server Management Shell.</span></span> <span data-ttu-id="f7776-155">手順については、「展開」のドキュメントの「 [Lync server 2013 でのネットワークサイトへのサブネットの関連付け](lync-server-2013-associate-a-subnet-with-a-network-site.md)」または「Lync Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7776-155">For instructions, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f7776-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7776-156">See Also</span></span>


[<span data-ttu-id="f7776-157">Lync Server 2013 での通話受付管理の計画</span><span class="sxs-lookup"><span data-stu-id="f7776-157">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="f7776-158">Lync Server 2013 での緊急サービス (E9-1-1) の計画</span><span class="sxs-lookup"><span data-stu-id="f7776-158">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[<span data-ttu-id="f7776-159">Lync Server 2013 でのメディアバイパスの計画</span><span class="sxs-lookup"><span data-stu-id="f7776-159">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

