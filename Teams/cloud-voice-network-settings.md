---
title: Microsoft Teams のクラウド音声機能のネットワーク設定
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: ダイレクトルーティングと強化された緊急サービスの位置情報に基づくルーティング用に構成する必要があるネットワーク設定について説明します。
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 74cf743d41f37cca2b8df4f25cc8f5328db6d776
ms.sourcegitcommit: 021c86bf579e315f15815dcddf232a0c651cbf6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615887"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="45036-103">Microsoft Teams のクラウド音声機能のネットワーク設定</span><span class="sxs-lookup"><span data-stu-id="45036-103">Network settings for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="45036-104">ネットワーク領域、ネットワークサイト、ネットワークサブネット、および信頼できる IP アドレスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="45036-104">Learn about network regions, network sites, network subnets, and trusted IP addresses.</span></span> <span data-ttu-id="45036-105">このような用語と概念は、skype のクラウドボイスドキュメントで使用され、ダイレクトルーティングおよび[動的緊急通話](configure-dynamic-emergency-calling.md)[の位置情報に基づくルーティング](location-based-routing-plan.md)を対象としています。</span><span class="sxs-lookup"><span data-stu-id="45036-105">These terms and concepts are used throughout our cloud voice documentation for [Location-Based Routing for Direct Routing](location-based-routing-plan.md) and [dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span> <span data-ttu-id="45036-106">これらのクラウド機能を組織に展開している場合は、Microsoft Teams でこれらの機能を使用するためにネットワーク設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45036-106">If you're deploying these cloud features in your organization, you must configure network settings for use with these features in Microsoft Teams.</span></span>

<span data-ttu-id="45036-107">この記事では、位置に基づくルーティングと動的な緊急通話に共通するネットワーク設定の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="45036-107">This article gives you an overview of the network settings that are common to Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="45036-108">展開しているクラウドの音声機能と機能に応じて、これらの設定の一部またはすべてを構成します。</span><span class="sxs-lookup"><span data-stu-id="45036-108">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="45036-109">これらの設定を構成する手順については、「 [Teams のクラウド機能のネットワークトポロジを管理](manage-your-network-topology.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45036-109">For steps on how to configure these settings, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

> [!NOTE]
> <span data-ttu-id="45036-110">ネットワーク設定の機能固有の要件については、その機能の構成トピックで説明しています。</span><span class="sxs-lookup"><span data-stu-id="45036-110">Any feature-specific requirements for network settings are documented in the configuration topics for that feature.</span></span>

## <a name="network-region"></a><span data-ttu-id="45036-111">ネットワークの地域</span><span class="sxs-lookup"><span data-stu-id="45036-111">Network region</span></span>

<span data-ttu-id="45036-112">ネットワーク地域にはネットワーク サイトのコレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="45036-112">A network region contains a collection of network sites.</span></span> <span data-ttu-id="45036-113">ネットワークのさまざまな部分を複数の地域で相互に接続します。</span><span class="sxs-lookup"><span data-stu-id="45036-113">It interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="45036-114">たとえば、組織にインド在住のサイトが数多くある場合は、ネットワーク領域として "インド" を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="45036-114">For example, if your organization has many sites located in India, you may choose to designate “India” as a network region.</span></span> <span data-ttu-id="45036-115">各ネットワークサイトは、ネットワーク領域に関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="45036-115">Each network site must be associated with a network region.</span></span>

<span data-ttu-id="45036-116">同一のネットワーク領域は、ダイレクトルーティングと強化された緊急サービスの位置情報に基づくルーティングによって共有されます。</span><span class="sxs-lookup"><span data-stu-id="45036-116">The same network regions are shared by Location-Based Routing for Direct Routing and enhanced emergency services.</span></span> <span data-ttu-id="45036-117">1つの機能に対して既にネットワークの領域を作成している場合は、他の機能のために新しいネットワークの領域を作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="45036-117">If you already created network regions for one feature, you don't have to create new network regions for the other feature.</span></span>

## <a name="network-site"></a><span data-ttu-id="45036-118">ネットワークサイト</span><span class="sxs-lookup"><span data-stu-id="45036-118">Network site</span></span>

<span data-ttu-id="45036-119">ネットワークサイトとは、オフィス、建物のセット、キャンパスなど、組織が物理的な会場を持っている場所を表します。</span><span class="sxs-lookup"><span data-stu-id="45036-119">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="45036-120">ネットワークサイトは、IP サブネットのコレクションとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="45036-120">Network sites are defined as a collection of IP subnets.</span></span> <span data-ttu-id="45036-121">各ネットワークサイトは、ネットワーク領域に関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="45036-121">Each network site must be associated with a network region.</span></span>

<span data-ttu-id="45036-122">また、ネットワークサイトを使って緊急通話を有効にし、構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="45036-122">You can also use network sites to enable and configure emergency calling.</span></span>

## <a name="network-subnet"></a><span data-ttu-id="45036-123">ネットワークサブネット</span><span class="sxs-lookup"><span data-stu-id="45036-123">Network subnet</span></span>

<span data-ttu-id="45036-124">各サブネットは、特定のネットワークサイトに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="45036-124">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="45036-125">クライアントの場所は、ネットワークサブネットと関連付けられたネットワークサイトに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="45036-125">A client's location is determined based on the network subnet and the associated network site.</span></span> <span data-ttu-id="45036-126">複数のサブネットを同じネットワークサイトに関連付けることはできますが、複数のサイトを同じサブネットに関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="45036-126">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span>

<span data-ttu-id="45036-127">サブネット情報は、新しいセッションが開始されたときにエンドポイントが配置されているネットワークサイトを特定するために使われます。</span><span class="sxs-lookup"><span data-stu-id="45036-127">Subnet information is used to determine the network site on which an endpoint is located when a new session is initiated.</span></span> <span data-ttu-id="45036-128">セッション内の各パーティの場所がわかっている場合は、クラウド音声機能によって、通話の設定またはルーティングを処理する方法を決定する情報を適用できます。</span><span class="sxs-lookup"><span data-stu-id="45036-128">When the location of each party in a session is known, the cloud voice feature can apply that information to determine how to handle call setup or routing.</span></span>

<span data-ttu-id="45036-129">各ネットワークサイトについて、ネットワーク管理者と協力して、各ネットワークサイトに割り当てる IP サブネットを決定します。</span><span class="sxs-lookup"><span data-stu-id="45036-129">For each network site, work with your network admin to determine which IP subnets are assigned to each network site.</span></span> <span data-ttu-id="45036-130">この例では、North America 地域の New York サイトに 172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24 の IP サブネットを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="45036-130">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24.</span></span> <span data-ttu-id="45036-131">通常、デトロイトで動作するボブは、ニューヨークの office に移動してトレーニングを受け、コンピューターを有効にしてネットワークに接続すると、172.29.80.103 のように、ニューヨークに割り当てられている4つの範囲のいずれかで IP アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="45036-131">If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York, for example, 172.29.80.103.</span></span>

## <a name="trusted-ip-address"></a><span data-ttu-id="45036-132">信頼できる IP アドレス</span><span class="sxs-lookup"><span data-stu-id="45036-132">Trusted IP address</span></span>

<span data-ttu-id="45036-133">信頼できる IP アドレスは、エンタープライズネットワークのインターネット外部 IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="45036-133">Trusted IP addresses are the internet external IP addresses of the enterprise network.</span></span> <span data-ttu-id="45036-134">特定のサイト一致を確認する前に、ユーザーのエンドポイントが企業ネットワーク内にあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="45036-134">They determine whether the user’s endpoint is inside the corporate network before checking for a specific site match.</span></span>

<span data-ttu-id="45036-135">ユーザーの外部 IP アドレスが、信頼された IP アドレス一覧にある IP アドレスと一致する場合、クラウド音声機能によって、ユーザーのエンドポイントが配置されている内部サブネットが確認されます。</span><span class="sxs-lookup"><span data-stu-id="45036-135">If the user’s external IP address matches an IP address that's in the trusted IP address list, the cloud voice feature checks to determine the internal subnet where the user’s endpoint is located.</span></span> <span data-ttu-id="45036-136">一致は、IPv4 または IPv6 の IP アドレスに対して行うことができます。また、ネットワーク設定に送信される IP パケットの形式によって異なります。</span><span class="sxs-lookup"><span data-stu-id="45036-136">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span> <span data-ttu-id="45036-137">(パブリック IP アドレスに IPv4 と IPv6 の両方が含まれている場合は、両方を信頼できる IP アドレスとして追加する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="45036-137">(If a public IP address has both IPv4 and IPv6, you must add both as trusted IP addresses.)</span></span>

<span data-ttu-id="45036-138">ユーザーの外部 IP アドレスが、信頼された IP アドレス一覧に含まれている IP アドレスと一致しない場合、エンドポイントは不明な場所にあると分類されます。</span><span class="sxs-lookup"><span data-stu-id="45036-138">If the user’s external IP address doesn’t match an IP address that's in the trusted IP address list, the endpoint is classified as being at an unknown location.</span></span>
