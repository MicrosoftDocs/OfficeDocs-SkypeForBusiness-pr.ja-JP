---
title: ネットワーク設定の構成-場所に基づくルーティング
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: ダイレクトルーティングの位置情報に基づくルーティング用に、ネットワークの領域、サイト、サブネットを作成してセットアップする方法について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f63ff0191518acf72fd3e4c33abe80b819c3db28
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141280"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="41ed6-103">場所に基づくルーティングのネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="41ed6-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="41ed6-104">まだインストールしていない場合は、「[位置情報に基づくルーティングを計画](location-based-routing-plan.md)する」を参照して、場所に基づくルーティングのネットワーク設定を構成する前に実行する必要があるその他の手順を確認してください。</span><span class="sxs-lookup"><span data-stu-id="41ed6-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="41ed6-105">この記事では、場所に基づくルーティングのネットワーク設定を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="41ed6-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="41ed6-106">組織で電話システムの直接ルーティングを展開した後、次の手順では、ネットワーク領域、ネットワークサイト、ネットワークサブネットを作成してセットアップします。</span><span class="sxs-lookup"><span data-stu-id="41ed6-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="41ed6-107">ネットワーク領域を定義する</span><span class="sxs-lookup"><span data-stu-id="41ed6-107">Define network regions</span></span>

<span data-ttu-id="41ed6-108">ネットワーク領域には、ネットワークサイトのコレクションが含まれており、複数の地域にわたってネットワークのさまざまな部分を相互接続しています。</span><span class="sxs-lookup"><span data-stu-id="41ed6-108">A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="41ed6-109">ネットワーク領域を構成する手順については、「 [Teams のクラウド機能のネットワークトポロジを管理](manage-your-network-topology.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41ed6-109">For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

## <a name="define-network-sites"></a><span data-ttu-id="41ed6-110">ネットワークサイトを定義する</span><span class="sxs-lookup"><span data-stu-id="41ed6-110">Define network sites</span></span>

<span data-ttu-id="41ed6-111">ネットワークサイトとは、オフィス、建物のセット、キャンパスなど、組織が物理的な会場を持っている場所を表します。</span><span class="sxs-lookup"><span data-stu-id="41ed6-111">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="41ed6-112">トポロジ内の各ネットワークサイトをネットワーク領域と関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="41ed6-112">You must associate each network site in your topology with a network region.</span></span> <span data-ttu-id="41ed6-113">ネットワークサイトを構成する手順については、「 [Teams のクラウド機能のネットワークトポロジを管理](manage-your-network-topology.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41ed6-113">For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="41ed6-114">場所に基づくルーティングのベストプラクティスは、一意の PSTN 接続がある場所ごとに個別のサイトを作成することです。</span><span class="sxs-lookup"><span data-stu-id="41ed6-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span> <span data-ttu-id="41ed6-115">場所に基づくルーティングまたは位置情報に基づくルーティング用に有効になっていないサイトのサイトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="41ed6-115">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="41ed6-116">たとえば、位置情報に基づくルーティングが有効になっていないサイトを作成して、場所ベースのルーティングが有効になっているユーザーがそのサイトに移動したときに PSTN 通話を発信できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="41ed6-116">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span>

## <a name="define-network-subnets"></a><span data-ttu-id="41ed6-117">ネットワークサブネットを定義する</span><span class="sxs-lookup"><span data-stu-id="41ed6-117">Define network subnets</span></span>

<span data-ttu-id="41ed6-118">各サブネットは、特定のネットワークサイトに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="41ed6-118">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="41ed6-119">複数のサブネットを同じネットワークサイトに関連付けることはできますが、複数のサイトを同じサブネットに関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="41ed6-119">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span> <span data-ttu-id="41ed6-120">ネットワークサブネットを構成する手順については、「 [Teams のクラウド機能のネットワークトポロジを管理](manage-your-network-topology.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41ed6-120">For steps on how to configure network subnets, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="41ed6-121">位置情報に基づくルーティングの場合、チームのエンドポイントがネットワークに接続できる場所で、IP サブネットを定義し、定義されたネットワークに関連付けて、有料のバイパスを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41ed6-121">For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="41ed6-122">サブネットの関連付けによって、位置情報に基づくルーティングが、特定の PSTN 通話を許可するかどうかを判断するために、エンドポイントを地理的に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="41ed6-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="41ed6-123">IPv6 と IPv4 の両方のサブネットがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="41ed6-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="41ed6-124">チームのエンドポイントがサイトに配置されているかどうかを判断するときに、位置ベースのルーティングでは、最初に一致する IPv6 アドレスが確認されます。</span><span class="sxs-lookup"><span data-stu-id="41ed6-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="41ed6-125">IPv6 アドレスが存在しない場合、場所に基づくルーティングで IPv4 アドレスが確認されます。</span><span class="sxs-lookup"><span data-stu-id="41ed6-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span>

## <a name="define-trusted-ip-addresses-external-subnets"></a><span data-ttu-id="41ed6-126">信頼できる IP アドレス (外部サブネット) を定義する</span><span class="sxs-lookup"><span data-stu-id="41ed6-126">Define trusted IP addresses (external subnets)</span></span>

<span data-ttu-id="41ed6-127">[信頼された IP アドレス] は、エンタープライズネットワークのインターネット外部 IP アドレスであり、ユーザーのエンドポイントが企業ネットワーク内にあるかどうかを判断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="41ed6-127">Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="41ed6-128">信頼された IP アドレスを構成する手順については、「 [Teams のクラウド機能のネットワークトポロジを管理](manage-your-network-topology.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41ed6-128">For steps on how to configure trusted IP addresses, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="41ed6-129">ユーザーの外部 IP アドレスが、信頼された IP アドレス一覧にある IP アドレスと一致する場合、場所ベースのルーティングでは、ユーザーのエンドポイントが配置されている内部サブネットを確認します。</span><span class="sxs-lookup"><span data-stu-id="41ed6-129">If the user's external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="41ed6-130">ユーザーの外部 IP アドレスが、信頼できる IP アドレスリストで定義されている IP アドレスと一致しない場合、エンドポイントは不明な場所に分類され、場所に基づくルーティングを有効にしているユーザーへの PSTN 通話はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="41ed6-130">If the user's external IP address doesn't match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>

## <a name="next-steps"></a><span data-ttu-id="41ed6-131">次の手順</span><span class="sxs-lookup"><span data-stu-id="41ed6-131">Next steps</span></span>

<span data-ttu-id="41ed6-132">「[ダイレクトルーティングで位置情報に基づくルーティングを有効](location-based-routing-enable.md)にする」に進みます。</span><span class="sxs-lookup"><span data-stu-id="41ed6-132">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="41ed6-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="41ed6-133">Related topics</span></span>

- [<span data-ttu-id="41ed6-134">Teams でのクラウド音声機能のネットワーク設定</span><span class="sxs-lookup"><span data-stu-id="41ed6-134">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
