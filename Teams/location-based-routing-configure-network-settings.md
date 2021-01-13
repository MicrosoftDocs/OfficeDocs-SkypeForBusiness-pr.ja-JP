---
title: ネットワーク設定の構成 - 場所に基づくルーティング
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 直接ルーティング用のネットワーク領域、サイト、サブネットを作成および設定するLocation-Based方法について説明します。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7dd707a6066cfe9a8dfcbcc9b3ae36d450d1dd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822947"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="a759f-103">場所に基づくルーティングのネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="a759f-103">Configure network settings for Location-Based Routing</span></span>

<span data-ttu-id="a759f-104">まだ行っていない場合は、「直接ルーティングの計画 [Location-Based](location-based-routing-plan.md) ルーティング」を参照して、Location-Based ルーティングのネットワーク設定を構成する前に実行する必要があるその他の手順を確認してください。</span><span class="sxs-lookup"><span data-stu-id="a759f-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="a759f-105">この記事では、ネットワーク ルーティングのネットワーク設定を構成するLocation-Based説明します。</span><span class="sxs-lookup"><span data-stu-id="a759f-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="a759f-106">組織に電話システム ダイレクト ルーティングを展開した後、次の手順は、ネットワーク領域、ネットワーク サイト、ネットワーク サブネットを作成してセットアップします。</span><span class="sxs-lookup"><span data-stu-id="a759f-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="a759f-107">ネットワーク領域を定義する</span><span class="sxs-lookup"><span data-stu-id="a759f-107">Define network regions</span></span>

<span data-ttu-id="a759f-108">ネットワーク領域には、ネットワーク サイトのコレクションが含まれるので、ネットワークのさまざまな部分が複数の地理的領域にわたって相互接続されます。</span><span class="sxs-lookup"><span data-stu-id="a759f-108">A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="a759f-109">ネットワーク領域を構成する方法の手順については、「Teams でクラウド機能のネットワーク トポロジを管理する」を [参照してください](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="a759f-109">For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

## <a name="define-network-sites"></a><span data-ttu-id="a759f-110">ネットワーク サイトを定義する</span><span class="sxs-lookup"><span data-stu-id="a759f-110">Define network sites</span></span>

<span data-ttu-id="a759f-111">ネットワーク サイトは、オフィス、建物のセット、キャンパスなど、組織が物理的な会場を持つ場所を表します。</span><span class="sxs-lookup"><span data-stu-id="a759f-111">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="a759f-112">トポロジ内の各ネットワーク サイトをネットワーク領域に関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="a759f-112">You must associate each network site in your topology with a network region.</span></span> <span data-ttu-id="a759f-113">ネットワーク サイトを構成する手順については、「Teams でクラウド機能のネットワーク トポロジを管理する」 [を参照してください](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="a759f-113">For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="a759f-114">ルーティングのベスト プラクティスLocation-Basedは、一意の PSTN 接続を持つ場所ごとに個別のサイトを作成することです。</span><span class="sxs-lookup"><span data-stu-id="a759f-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span> <span data-ttu-id="a759f-115">カスタム ルーティングに対して有効になっているサイトLocation-Based、またはサイト のルーティングが有効になっていないLocation-Basedできます。</span><span class="sxs-lookup"><span data-stu-id="a759f-115">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="a759f-116">たとえば、Location-Based ルーティングが有効になっていないサイトを作成して、Location-Based ルーティングが有効になっているユーザーがサイトにローミングするときに PSTN 通話を発信できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a759f-116">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span>

## <a name="define-network-subnets"></a><span data-ttu-id="a759f-117">ネットワーク サブネットを定義する</span><span class="sxs-lookup"><span data-stu-id="a759f-117">Define network subnets</span></span>

<span data-ttu-id="a759f-118">各サブネットは、特定のネットワーク サイトに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a759f-118">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="a759f-119">複数のサブネットを同じネットワーク サイトに関連付けできますが、複数のサイトを同じサブネットに関連付け設定できない。</span><span class="sxs-lookup"><span data-stu-id="a759f-119">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span> <span data-ttu-id="a759f-120">ネットワーク サブネットを構成する方法の手順については、「Teams でクラウド機能のネットワーク トポロジを管理する」  [を参照してください](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="a759f-120">For steps on how to configure network subnets, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="a759f-121">ルーティングLocation-Based、有料バイパスを適用するには、Teams のエンドポイントがネットワークに接続できる場所の IP サブネットを定義し、定義されたネットワークに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a759f-121">For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="a759f-122">このサブネットの関連付けにより、Location-Basedルーティングでエンドポイントを地理的に特定し、特定の PSTN 通話を許可するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="a759f-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="a759f-123">IPv6 サブネットと IPv4 サブネットの両方がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a759f-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="a759f-124">Teams エンドポイントがサイトにあるかどうかを判断する場合、最初にルーティングLocation-Based IPv6 アドレスが一致するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a759f-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="a759f-125">IPv6 アドレスが存在しない場合は、Location-Basedが IPv4 アドレスをチェックします。</span><span class="sxs-lookup"><span data-stu-id="a759f-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span>

## <a name="define-trusted-ip-addresses-external-subnets"></a><span data-ttu-id="a759f-126">信頼できる IP アドレス (外部サブネット) を定義する</span><span class="sxs-lookup"><span data-stu-id="a759f-126">Define trusted IP addresses (external subnets)</span></span>

<span data-ttu-id="a759f-127">信頼済み IP アドレスは、エンタープライズ ネットワークのインターネット外部 IP アドレスであり、ユーザーのエンドポイントが企業ネットワーク内にあるかどうかを判断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a759f-127">Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="a759f-128">信頼できる IP アドレスを構成する方法の手順については、「Teams でクラウド機能のネットワーク トポロジを管理する」を  [参照してください](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="a759f-128">For steps on how to configure trusted IP addresses, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="a759f-129">ユーザーの外部 IP アドレスが信頼済み IP アドレス一覧内の IP アドレスと一致する場合、Location-Based ルーティングはユーザーのエンドポイントがある内部サブネットを確認します。</span><span class="sxs-lookup"><span data-stu-id="a759f-129">If the user's external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="a759f-130">ユーザーの外部 IP アドレスが信頼済み IP アドレス一覧で定義されている IP アドレスと一致しない場合、エンドポイントは不明な場所にあると分類され、Location-Based ルーティングが有効になっているユーザーとの間の PSTN 通話はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="a759f-130">If the user's external IP address doesn't match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a759f-131">次の手順</span><span class="sxs-lookup"><span data-stu-id="a759f-131">Next steps</span></span>

<span data-ttu-id="a759f-132">「ダイレクト ルーティング [のLocation-Basedを有効にする」を参照してください](location-based-routing-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="a759f-132">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a759f-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="a759f-133">Related topics</span></span>

- [<span data-ttu-id="a759f-134">Teams のクラウド音声機能のネットワーク設定</span><span class="sxs-lookup"><span data-stu-id="a759f-134">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
