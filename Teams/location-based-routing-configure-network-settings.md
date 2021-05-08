---
title: ネットワーク設定の構成 - 場所ベースのルーティング
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: ダイレクト ルーティング用のネットワーク リージョン、サイト、サブネットを作成および設定するLocation-Basedについて説明します。
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
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="20c49-103">場所に基づくルーティングのネットワーク設定を構成する</span><span class="sxs-lookup"><span data-stu-id="20c49-103">Configure network settings for Location-Based Routing</span></span>

<span data-ttu-id="20c49-104">まだ行っていない場合は、「直接ルーティングのための [Location-Based](location-based-routing-plan.md) ルーティングの計画」を参照して、Location-Based ルーティングのネットワーク設定を構成する前に実行する必要があるその他の手順を確認してください。</span><span class="sxs-lookup"><span data-stu-id="20c49-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="20c49-105">この記事では、ルーティングのネットワーク設定を構成するLocation-Based説明します。</span><span class="sxs-lookup"><span data-stu-id="20c49-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="20c49-106">組織に直接ルーティング電話システムデプロイした後、次の手順では、ネットワーク リージョン、ネットワーク サイト、ネットワーク サブネットを作成して設定します。</span><span class="sxs-lookup"><span data-stu-id="20c49-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="20c49-107">ネットワーク リージョンを定義する</span><span class="sxs-lookup"><span data-stu-id="20c49-107">Define network regions</span></span>

<span data-ttu-id="20c49-108">ネットワーク リージョンには、ネットワーク サイトのコレクションが含まれるので、ネットワークのさまざまな部分が複数の地理的領域にわたって相互接続されます。</span><span class="sxs-lookup"><span data-stu-id="20c49-108">A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="20c49-109">ネットワーク リージョンを構成する方法の手順については、クラウド機能のネットワーク トポロジの管理に関するページを[参照](manage-your-network-topology.md)Teams。</span><span class="sxs-lookup"><span data-stu-id="20c49-109">For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

## <a name="define-network-sites"></a><span data-ttu-id="20c49-110">ネットワーク サイトを定義する</span><span class="sxs-lookup"><span data-stu-id="20c49-110">Define network sites</span></span>

<span data-ttu-id="20c49-111">ネットワーク サイトは、オフィス、ビルのセット、キャンパスなど、組織が物理的な会場を持つ場所を表します。</span><span class="sxs-lookup"><span data-stu-id="20c49-111">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="20c49-112">トポロジ内の各ネットワーク サイトをネットワーク リージョンに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="20c49-112">You must associate each network site in your topology with a network region.</span></span> <span data-ttu-id="20c49-113">ネットワーク サイトを構成する方法の手順については、「ネットワーク サイトでクラウド機能のネットワーク トポロジを管理する[」をTeams。](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="20c49-113">For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="20c49-114">ルーティングのベスト プラクティスはLocation-Based PSTN 接続を持つ場所ごとに個別のサイトを作成することです。</span><span class="sxs-lookup"><span data-stu-id="20c49-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span> <span data-ttu-id="20c49-115">カスタム ルーティングが有効になっているサイトLocation-Based、またはルーティングに対して有効になっていないサイトLocation-Basedできます。</span><span class="sxs-lookup"><span data-stu-id="20c49-115">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="20c49-116">たとえば、Location-Based ルーティングが有効になっていないサイトを作成して、Location-Based ルーティングが有効になっているユーザーが、そのサイトにローミングするときに PSTN 通話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="20c49-116">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span>

## <a name="define-network-subnets"></a><span data-ttu-id="20c49-117">ネットワーク サブネットを定義する</span><span class="sxs-lookup"><span data-stu-id="20c49-117">Define network subnets</span></span>

<span data-ttu-id="20c49-118">各サブネットは、特定のネットワーク サイトに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="20c49-118">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="20c49-119">複数のサブネットを同じネットワーク サイトに関連付けできますが、複数のサイトを同じサブネットに関連付けは行いません。</span><span class="sxs-lookup"><span data-stu-id="20c49-119">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span> <span data-ttu-id="20c49-120">ネットワーク サブネットを構成する方法の手順については、「クラウド機能のネットワーク トポロジを管理する」を参照[Teams。](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="20c49-120">For steps on how to configure network subnets, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="20c49-121">ルーティングLocation-Based、Teams エンドポイントがネットワークに接続できる場所にある IP サブネットを定義し、定義されたネットワークに関連付け、有料バイパスを強制する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20c49-121">For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="20c49-122">このサブネットの関連付Location-Basedルーティングを使用して、特定の PSTN 呼び出しを許可するかどうかを判断するために、エンドポイントを地理的に特定できます。</span><span class="sxs-lookup"><span data-stu-id="20c49-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="20c49-123">IPv6 サブネットと IPv4 サブネットの両方がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="20c49-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="20c49-124">エンドポイントがサイトにTeamsかどうかを判断する場合は、Location-Based一致する IPv6 アドレスが最初にチェックされます。</span><span class="sxs-lookup"><span data-stu-id="20c49-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="20c49-125">IPv6 アドレスが存在しない場合は、Location-Basedが IPv4 アドレスをチェックします。</span><span class="sxs-lookup"><span data-stu-id="20c49-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span>

## <a name="define-trusted-ip-addresses-external-subnets"></a><span data-ttu-id="20c49-126">信頼できる IP アドレス (外部サブネット) を定義する</span><span class="sxs-lookup"><span data-stu-id="20c49-126">Define trusted IP addresses (external subnets)</span></span>

<span data-ttu-id="20c49-127">信頼できる IP アドレスは、エンタープライズ ネットワークのインターネット外部 IP アドレスであり、ユーザーのエンドポイントが企業ネットワーク内にあるかどうかを判断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="20c49-127">Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="20c49-128">信頼できる IP アドレスを構成する手順については、「クラウド機能のネットワーク トポロジを管理する」を参照[Teams。](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="20c49-128">For steps on how to configure trusted IP addresses, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="20c49-129">ユーザーの外部 IP アドレスが信頼済み IP アドレス一覧にある IP アドレスと一致する場合、Location-Based ルーティングはユーザーのエンドポイントが位置する内部サブネットを確認します。</span><span class="sxs-lookup"><span data-stu-id="20c49-129">If the user's external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="20c49-130">ユーザーの外部 IP アドレスが信頼済み IP アドレス一覧で定義されている IP アドレスと一致しない場合、エンドポイントは不明な場所にあると分類され、Location-Based ルーティングが有効になっているユーザーとの間の PSTN 通話はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="20c49-130">If the user's external IP address doesn't match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>

## <a name="next-steps"></a><span data-ttu-id="20c49-131">次の手順</span><span class="sxs-lookup"><span data-stu-id="20c49-131">Next steps</span></span>

<span data-ttu-id="20c49-132">「Enable Location-Based Routing for Direct Routing (ダイレクト [ルーティングのルーティングを有効にする)」を参照してください](location-based-routing-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="20c49-132">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="20c49-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="20c49-133">Related topics</span></span>

- [<span data-ttu-id="20c49-134">Teams のクラウド音声機能のネットワーク設定</span><span class="sxs-lookup"><span data-stu-id="20c49-134">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
