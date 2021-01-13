---
title: クラウド ボイス機能のネットワーク設定
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: ダイレクト ルーティングおよび拡張緊急サービスの自動ルーティングLocation-Based構成する必要があるネットワーク設定について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 10547a99b0e63585ae39cc90a5b0cf573a9c94e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834337"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="37016-103">Microsoft Teams のクラウド音声機能のネットワーク設定</span><span class="sxs-lookup"><span data-stu-id="37016-103">Network settings for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="37016-104">ネットワーク領域、ネットワーク サイト、ネットワーク サブネット、信頼済み IP アドレスについて学習します。</span><span class="sxs-lookup"><span data-stu-id="37016-104">Learn about network regions, network sites, network subnets, and trusted IP addresses.</span></span> <span data-ttu-id="37016-105">これらの用語と概念は、直接ルーティングおよび動的緊急通話用の場所ベースのルーティングに関するクラウド[音声ドキュメント](location-based-routing-plan.md)[全体で使用されます](configure-dynamic-emergency-calling.md)。</span><span class="sxs-lookup"><span data-stu-id="37016-105">These terms and concepts are used throughout our cloud voice documentation for [Location-Based Routing for Direct Routing](location-based-routing-plan.md) and [dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span> <span data-ttu-id="37016-106">組織でこれらのクラウド機能を展開する場合は、Microsoft Teams のこれらの機能で使用するネットワーク設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37016-106">If you're deploying these cloud features in your organization, you must configure network settings for use with these features in Microsoft Teams.</span></span>

<span data-ttu-id="37016-107">この記事では、ルーティングと動的緊急通話で一般的なネットワークLocation-Based概要を示します。</span><span class="sxs-lookup"><span data-stu-id="37016-107">This article gives you an overview of the network settings that are common to Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="37016-108">展開するクラウド音声機能に応じて、これらの設定の一部またはすべてを構成します。</span><span class="sxs-lookup"><span data-stu-id="37016-108">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="37016-109">これらの設定を構成する手順については、「Teams でクラウド機能のネットワーク トポロジを管理する」を [参照してください](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="37016-109">For steps on how to configure these settings, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

> [!NOTE]
> <span data-ttu-id="37016-110">ネットワーク設定に関する機能固有の要件は、その機能の構成トピックに記載されています。</span><span class="sxs-lookup"><span data-stu-id="37016-110">Any feature-specific requirements for network settings are documented in the configuration topics for that feature.</span></span>

## <a name="network-region"></a><span data-ttu-id="37016-111">ネットワーク領域</span><span class="sxs-lookup"><span data-stu-id="37016-111">Network region</span></span>

<span data-ttu-id="37016-112">ネットワーク地域にはネットワーク サイトのコレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="37016-112">A network region contains a collection of network sites.</span></span> <span data-ttu-id="37016-113">ネットワークのさまざまな部分が複数の地理的領域にわたって相互に接続されます。</span><span class="sxs-lookup"><span data-stu-id="37016-113">It interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="37016-114">たとえば、組織にインドに多数のサイトがある場合、"インド" をネットワーク地域として指定することができます。</span><span class="sxs-lookup"><span data-stu-id="37016-114">For example, if your organization has many sites located in India, you may choose to designate "India" as a network region.</span></span> <span data-ttu-id="37016-115">各ネットワーク サイトは、ネットワーク領域に関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="37016-115">Each network site must be associated with a network region.</span></span>

<span data-ttu-id="37016-116">同じネットワーク領域は、直接ルーティングおよび拡張Location-Basedルーティングによって共有されます。</span><span class="sxs-lookup"><span data-stu-id="37016-116">The same network regions are shared by Location-Based Routing for Direct Routing and enhanced emergency services.</span></span> <span data-ttu-id="37016-117">1 つの機能に対して既にネットワーク領域を作成している場合は、その機能用に新しいネットワーク領域を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37016-117">If you already created network regions for one feature, you don't have to create new network regions for the other feature.</span></span>

## <a name="network-site"></a><span data-ttu-id="37016-118">ネットワーク サイト</span><span class="sxs-lookup"><span data-stu-id="37016-118">Network site</span></span>

<span data-ttu-id="37016-119">ネットワーク サイトは、オフィス、建物のセット、キャンパスなど、組織が物理的な会場を持つ場所を表します。</span><span class="sxs-lookup"><span data-stu-id="37016-119">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="37016-120">ネットワーク サイトは、IP サブネットのコレクションとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="37016-120">Network sites are defined as a collection of IP subnets.</span></span> <span data-ttu-id="37016-121">各ネットワーク サイトは、ネットワーク領域に関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="37016-121">Each network site must be associated with a network region.</span></span>

<span data-ttu-id="37016-122">また、ネットワーク サイトを使用して、緊急通話を有効にし、構成することができます。</span><span class="sxs-lookup"><span data-stu-id="37016-122">You can also use network sites to enable and configure emergency calling.</span></span>

## <a name="network-subnet"></a><span data-ttu-id="37016-123">ネットワーク サブネット</span><span class="sxs-lookup"><span data-stu-id="37016-123">Network subnet</span></span>

<span data-ttu-id="37016-124">各サブネットは、特定のネットワーク サイトに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="37016-124">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="37016-125">クライアントの場所は、ネットワーク サブネットと関連するネットワーク サイトに基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="37016-125">A client's location is determined based on the network subnet and the associated network site.</span></span> <span data-ttu-id="37016-126">複数のサブネットを同じネットワーク サイトに関連付けできますが、複数のサイトを同じサブネットに関連付け設定できない。</span><span class="sxs-lookup"><span data-stu-id="37016-126">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span>

<span data-ttu-id="37016-127">サブネット情報は、新しいセッションが開始された場合にエンドポイントが保存されているネットワーク サイトを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="37016-127">Subnet information is used to determine the network site on which an endpoint is located when a new session is initiated.</span></span> <span data-ttu-id="37016-128">セッション内の各パーティーの場所が既知の場合、クラウド音声機能は、その情報を適用して、通話セットアップまたはルーティングを処理する方法を決定できます。</span><span class="sxs-lookup"><span data-stu-id="37016-128">When the location of each party in a session is known, the cloud voice feature can apply that information to determine how to handle call setup or routing.</span></span>

<span data-ttu-id="37016-129">ネットワーク サイトごとに、ネットワーク管理者と共同で、各ネットワーク サイトに割り当てられている IP サブネットを決定します。</span><span class="sxs-lookup"><span data-stu-id="37016-129">For each network site, work with your network admin to determine which IP subnets are assigned to each network site.</span></span> <span data-ttu-id="37016-130">この例では、North America 地域の New York サイトに 172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24 の IP サブネットを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="37016-130">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24.</span></span> <span data-ttu-id="37016-131">通常はイントラディブルで働くボブがトレーニングのためにニューヨークのオフィスに出張し、コンピューターをオンにし、ネットワークに接続すると、コンピューターは 172.29.80.103 のように、ニューヨークに割り当てられる 4 つの範囲の 1 つで IP アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="37016-131">If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York, for example, 172.29.80.103.</span></span>

## <a name="trusted-ip-address"></a><span data-ttu-id="37016-132">信頼できる IP アドレス</span><span class="sxs-lookup"><span data-stu-id="37016-132">Trusted IP address</span></span>

<span data-ttu-id="37016-133">信頼できる IP アドレスは、エンタープライズ ネットワークのインターネット外部 IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="37016-133">Trusted IP addresses are the internet external IP addresses of the enterprise network.</span></span> <span data-ttu-id="37016-134">特定のサイトの一致を確認する前に、ユーザーのエンドポイントが企業ネットワーク内にあるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="37016-134">They determine whether the user's endpoint is inside the corporate network before checking for a specific site match.</span></span>

<span data-ttu-id="37016-135">ユーザーの外部 IP アドレスが信頼済み IP アドレス一覧内の IP アドレスと一致する場合、クラウド音声機能は、ユーザーのエンドポイントがある内部サブネットを確認します。</span><span class="sxs-lookup"><span data-stu-id="37016-135">If the user's external IP address matches an IP address that's in the trusted IP address list, the cloud voice feature checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="37016-136">一致は IPv4 または IPv6 IP アドレスに対して行い、ネットワーク設定に送信される IP パケットの形式に依存します。</span><span class="sxs-lookup"><span data-stu-id="37016-136">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span> <span data-ttu-id="37016-137">(パブリック IP アドレスに IPv4 と IPv6 の両方がある場合は、両方を信頼済み IP アドレスとして追加する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="37016-137">(If a public IP address has both IPv4 and IPv6, you must add both as trusted IP addresses.)</span></span>

<span data-ttu-id="37016-138">ユーザーの外部 IP アドレスが信頼済み IP アドレス一覧内の IP アドレスと一致しない場合、エンドポイントは不明な場所にあると分類されます。</span><span class="sxs-lookup"><span data-stu-id="37016-138">If the user's external IP address doesn't match an IP address that's in the trusted IP address list, the endpoint is classified as being at an unknown location.</span></span>
