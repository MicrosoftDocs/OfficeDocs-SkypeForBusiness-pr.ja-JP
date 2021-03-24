---
title: Microsoft Teams の通話フロー
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 06/08/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sonua
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: さまざまなトポロジにおいて、Teams が Office 365 フローを使用する方法と、ピアツーピアのメディア通信に使用する固有のTeam フローについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a720838958fa249674f6216cbc24ade5134127bc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098483"
---
# <a name="microsoft-teams-call-flows"></a><span data-ttu-id="95f1f-103">Microsoft Teams の通話フロー</span><span class="sxs-lookup"><span data-stu-id="95f1f-103">Microsoft Teams call flows</span></span>

> [!TIP]
> <span data-ttu-id="95f1f-104">Teams でのユーザーのネットワークの活用方法と最適なネットワーク接続を計画する方法については、次のセッションをご覧ください: [Teams のネットワーク計画](https://aka.ms/teams-networking)。</span><span class="sxs-lookup"><span data-stu-id="95f1f-104">Watch this session to learn how Teams leverages your network and how to plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking).</span></span>

## <a name="overview"></a><span data-ttu-id="95f1f-105">概要</span><span class="sxs-lookup"><span data-stu-id="95f1f-105">Overview</span></span>

<span data-ttu-id="95f1f-106">この記事では、Teams で Microsoft 365 または Office 365 の通話フローがさまざまなトポロジで使用される方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-106">This article describes how Teams uses Microsoft 365 or Office 365 call flows in various topologies.</span></span> <span data-ttu-id="95f1f-107">また、ピアツーピアのメディア 通信で使用される固有の Teams のフローについても説明します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-107">In addition, it describes unique Teams flows that are used for peer-to-peer media communication.</span></span> <span data-ttu-id="95f1f-108">この記事では、これらのフロー、その目的、ネットワーク上でのフローの始端と終端について説明します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-108">The document describes these flows, their purpose, and their origin and termination on the network.</span></span> <span data-ttu-id="95f1f-109">この記事では次のことを想定しています:</span><span class="sxs-lookup"><span data-stu-id="95f1f-109">For purposes of this article, assume the following:</span></span>

- <span data-ttu-id="95f1f-110">Flow X は、オンプレミスのクライアントがクラウドの Microsoft 365 または Office 365 サービスと通信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-110">Flow X is used by the on-premises client to communicate with the Microsoft 365 or Office 365 service in the cloud.</span></span> <span data-ttu-id="95f1f-111">これは、顧客ネットワークが始端となり、Microsoft 365または Office 365 がエンドポイントとして終端します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-111">It originates from the customer network, and it terminates as an endpoint in Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="95f1f-112">フロー Y は、Microsoft 365 または Office 365 が依存しているインターネット上のサービスと通信するためにオンプレミスのクライアントによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-112">Flow Y is used by the on-premises client to communicate with a service on the Internet that Microsoft 365 or Office 365 has a dependency on.</span></span> <span data-ttu-id="95f1f-113">これは、顧客ネットワークが始端となり、インターネット上のエンドポイントとして終端します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-113">It originates from the customer network, and it terminates as an endpoint on the Internet.</span></span>

<span data-ttu-id="95f1f-114">この記事には、次の情報が記載されています:</span><span class="sxs-lookup"><span data-stu-id="95f1f-114">This article covers the following information:</span></span>

- <span data-ttu-id="95f1f-115">**背景**。</span><span class="sxs-lookup"><span data-stu-id="95f1f-115">**Background**.</span></span> <span data-ttu-id="95f1f-116">フローが通過する可能性があるネットワーク、トラフィックの種類、顧客のネットワークから Microsoft 365 またはOffice 365 のサービス エンドポイントへの接続に関するガイダンス、サードパーティ製のコンポーネントとの相互運用性、Teams がメディア フローの選択に使用する原則などの背景情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-116">Provides background information such as networks that the flows may traverse, types of traffic, connectivity guidance from the customer network to Microsoft 365 or Office 365 service endpoints, interoperability with third-party components, and principles that are used by Teams to select media flows.</span></span>

- <span data-ttu-id="95f1f-117">**さまざまなトポロジにおける通話フロー**。</span><span class="sxs-lookup"><span data-stu-id="95f1f-117">**Call flows in various topologies**.</span></span> <span data-ttu-id="95f1f-118">さまざまなトポロジでの通話フローの使用を示します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-118">Illustrates the use of call flows in various topologies.</span></span> <span data-ttu-id="95f1f-119">このセクションでは、各トポロジについて、サポートされるすべてのフローを列挙し、これらのフローの使用方法をいくつかのユース ケースを使って示します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-119">For each topology, the section enumerates all supported flows and illustrates how these flows are used in several use cases.</span></span> <span data-ttu-id="95f1f-120">各ユース ケースについて、フローの順序と選択をフロー図を用いて示します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-120">For each use case, it describes the sequence and selection of flows using a flow diagram.</span></span>

- <span data-ttu-id="95f1f-121">**Teams と Express Route 最適化**。</span><span class="sxs-lookup"><span data-stu-id="95f1f-121">**Teams with Express Route optimization**.</span></span> <span data-ttu-id="95f1f-122">Express Route が最適化のために使用される場合の、これらのフローの使用方法について、単純なトポロジを使用して分かりやすく説明します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-122">Describes how these flows are used when Express Route is deployed for optimization, illustrated using a simple topology.</span></span>

## <a name="background"></a><span data-ttu-id="95f1f-123">背景</span><span class="sxs-lookup"><span data-stu-id="95f1f-123">Background</span></span>

### <a name="network-segments"></a><span data-ttu-id="95f1f-124">ネットワーク セグメント</span><span class="sxs-lookup"><span data-stu-id="95f1f-124">Network segments</span></span>

<span data-ttu-id="95f1f-125">**顧客ネットワーク**。</span><span class="sxs-lookup"><span data-stu-id="95f1f-125">**Customer network**.</span></span> <span data-ttu-id="95f1f-126">これは、ユーザーが制御および管理するネットワーク セグメントです。</span><span class="sxs-lookup"><span data-stu-id="95f1f-126">This is the network segment that you control and manage.</span></span> <span data-ttu-id="95f1f-127">これには、顧客のオフィス内の有線または無線によるすべての接続、オフィスビル間の接続、オンプレミス データセンターへの接続、インターネット プロバイダーへの接続、Express Route、またはプライベート ピアリングへの接続が含まれます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-127">This includes all customer connections within customer offices, whether wired or wireless, connections between office buildings, connections to on-premises datacenters, and your connections to Internet providers, Express Route, or any other private peering.</span></span>

<span data-ttu-id="95f1f-128">通常、顧客ネットワークには、ファイアウォールおよび/またはプロキシ サーバーを使用して組織のセキュリティ ポリシーを適用するネットワーク境界が複数あり、設定と構成を行った特定のネットワーク トラフィックのみが許可されるようになっています。</span><span class="sxs-lookup"><span data-stu-id="95f1f-128">Typically, a customer network has several network perimeters with firewalls and/or proxy servers, which enforce your organization's security policies, and that only allow certain network traffic that you have set up and configured.</span></span> <span data-ttu-id="95f1f-129">このネットワークの管理を行うのはユーザーであるため、ユーザーはネットワークのパフォーマンスを直接管理できます。ネットワーク上のサイトとネットワークから Microsoft 365 または Office 365 のネットワークの接続の両方のパフォーマンスについて、ネットワーク評価を行うことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="95f1f-129">Because you manage this network, you have direct control over the performance of the network, and we recommend that you complete network assessments to validate performance both within sites in your network and from your network to the Microsoft 365 or Office 365 network.</span></span>

<span data-ttu-id="95f1f-130">**インターネット**。</span><span class="sxs-lookup"><span data-stu-id="95f1f-130">**Internet**.</span></span> <span data-ttu-id="95f1f-131">これはネットワーク全体の一部で、顧客ネットワークの外部からMicrosoft 365 または Office 365 に接続するユーザーによって使用されるネットワークのセグメントです。</span><span class="sxs-lookup"><span data-stu-id="95f1f-131">This is the network segment that is part of your overall network that will be used by users who are connecting to Microsoft 365 or Office 365 from outside of the customer network.</span></span> <span data-ttu-id="95f1f-132">また、顧客ネットワークから Microsoft 365 または Office 365 へのトラフィックの一部にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-132">It is also used by some traffic from the customer network to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="95f1f-133">**アクセスした、またはゲストのプライベート ネットワーク**。</span><span class="sxs-lookup"><span data-stu-id="95f1f-133">**Visited or guest private network**.</span></span> <span data-ttu-id="95f1f-134">このネットワーク セグメントは顧客のネットワークには属しませんが、パブリック インターネットではアクセスできません。でもユーザーとそのゲストはアクセスする可能性があります。(たとえば、ホーム プライベート ネットワークやエンタープライズ プライベート ネットワークなどで、Teams を使用しない場合でも、Teams サービスを操作するユーザーまたは顧客が存在する可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="95f1f-134">This is the network segment outside your customer network, but not in the public Internet, that your users and their guests may visit (for example, a home private network or an enterprise private network, that does not deploy Teams, where your users and their customers that interact with Teams services may reside).</span></span>

> [!NOTE]
> <span data-ttu-id="95f1f-135">Microsoft 365 または Office 365 への接続は、これらのネットワークにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-135">Connectivity to Microsoft 365 or Office 365 is also applicable to these networks.</span></span>

<span data-ttu-id="95f1f-136">**Microsoft 365 または Office 365**。</span><span class="sxs-lookup"><span data-stu-id="95f1f-136">**Microsoft 365 or Office 365**.</span></span> <span data-ttu-id="95f1f-137">これは、Microsoft 365 または Office 365 のサービスをサポートするネットワーク セグメントです。</span><span class="sxs-lookup"><span data-stu-id="95f1f-137">This is the network segment that supports Microsoft 365 or Office 365 services.</span></span> <span data-ttu-id="95f1f-138">これは世界中に分散しているネットワークで、ほとんどの場所で顧客ネットワークに近接するエッジを使用しています。</span><span class="sxs-lookup"><span data-stu-id="95f1f-138">It is distributed worldwide with edges in proximity to the customer network in most locations.</span></span> <span data-ttu-id="95f1f-139">機能には、トランスポート リレー、会議サーバー、およびメディア プロセッサが含まれます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-139">Functions include Transport Relay, conferencing server, and Media Processor.</span></span>

<span data-ttu-id="95f1f-140">**Express Route (オプション)**。</span><span class="sxs-lookup"><span data-stu-id="95f1f-140">**Express Route (optional)**.</span></span> <span data-ttu-id="95f1f-141">これはネットワーク全体の一部で、Microsoft 365 または Office 365 ネットワークへの専用のプライベート接続を提供するネットワーク セグメントです。</span><span class="sxs-lookup"><span data-stu-id="95f1f-141">This is the network segment that is part of your overall network that will give you a dedicated, private connection to the Microsoft 365 or Office 365 network.</span></span>

### <a name="types-of-traffic"></a><span data-ttu-id="95f1f-142">トラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="95f1f-142">Types of traffic</span></span>

<span data-ttu-id="95f1f-143">**リアルタイムのメディア**。</span><span class="sxs-lookup"><span data-stu-id="95f1f-143">**Real-time media**.</span></span> <span data-ttu-id="95f1f-144">オーディオ、ビデオ、および画面共有のワークロードをサポートする RTP (リアルタイム転送プロトコル) 内にカプセル化されたデータ。</span><span class="sxs-lookup"><span data-stu-id="95f1f-144">Data encapsulated within Real-time Transport Protocol (RTP) that supports audio, video, and screen sharing workloads.</span></span> <span data-ttu-id="95f1f-145">一般的に、メディア トラッフィックは遅延に対して非常に敏感なため、このトラフィックはできるだけ直接的な経路を使用し、トランスポート層プロトコルとして TCP ではなく、品質の点で対話的なリアルタイム メディアには最良のトランスポートである UDP を使用します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-145">In general, media traffic is highly latency sensitive, so you would want this traffic to take the most direct path possible, and to use UDP versus TCP as the transport layer protocol, which is the best transport for interactive real time media from a quality perspective.</span></span> <span data-ttu-id="95f1f-146">(注: 最後の手段として、メディアには TCP/IP を使用し、HTTP プロトコル内でトンネリングすることができますが、品質に悪影響を与える可能性があるため、お勧めできません)。RTP フローは SRTP を使用して保護され、ペイロードのみが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-146">(Note that as a last resort, media can use TCP/IP and also be tunneled within the HTTP protocol, but it is not recommended due to bad quality implications.) RTP flow is secured using SRTP, in which only the payload is encrypted.</span></span>

<span data-ttu-id="95f1f-147">**シグナリング**。</span><span class="sxs-lookup"><span data-stu-id="95f1f-147">**Signaling**.</span></span> <span data-ttu-id="95f1f-148">クライアントとサーバーまたはその他のクライアントとの間の通信リンクで、アクティビティの制御 (たとえば、通話が開始された場合など) とインスタント メッセージの配信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-148">The communication link between the client and server, or other clients that are used to control activities (for example, when a call is initiated), and deliver instant messages.</span></span> <span data-ttu-id="95f1f-149">ほとんどのシグナリング トラフィックは HTTPS ベースの REST インターフェイスを使用しますが、一部の シナリオ (Microsoft 365 または Office 365 とセッション ボーダー コントローラーの間の接続など) では、SIP プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-149">Most signaling traffic uses the HTTPS-based REST interfaces, though in some scenarios (for example, connection between Microsoft 365 or Office 365 and a Session Border Controller) it uses SIP protocol.</span></span> <span data-ttu-id="95f1f-150">このトラフィックは遅延に対してあまり敏感ではありませんが、エンドポイント間に数秒を超える遅延があった場合、サービス停止や通話のタイムアウトが発生する可能性がある点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="95f1f-150">It's important to understand that this traffic is much less sensitive to latency but may cause service outages or call timeouts if latency between the endpoints exceeds several seconds.</span></span>

### <a name="connectivity-to-microsoft-365-or-office-365"></a><span data-ttu-id="95f1f-151">Microsoft 365 または Office 365 への接続</span><span class="sxs-lookup"><span data-stu-id="95f1f-151">Connectivity to Microsoft 365 or Office 365</span></span>

<span data-ttu-id="95f1f-152">Teams を使用するには、[インターネットへの接続](/office365/enterprise/assessing-network-connectivity)が必要です。</span><span class="sxs-lookup"><span data-stu-id="95f1f-152">Teams requires [connectivity to the Internet](/office365/enterprise/assessing-network-connectivity).</span></span> <span data-ttu-id="95f1f-153">Teams のエンドポイントの URL と IP アドレスの範囲は、「[Office 365 の URL と IP アドレスの範囲](/office365/enterprise/urls-and-ip-address-ranges)」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="95f1f-153">Teams endpoint URLs and IP address ranges are listed in [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges).</span></span> <span data-ttu-id="95f1f-154">(注: TCP ポート 80 および 443、UDP ポート 3478 から3481 へのオープン接続が必要です。) さらに、Teams は Skype for Business Online に依存しているため、Skype for Business Online もインターネットに接続されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="95f1f-154">(Note that open connectivity to TCP ports 80 and 443, and to UDP ports 3478 through 3481, is required.) Furthermore, Teams has a dependency on Skype for Business Online, which must also be connected to the Internet.</span></span>

<span data-ttu-id="95f1f-155">Teams のメディア フロー接続は、標準の IETF ICE (Interactive Connectivity Establishment) の手順に従って実装されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-155">Teams media flows connectivity is implemented using standard IETF Interactive Connectivity Establishment (ICE) procedures.</span></span>

### <a name="interoperability-restrictions"></a><span data-ttu-id="95f1f-156">相互運用性の制限</span><span class="sxs-lookup"><span data-stu-id="95f1f-156">Interoperability restrictions</span></span>

<span data-ttu-id="95f1f-157">**サードパーティ製メディア リレー**。</span><span class="sxs-lookup"><span data-stu-id="95f1f-157">**Third-party media relays**.</span></span> <span data-ttu-id="95f1f-158">Teams のメディア フロー (つまり、いずれかのメディア エンドポイントが Teams である場合) は、Teams または Skype for Business のネイティブ メディア リレーのみを通過できます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-158">A Teams media flow (that is, where one of the media endpoints is Teams) may traverse only Teams or Skype for Business native media relays.</span></span> <span data-ttu-id="95f1f-159">サードパーティ製メディア リレーとの相互運用性は、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="95f1f-159">Interoperability with a third-party media relay is not supported.</span></span> <span data-ttu-id="95f1f-160">(注: PSTN との境界にあるサードパーティの SBC は、RTP/RTCP ストリーム を終了し、SRTP を介して保護されている必要があり、次のホップにリレーさせることはできません)。</span><span class="sxs-lookup"><span data-stu-id="95f1f-160">(Note that a third-party SBC on the boundary with PSTN must terminate RTP/RTCP stream, secured using SRTP, and not relay it to the next hop.)</span></span>

<span data-ttu-id="95f1f-161">**サードパーティの SIP プロキシ サーバー**。</span><span class="sxs-lookup"><span data-stu-id="95f1f-161">**Third-party SIP proxy servers**.</span></span> <span data-ttu-id="95f1f-162">サードパーティの SBC および/またはゲートウェイを使用する Teams のシグナリング SIP ダイアログは、 Teams または Skype for Business のネイティブ SIP プロキシを通過する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="95f1f-162">A Teams signaling SIP dialog with a third-party SBC and/or gateway may traverse Teams or Skype for Business native SIP proxies.</span></span> <span data-ttu-id="95f1f-163">サードパーティ製 SIP プロキシとの相互運用性は、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="95f1f-163">Interoperability with a third-party SIP proxy is not supported.</span></span>

<span data-ttu-id="95f1f-164">**サードパーティ製 B2BUA (または SBC)**。</span><span class="sxs-lookup"><span data-stu-id="95f1f-164">**Third-party B2BUA (or SBC)**.</span></span> <span data-ttu-id="95f1f-165">PSTN との間の Teams メディア フローは、サードパーティ製 SBC で終了します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-165">A Teams media flow to and from the PSTN is terminated by a third-party SBC.</span></span> <span data-ttu-id="95f1f-166">ただし、Teams ネットワーク内のサードパーティー製 SBC との相互運用性 (つまり、サードパーティ製 SBC が Teams と Skype for Business の 2 つのエンドポイントの間を仲介しています) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="95f1f-166">However, interoperability with a third-party SBC within the Teams network (where a third-party SBC mediates two Teams or Skype for Business endpoints) is not supported.</span></span>

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a><span data-ttu-id="95f1f-167">Microsoft Teams で推奨されないテクノロジ</span><span class="sxs-lookup"><span data-stu-id="95f1f-167">Technologies that are not recommended with Microsoft Teams</span></span>

<span data-ttu-id="95f1f-168">**VPN ネットワーク**。</span><span class="sxs-lookup"><span data-stu-id="95f1f-168">**VPN network**.</span></span> <span data-ttu-id="95f1f-169">メディア トラフィック (またはフロー 2') にはお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="95f1f-169">It is not recommended for media traffic (or flow 2').</span></span> <span data-ttu-id="95f1f-170">[Lync メディアが VPN トンネルをバイパス可能にする](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210) で指定されているように、VPN クライアントはスプリット VPN を使用し、外部の非 VPN ユーザーなどのメディア トラフィックをルーティングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="95f1f-170">The VPN client should use split VPN and route media traffic like any external non-VPN user, as specified in [Enabling Lync media to bypass a VPN tunnel](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210).</span></span>

> [!NOTE]
> <span data-ttu-id="95f1f-171">タイトルは Lync となっていますが、Teams にも適用できます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-171">Although the title indicates Lync, it is applicable to Teams as well.</span></span>

<span data-ttu-id="95f1f-172">**パケット シェーパー**。</span><span class="sxs-lookup"><span data-stu-id="95f1f-172">**Packet shapers**.</span></span> <span data-ttu-id="95f1f-173">あらゆる種類のパケット スニッパー、パケット検査、またはパケット シェーパーのデバイスの使用はお勧めしません。品質が大きく低下する場合があります。</span><span class="sxs-lookup"><span data-stu-id="95f1f-173">Any kind of packet snippers, packet inspection, or packet shaper devices are not recommended and may degrade quality significantly.</span></span>

### <a name="principles"></a><span data-ttu-id="95f1f-174">原則</span><span class="sxs-lookup"><span data-stu-id="95f1f-174">Principles</span></span>

<span data-ttu-id="95f1f-175">Microsoft Teams の通話フローを理解するのに役立つ、4つの一般的な原則があります。</span><span class="sxs-lookup"><span data-stu-id="95f1f-175">There are four general principles that help you understand call flows for Microsoft Teams:</span></span>

- <span data-ttu-id="95f1f-176">Microsoft Teams の会議は、最初の参加者が参加したのと同じ地域の Microsoft 365 または Office 365 によってホストされます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-176">A Microsoft Teams conference is hosted by Microsoft 365 or Office 365 in the same region where the first participant joined.</span></span> <span data-ttu-id="95f1f-177">(注: トポロジによってこのルールの例外が発生する場合については、この記事で説明します。適切な通話フローも示されます。)</span><span class="sxs-lookup"><span data-stu-id="95f1f-177">(Note that if there are exceptions to this rule in some topologies, they will be described in this document and illustrated by an appropriate call flow.)</span></span>

- <span data-ttu-id="95f1f-178">Microsoft 365 または Office 365 の Teams メディア エンドポイントは、通話の種類に基づいてではなく、メディア処理のニーズに基づいて使用されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-178">A Teams media endpoint in Microsoft 365 or Office 365 is used based on media processing needs and not based on call type.</span></span> <span data-ttu-id="95f1f-179">(たとえば、ポイントツーポイントの通話では、トランスクリプションおよび/または録音のためのメディア処理に、クラウド内のメディア エンドポイントを使用する場合がありますが、参加者が 2 人の会議ではクラウド内のメディア エンドポイントを使用しない場合があります。) ただし、ほとんどの会議では、ミキシングおよびルーティングのために、会議がホストされる場所に割り当てられているメディア エンドポイントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-179">(For example, a point-to-point call may use a media endpoint in the cloud to process media for transcription or recording, while a conference with two participants may not use any media endpoint in the cloud.) However, most conferences will use a media endpoint for mixing and routing purposes, allocated where the conference is hosted.</span></span> <span data-ttu-id="95f1f-180">クライアントからメディア エンドポイントに送信されるメディア トラフィックは、直接ルーティングされる場合と、顧客ネットワークのファイアウォール制限のために必要な場合は、Microsoft 365 または Office 365 でトランスポート リレーを使用する場合とがあります。</span><span class="sxs-lookup"><span data-stu-id="95f1f-180">The media traffic sent from a client to the media endpoint may be routed directly or use a Transport Relay in Microsoft 365 or Office 365 if required due to customer network firewall restrictions.</span></span>

- <span data-ttu-id="95f1f-181">ピアツーピア通話のメディア トラフィックは、通話でクラウド内のメディア エンドポイントが要求されていない限り (上の原則を参照)、使用できる最も直接的なルートを使用します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-181">Media traffic for peer-to-peer calls take the most direct route that is available, assuming that the call doesn't mandate a media endpoint in the cloud (see previous principle).</span></span> <span data-ttu-id="95f1f-182">リモート ピア (クライアント) への直接のルートが優先されますが、このルートが利用できない場合は、1 つまたは複数のトランスポート リレーがトラフィックを中継します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-182">The preferred route is direct to the remote peer (client), but if that route isn't available, then one or more Transport Relays will relay traffic.</span></span> <span data-ttu-id="95f1f-183">メディアの品質に影響を与えるため、メディア トラフィックがパケット シェーパーや VPN サーバーなどのサーバーを通過しないことが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-183">It is recommended that media traffic shall not transverse servers such as packet shapers, VPN servers, and so on, since this will impact the media quality.</span></span>

- <span data-ttu-id="95f1f-184">シグナリング トラフィックは、常にユーザーに最も近いサーバーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-184">Signaling traffic always goes to the closest server to the user.</span></span>

<span data-ttu-id="95f1f-185">選択されているメディア経路の詳細については、「[Microsoft Teams のメディアフローを理解する-BRK4016](https://www.youtube.com/watch?v=1tmHMIlAQdo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95f1f-185">To learn more about the details on the media path that is chosen, see [Understanding Media Flows in Microsoft Teams - BRK4016](https://www.youtube.com/watch?v=1tmHMIlAQdo).</span></span>

## <a name="call-flows-in-various-topologies"></a><span data-ttu-id="95f1f-186">さまざまなトポロジにおける通話フロー</span><span class="sxs-lookup"><span data-stu-id="95f1f-186">Call flows in various topologies</span></span>

### <a name="teams-topology"></a><span data-ttu-id="95f1f-187">Teams のトポロジ</span><span class="sxs-lookup"><span data-stu-id="95f1f-187">Teams topology</span></span>

<span data-ttu-id="95f1f-188">このトポロジは、Skype for Business Server や電話システムのダイレクト ルーティングなどのオンプレミスの展開がない状態でクラウドから Teams のサービスを利用するお客様に使用されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-188">This topology is used by customers that leverage Teams services from the cloud without any on-premises deployment, such as Skype for Business Server or Phone System Direct Routing.</span></span> <span data-ttu-id="95f1f-189">また、Microsoft 365 または Office 365 のインターフェイスは、Azure Express Route を使用せずにインターネット経由で実行されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-189">In addition, the interface to Microsoft 365 or Office 365 is done over the Internet without Azure Express Route.</span></span>

<span data-ttu-id="95f1f-190">[![Microsoft Teams オンライン通話フロー 図 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-190">[![Microsoft Teams Online Call Flows Figure 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span></span>

<span data-ttu-id="95f1f-191">*図 1 - Teams のトポロジ*</span><span class="sxs-lookup"><span data-stu-id="95f1f-191">*Figure 1 - Teams topology*</span></span>

<span data-ttu-id="95f1f-192">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="95f1f-192">Note that:</span></span>

- <span data-ttu-id="95f1f-193">上の図の矢印の方向は、エンタープライズ境界での接続に影響を与える、通信の開始方向を反映します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-193">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="95f1f-194">メディアの UDP については、最初のパケットは逆方向に流れる場合がありますが、これらのパケットは、別の方向へのパケットが流れるまでブロックされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="95f1f-194">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>
- <span data-ttu-id="95f1f-195">Teams は、Skype for Business Online と並行して展開されます。そのため、クライアントは "Teams/SFB ユーザー" として表示されています。</span><span class="sxs-lookup"><span data-stu-id="95f1f-195">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user."</span></span>

<span data-ttu-id="95f1f-196">次のオプションのトポロジの詳細については、この記事の後の方で説明します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-196">You can find more information on the following optional topologies later in the article:</span></span>

- <span data-ttu-id="95f1f-197">Skype for Business のオンプレミスの展開については、「**Teams ハイブリッド トポロジ**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95f1f-197">Skype for Business on-premises deployment is described in **Teams hybrid topology**.</span></span>
- <span data-ttu-id="95f1f-198">電話システムのダイレクト ルーティング (PSTN 接続用) については、「**ダイレクト ルーティングを使用する Teams**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95f1f-198">Phone System Direct Routing (for PSTN connectivity) is described in **Teams with Direct Routing topology**.</span></span>
- <span data-ttu-id="95f1f-199">Express Route については、「**Express Route による Teams の最適化**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95f1f-199">Express Route is described in **Teams with Express Route optimization**.</span></span>

<span data-ttu-id="95f1f-200">**フローの説明**</span><span class="sxs-lookup"><span data-stu-id="95f1f-200">**Flow descriptions**:</span></span>

- <span data-ttu-id="95f1f-201">**フロー 2** – ユーザーが、Teams の操作の一部として顧客ネットワーク上で開始するインターネットへのフローを表します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-201">**Flow 2** – Represents a flow initiated by a user on the customer network to the Internet as a part of the user's Teams experience.</span></span> <span data-ttu-id="95f1f-202">この種類のフローの例は、DNS とピアツーピア メディアです。</span><span class="sxs-lookup"><span data-stu-id="95f1f-202">Examples of these flows are DNS and peer-to-peer media.</span></span>
- <span data-ttu-id="95f1f-203">**フロー 2'** – Teams のリモート モバイル ユーザーが VPN を使用して開始する顧客ネットワークへのフローを表します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-203">**Flow 2'** – Represents a flow initiated by a remote mobile Teams user, with VPN to the customer network.</span></span>
- <span data-ttu-id="95f1f-204">**フロー 3** – Teams のリモート モバイル ユーザーが開始する Microsoft 365 または Office 365/Teams のエンドポイントへのフローを表します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-204">**Flow 3** – Represents a flow initiated by a remote mobile Teams user to Microsoft 365 or Office 365/Teams endpoints.</span></span>
- <span data-ttu-id="95f1f-205">**フロー 4** – 顧客ネットワーク上のユーザーが開始する Microsoft 365 または Office 365/Teams のエンドポイントへのフローを表します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-205">**Flow 4** – Represents a flow initiated by a user on the customer network to Microsoft 365 or Office 365/Teams endpoints.</span></span>
- <span data-ttu-id="95f1f-206">**フロー 5** – Teams ユーザーと別の Teams ユーザーまたは顧客ネットワーク内の Skype for Business ユーザーの間のピアツーピア メディア フローを表します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-206">**Flow 5** – Represents a peer-to-peer media flow between a Teams user and another Teams or Skype for Business user within the customer network.</span></span>
- <span data-ttu-id="95f1f-207">**フロー 6** – Teams のリモート モバイル ユーザーと別の Teams のリモート モバイル ユーザーまたは Skype for Business ユーザーの間の、インターネットを介したピアツーピア メディア フローを表します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-207">**Flow 6** – Represents a peer-to-peer media flow between a remote mobile Teams user and another remote mobile Teams or Skype for Business user over the Internet.</span></span>

#### <a name="use-case-one-to-one"></a><span data-ttu-id="95f1f-208">ユース ケース: 一対一</span><span class="sxs-lookup"><span data-stu-id="95f1f-208">Use case: One-to-one</span></span>

<span data-ttu-id="95f1f-209">一対一の通話では共通のモデルが使用され、発信者は、ローカル、リレー、および再帰 (リレーから見える、クライアントのパブリック IP アドレス) の候補を含む、IP アドレス/ポートから成る候補のセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-209">One-to-one calls use a common model in which the caller will obtain a set of candidates consisting of IP addresses/ports, including local, relay, and reflexive (public IP address of client as seen by the relay) candidates.</span></span> <span data-ttu-id="95f1f-210">発信者は、これらの候補を通話相手に送信します。通話を受けた相手は、同様の候補のセットを取得し、それを発信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-210">The caller sends these candidates to the called party; the called party also obtains a similar set of candidates and sends them to the caller.</span></span> <span data-ttu-id="95f1f-211">STUN 接続確認メッセージは、発信者/受信者のメディア パスはどれが機能しているかを判断し、機能しているパスの中から最適のものを選択します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-211">STUN connectivity check messages are used to find which caller/called party media paths work, and the best working path is selected.</span></span> <span data-ttu-id="95f1f-212">その後、選択された候補のペアを使用してメディア (つまり、SRTP を介して保護された RTP/RTCP パケット) が送信されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-212">Media (that is, RTP/RTCP packets secured using SRTP) are then sent using the selected candidate pair.</span></span> <span data-ttu-id="95f1f-213">トランスポート リレーは、Microsoft 365 および Office 365 の一部として展開されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-213">The Transport relay is deployed as part of Microsoft 365 and Office 365.</span></span>

<span data-ttu-id="95f1f-214">ローカル IP アドレス/ポートの候補または再帰候補に接続がある場合、クライアント間のダイレクト パス (または NAT 経由) がメディア用に選択されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-214">If the local IP address/port candidates or the reflexive candidates have connectivity, then the direct path between the clients (or using a NAT) will be selected for media.</span></span> <span data-ttu-id="95f1f-215">クライアントが両方とも顧客ネットワーク上にいる場合は、ダイレクト パスが選択されるはずです。</span><span class="sxs-lookup"><span data-stu-id="95f1f-215">If the clients are both on the customer network, then the direct path should be selected.</span></span> <span data-ttu-id="95f1f-216">これには、顧客ネットワーク内での UDP への直接接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="95f1f-216">This requires direct UDP connectivity within the customer network.</span></span> <span data-ttu-id="95f1f-217">クライアントが両方とも Nomadic Crowd のユーザーである場合、NAT/ファイアウォールによっては、メディアは直接接続を使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="95f1f-217">If the clients are both nomadic cloud users, then depending on the NAT/firewall, media may use direct connectivity.</span></span>

<span data-ttu-id="95f1f-218">一方のクライアントが顧客ネットワーク内にいて、もう一方のクライアントが外部にいる (モバイル クラウド ユーザーなど) 場合、ローカル候補と再帰候補の間の直接接続は正常に機能しない可能性が高いです。</span><span class="sxs-lookup"><span data-stu-id="95f1f-218">If one client is internal on the customer network and one client is external (for example, a mobile cloud user), then it is unlikely that direct connectivity between the local or reflexive candidates is working.</span></span> <span data-ttu-id="95f1f-219">この場合、どちらかのクライアントが、トランスポート リレー候補のいずれかを使用するというオプションがあります (たとえば、内部のクライアントが Microsoft 365 または Office 365 のトランスポート リレーからリレー候補を取得した場合は、外部のクライアントは STUN/RTP/RTCP パケットをトランスポート リレーに送信できる必要があります)。</span><span class="sxs-lookup"><span data-stu-id="95f1f-219">In this case, an option is to use one of the Transport Relay candidates from either client (for example, the internal client obtained a relay candidate from the Transport relay in Microsoft 365 or Office 365; the external client needs to be able to send STUN/RTP/RTCP packets to the transport relay).</span></span> <span data-ttu-id="95f1f-220">別のオプションとして、内部のクライアントが、モバイル クラウド クライアントが取得したリレー候補に送信するというものです。</span><span class="sxs-lookup"><span data-stu-id="95f1f-220">Another option is the internal client sends to the relay candidate obtained by the mobile cloud client.</span></span> <span data-ttu-id="95f1f-221">メディアの場合は UDP 接続を強く推奨しますが、TCP もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="95f1f-221">Note that, although UDP connectivity for media is highly recommended, TCP is supported.</span></span>

<span data-ttu-id="95f1f-222">**大まかな手順**:</span><span class="sxs-lookup"><span data-stu-id="95f1f-222">**High-level steps**:</span></span>

1. <span data-ttu-id="95f1f-223">Teams ユーザー A が、フロー 2 経由で URL ドメイン名 (DNS) を解決します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-223">Teams User A resolves URL domain name (DNS) using flow 2.</span></span>
1. <span data-ttu-id="95f1f-224">Teams ユーザー A が、フロー 4 経由で Teams トランスポート リレーでメディア リレー ポートを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-224">Teams User A allocates a media Relay port on Teams Transport Relay using flow 4.</span></span>
1. <span data-ttu-id="95f1f-225">Teams ユーザー A は、フロー 4 経由で Microsoft 365ま たは Office 365 へ「招待」を ICE 候補と共に送信します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-225">Teams User A sends "invite" with ICE candidates using flow 4 to Microsoft 365 or Office 365.</span></span>
1. <span data-ttu-id="95f1f-226">Microsoft 365 または Office 365 は、フロー 4 経由で Teams ユーザー B に通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-226">Microsoft 365 or Office 365 sends notification to Teams User B using flow 4.</span></span>
1. <span data-ttu-id="95f1f-227">Teams ユーザー B が、フロー 4 経由で Teams トランスポート リレーでメディア リレー ポートを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-227">Teams User B allocates a media Relay port on Teams Transport Relay using flow 4.</span></span>
1. <span data-ttu-id="95f1f-228">Teams ユーザー B が、フロー 4 経由で「回答」 を ICE 候補と共に送信し、これはフロー 4 経由で Teams ユーザー A に戻されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-228">Teams User B sends "answer" with ICE candidates using flow 4, which is forwarded back to Teams User A using Flow 4.</span></span>
1. <span data-ttu-id="95f1f-229">Teams ユーザー A および Teams ユーザー B が ICE 接続テストを実行し、最適なメディア パスが選択されます (下の図でさまざまなユース ケースをご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="95f1f-229">Teams User A and Teams User B invoke ICE connectivity tests and the best available media path is selected (see diagrams below for various use cases).</span></span>
1. <span data-ttu-id="95f1f-230">Teams ユーザーが、フロー 4 経由でテレメトリを Microsoft 365 または Office 365 に送信します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-230">Teams Users send telemetry to Microsoft 365 or Office 365 using flow 4.</span></span>

<span data-ttu-id="95f1f-231">**顧客ネットワーク内:**</span><span class="sxs-lookup"><span data-stu-id="95f1f-231">**Within customer network:**</span></span>

<span data-ttu-id="95f1f-232">[![Microsoft Teams オンライン通話フロー 図 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-232">[![Microsoft Teams Online Call Flows Figure 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span></span>

<span data-ttu-id="95f1f-233">*図 2 - 顧客ネットワーク内*</span><span class="sxs-lookup"><span data-stu-id="95f1f-233">*Figure 2 - Within customer network*</span></span>

<span data-ttu-id="95f1f-234">手順 7 では、ピアツーピア メディア フロー 5 が選択されています。</span><span class="sxs-lookup"><span data-stu-id="95f1f-234">In step 7, peer-to-peer media flow 5 is selected.</span></span>

<span data-ttu-id="95f1f-235">メディアは双方向です。</span><span class="sxs-lookup"><span data-stu-id="95f1f-235">Media is bidirectional.</span></span> <span data-ttu-id="95f1f-236">フロー 5 の方向は、この記事のすべてのフローの場合と同様、一方が通信を開始したことを接続の観点から示します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-236">The direction of flow 5 indicates that one side initiates the communication from a connectivity perspective, consistent with all the flows in this document.</span></span> <span data-ttu-id="95f1f-237">このケースでは両方のエンドポイントが顧客ネットワーク内にあるため、使用されている方向を考慮する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="95f1f-237">In this case, it doesn't matter which direction is used because both endpoints are within the customer network.</span></span>

<span data-ttu-id="95f1f-238">**顧客ネットワークから外部ユーザーへ (メディアは Teams トランスポート リレーが中継):**</span><span class="sxs-lookup"><span data-stu-id="95f1f-238">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="95f1f-239">[![Microsoft Teams オンライン通話フロー 図 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-239">[![Microsoft Teams Online Call Flows Figure 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span></span>

<span data-ttu-id="95f1f-240">*図 3 - 顧客ネットワークから外部ユーザーへ (メディアは Teams トランスポート リレーが中継):*</span><span class="sxs-lookup"><span data-stu-id="95f1f-240">*Figure 3 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="95f1f-241">手順 7 では、フロー 4 (顧客ネットワークからMicrosoft 365 または Office 365) とフロー 3 (Teams リモート モバイル ユーザーからMicrosoft 365 または Office 365) が選択されています。</span><span class="sxs-lookup"><span data-stu-id="95f1f-241">In step 7, flow 4, from customer network to Microsoft 365 or Office 365, and flow 3, from remote mobile Teams user to Microsoft 365 or Office 365, are selected.</span></span> <span data-ttu-id="95f1f-242">これらのフローは、Microsoft 365 または Office 365 内の Teams トランスポート リレーにより中継されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-242">These flows are relayed by Teams Transport Relay within Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="95f1f-243">メディアは双方向で、どちら側が通信を開始したかを接続の観点から方向で示します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-243">Media is bidirectional, where direction indicates which side initiates the communication from a connectivity perspective.</span></span> <span data-ttu-id="95f1f-244">この場合、これらのフローは、異なるトランスポート プロトコルとアドレスを使用して、シグナリングとメディアに使用されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-244">In this case, these flows are used for signaling and media, using different transport protocols and addresses.</span></span>

<span data-ttu-id="95f1f-245">**顧客ネットワークから外部ユーザーへ (ダイレクト メディア):**</span><span class="sxs-lookup"><span data-stu-id="95f1f-245">**Customer network to external user (direct media):**</span></span>

<span data-ttu-id="95f1f-246">[![Microsoft Teams オンライン通話フロー 図 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-246">[![Microsoft Teams Online Call Flows Figure 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span></span>

<span data-ttu-id="95f1f-247">*図 4 - 顧客ネットワークから外部ユーザーへ (ダイレクト メディア)*</span><span class="sxs-lookup"><span data-stu-id="95f1f-247">*Figure 4 - Customer network to external user (direct media)*</span></span>

<span data-ttu-id="95f1f-248">手順 7 では、顧客ネットワークから インターネット (クライアントのピア) のフロー 2 が選択されています。</span><span class="sxs-lookup"><span data-stu-id="95f1f-248">In step 7, flow 2, from customer network to the Internet (client's peer), is selected.</span></span>

- <span data-ttu-id="95f1f-249">リモート モバイル ユーザー (Microsoft 365 または Office 365 経由では中継されていません) とのダイレクト メディアは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="95f1f-249">Direct media with remote mobile user (not relayed through Microsoft 365 or Office 365) is optional.</span></span> <span data-ttu-id="95f1f-250">Microsoft 365 または Office 365 のトランスポート リレー経由のメディア パスを強制するために、顧客はこのパスをブロックできることを意味します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-250">In other words, customer may block this path to enforce a media path through Transport Relay in Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="95f1f-251">メディアは双方向です。</span><span class="sxs-lookup"><span data-stu-id="95f1f-251">Media is bidirectional.</span></span> <span data-ttu-id="95f1f-252">モバイル ユーザーへのフロー 2 の方向は、一方が通信を開始したことを接続の観点から示します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-252">The direction of flow 2 to remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

<span data-ttu-id="95f1f-253">**VPN から内部ユーザーへ (メディアは Teams トランスポート リレーが中継)**</span><span class="sxs-lookup"><span data-stu-id="95f1f-253">**VPN user to internal user (media relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="95f1f-254">[![Microsoft Teams オンライン通話フロー 図 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-254">[![Microsoft Teams Online Call Flows Figure 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span></span>

<span data-ttu-id="95f1f-255">*図 5 - VPN ユーザーから内部ユーザーへ (メディアは Teams トランスポート リレーが中継)*</span><span class="sxs-lookup"><span data-stu-id="95f1f-255">*Figure 5 - VPN user to internal user (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="95f1f-256">VPN と顧客ネットワークとの間のシグナリングは、フロー 2' を使用しています。</span><span class="sxs-lookup"><span data-stu-id="95f1f-256">Signaling between the VPN to the customer network is using flow 2'.</span></span> <span data-ttu-id="95f1f-257">顧客ネットワークと Microsoft 365 または Office 365 の間のシグナリングはフロー 4 を使用します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-257">Signaling between the customer network and Microsoft 365 or Office 365 is using flow 4.</span></span> <span data-ttu-id="95f1f-258">ただし、メディアは VPN をバイパスし、Microsoft 365 または Office 365 の Teams メディア リレーを介してフロー 3 とフロー 4 経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-258">However, media bypasses the VPN and is routed using flows 3 and 4 through Teams media relay in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="95f1f-259">**VPN ユーザーから内部ユーザーへ (ダイレクトメディア)**</span><span class="sxs-lookup"><span data-stu-id="95f1f-259">**VPN user to internal user (direct media)**</span></span>

<span data-ttu-id="95f1f-260">[![Microsoft Teams オンライン通話フロー 図 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-260">[![Microsoft Teams Online Call Flows Figure 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span></span>

<span data-ttu-id="95f1f-261">*図 6 - VPN ユーザーから内部ユーザーへ (ダイレクトメディア)*</span><span class="sxs-lookup"><span data-stu-id="95f1f-261">*Figure 6 - VPN user to internal user (direct media)*</span></span>

<span data-ttu-id="95f1f-262">VPN と顧客ネットワークとの間のシグナリングは、フロー 2' を使用しています。</span><span class="sxs-lookup"><span data-stu-id="95f1f-262">Signaling between the VPN to the customer network is using flow 2'.</span></span> <span data-ttu-id="95f1f-263">顧客ネットワークと Microsoft 365 または Office 365 の間のシグナリングはフロー 4 を使用します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-263">Signaling between the customer network and Microsoft 365 or Office 365 is using flow 4.</span></span> <span data-ttu-id="95f1f-264">ただし、メディアは VPN をバイパスし、フロー 2 (顧客ネットワークからインターネット) 経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-264">However, media bypasses the VPN and is routed using flow 2 from the customer network to the Internet.</span></span>

<span data-ttu-id="95f1f-265">メディアは双方向です。</span><span class="sxs-lookup"><span data-stu-id="95f1f-265">Media is bidirectional.</span></span> <span data-ttu-id="95f1f-266">モバイル ユーザーへのフロー 2 の方向は、一方が通信を開始したことを接続の観点から示します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-266">The direction of flow 2 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

<span data-ttu-id="95f1f-267">**VPN ユーザーから外部ユーザーへ (ダイレクトメディア)**</span><span class="sxs-lookup"><span data-stu-id="95f1f-267">**VPN user to external user (direct media)**</span></span>

<span data-ttu-id="95f1f-268">[![Microsoft Teams オンライン通話フロー 図 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-268">[![Microsoft Teams call flows Figure 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span></span>

<span data-ttu-id="95f1f-269">*図 7 - VPN ユーザーから外部ユーザーへ (ダイレクトメディア)*</span><span class="sxs-lookup"><span data-stu-id="95f1f-269">*Figure 7 - VPN user to external user (direct media)*</span></span>

<span data-ttu-id="95f1f-270">VPN ユーザーと顧客ネットワーク間のシグナリングにはフロー 2 ' を使用して、フロー 4 を Microsoft 365 または Office 365 に使用します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-270">Signaling between the VPN user to the customer network is using flow 2' and using flow 4 to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="95f1f-271">ただし、メディアは VPN をバイパスし、フロー 6 経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-271">However, media bypasses VPN and is routed using flow 6.</span></span>

<span data-ttu-id="95f1f-272">メディアは双方向です。</span><span class="sxs-lookup"><span data-stu-id="95f1f-272">Media is bidirectional.</span></span> <span data-ttu-id="95f1f-273">モバイル ユーザーへのフロー 6 の方向は、一方が通信を開始したことを接続の観点から示します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-273">The direction of flow 6 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

#### <a name="use-case-teams-to-pstn-through-microsoft-365-or-office-365-trunk"></a><span data-ttu-id="95f1f-274">ユース ケース: Microsoft 365 または Office 365 の トラ ンクを使用して、Teams から PSTNへ。</span><span class="sxs-lookup"><span data-stu-id="95f1f-274">Use Case: Teams to PSTN through Microsoft 365 or Office 365 Trunk</span></span>

<span data-ttu-id="95f1f-275">Microsoft 365 および Office 365 には、公衆交換電話網 (PSTN) から、通話を発信および受信できる電話システムがあります。</span><span class="sxs-lookup"><span data-stu-id="95f1f-275">Microsoft 365 and Office 365 have a Phone System that allows placing and receiving calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="95f1f-276">PSTN トランクが電話システムの通話プランで接続されている場合、このユース ケースに関しては特別な接続要件はありません。</span><span class="sxs-lookup"><span data-stu-id="95f1f-276">If the PSTN trunk is connected using the Phone System Calling Plan, then there are no special connectivity requirements for this use case.</span></span> <span data-ttu-id="95f1f-277">(自社のオンプレミスの PSTN トランクを Microsoft 365 または Office 365 に接続する場合は、電話システムのダイレクト ルーティングを使用できます。)</span><span class="sxs-lookup"><span data-stu-id="95f1f-277">(If you want to connect your own on-premises PSTN trunk to Microsoft 365 or Office 365, you can use Phone System Direct Routing.)</span></span>

<span data-ttu-id="95f1f-278">[![Microsoft Teams オンライン通話フロー 図 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-278">[![Microsoft Teams Online Call Flows Figure 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span></span>

<span data-ttu-id="95f1f-279">*図 8 - Office 365 トランク経由で Teams から PSTN へ*</span><span class="sxs-lookup"><span data-stu-id="95f1f-279">*Figure 8 - Teams to PSTN through Office 365 Trunk*</span></span>

#### <a name="use-case-teams-meeting"></a><span data-ttu-id="95f1f-280">ユースケース: Teams 会議</span><span class="sxs-lookup"><span data-stu-id="95f1f-280">Use case: Teams meeting</span></span>

<span data-ttu-id="95f1f-281">音声/ビデオ/画面共有 (VBSS) 会議サーバーは、Microsoft 365 および Office 365 の一部です。</span><span class="sxs-lookup"><span data-stu-id="95f1f-281">The audio/video/screen sharing (VBSS) conferencing server is part of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="95f1f-282">これには顧客ネットワークから到達可能である必要があるパブリック IP アドレスが含まれ、これは、Nomadic Cloud のクライアントから到達可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="95f1f-282">It has a public IP address that must be reachable from the customer network and must be reachable from a Nomadic Cloud client.</span></span> <span data-ttu-id="95f1f-283">各クライアント/エンドポイントは、会議サーバーに接続できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="95f1f-283">Each client/endpoint needs to be able to connect to the conferencing server.</span></span>

<span data-ttu-id="95f1f-284">内部クライアントは、一対一の通話で説明したのと同じ方法でローカル、再帰、およびリレー候補を取得します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-284">Internal clients will obtain local, reflexive, and relay candidates in the same manner as described for one-to-one calls.</span></span> <span data-ttu-id="95f1f-285">クライアントは、招待状にある会議サーバーにこれらの候補を送信します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-285">The clients will send these candidates to the conferencing server in an invite.</span></span> <span data-ttu-id="95f1f-286">会議サーバーは、公開されている IP アドレスを持っているためにリレーを使用しません。そのため、会議サーバーのローカル IP アドレス候補が返されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-286">The conferencing server does not use a relay since it has a publicly reachable IP address, so it responds with its local IP address candidate.</span></span> <span data-ttu-id="95f1f-287">クライアントと会議サーバーは、一対一の通話で説明したのと同じ方法で接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-287">The client and conferencing server will check connectivity in the same manner described for one-to-one calls.</span></span>

<span data-ttu-id="95f1f-288">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="95f1f-288">Note that:</span></span>

- <span data-ttu-id="95f1f-289">Teams のクライアントは Skype for business 会議に参加できず、Skype for Business のクライアントは Teams 会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="95f1f-289">Teams clients cannot join Skype for Business meetings, and Skype for Business clients cannot join Teams meetings.</span></span>

- <span data-ttu-id="95f1f-290">PSTN ユーザーは、会議開催者の PSTN 通話および/または会議のプロビジョニングに応じて、「ダイヤル イン」 または「ダイヤル アウト」することもできます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-290">A PSTN user optionally "Dials IN" or is "Dialed OUT", depending on the meeting's organizer PSTN Calling and/or conferencing provisioning.</span></span>

- <span data-ttu-id="95f1f-291">ゲスト ユーザーまたは顧客ユーザーはゲスト プライベートネットワークから参加できます。このネットワークは、厳密なルールを適用して FW/NAT を介して保護されています。</span><span class="sxs-lookup"><span data-stu-id="95f1f-291">A guest user or a customer user may join from a guest private network, which is protected using FW/NAT with strict rules.</span></span>

<span data-ttu-id="95f1f-292">[![Microsoft Teams オンライン通話フロー 図 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-292">[![Microsoft Teams Online Call Flows Figure 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span></span>

<span data-ttu-id="95f1f-293">*図 9 - Teams 会議*</span><span class="sxs-lookup"><span data-stu-id="95f1f-293">*Figure 9 - Teams Meeting*</span></span>

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a><span data-ttu-id="95f1f-294">ユース ケース: Skype for Business オンプレミス とのフェデレーション</span><span class="sxs-lookup"><span data-stu-id="95f1f-294">Use case: Federation with Skype for Business on premises</span></span>

<span data-ttu-id="95f1f-295">**Microsoft 365 または Office 365 で Teams トランスポート リレーによって中継されたメディア**</span><span class="sxs-lookup"><span data-stu-id="95f1f-295">**Media relayed by Teams Transport Relay in Microsoft 365 or Office 365**</span></span>

<span data-ttu-id="95f1f-296">[![Microsoft Teams オンライン通話フロー 図 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-296">[![Microsoft Teams Online Call Flows Figure 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span></span>

<span data-ttu-id="95f1f-297">*図 10 - Office 365 内の Teams トランスポート リレーにより中継されるメディア*</span><span class="sxs-lookup"><span data-stu-id="95f1f-297">*Figure 10 - Media relayed by Teams Transport Relay in Office 365*</span></span>

<span data-ttu-id="95f1f-298">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="95f1f-298">Note that:</span></span>

- <span data-ttu-id="95f1f-299">フェデレーションは、その性質上、2 つのテナント間の通信です。</span><span class="sxs-lookup"><span data-stu-id="95f1f-299">Federation is, by definition, a communication between two tenants.</span></span> <span data-ttu-id="95f1f-300">この例では、Teams を使用する テナント A は、Skype for Business オンプレミスを使用するテナント B とフェデレーションします。</span><span class="sxs-lookup"><span data-stu-id="95f1f-300">In this case, tenant A, which uses Teams, federates with tenant B, which uses Skype for Business on premises.</span></span> <span data-ttu-id="95f1f-301">もしテナント B も Microsoft 365 または Office 365 を使用していた場合は、Skype for Business クライアントは Microsoft 365 または Office 365 との接続にフロー 3 を使用していたはずです。</span><span class="sxs-lookup"><span data-stu-id="95f1f-301">If tenant B is also using Microsoft 365 or Office 365, then the Skype for Business client would have used flow 3 to connect with Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="95f1f-302">フェデレーションされた Skype for Business クライアントからオンプレミスの Skype for Business サーバーへのシグナリングとメディアについては、この記事では説明しません。</span><span class="sxs-lookup"><span data-stu-id="95f1f-302">Signaling and media from the federated Skype for Business client to on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="95f1f-303">説明をわかりやすくするためにこれを図に示します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-303">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="95f1f-304">Teams と Skype for Business の間のシグナリングは、ゲートウェイによりブリッジされます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-304">Signaling between Teams and Skype for Business is bridged by a gateway.</span></span>

- <span data-ttu-id="95f1f-305">メディアはこの場合、Teams トランスポート リレーにより、フロー 4 経由で 顧客ネットワークとリモートの Skype for Business クライアントに中継されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-305">Media in this case is relayed by Teams Transport Relay to the customer network and remote Skype for Business client using flow 4.</span></span>

<span data-ttu-id="95f1f-306">**フェデレーションされたテナントの Skype for Business メディア リレーによって中継されるメディア**</span><span class="sxs-lookup"><span data-stu-id="95f1f-306">**Media relayed by Skype for Business Media Relay in federated tenant**</span></span>

<span data-ttu-id="95f1f-307">[![Microsoft Teams オンライン通話フロー 図 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-307">[![Microsoft Teams Online Call Flows Figure 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span></span>

<span data-ttu-id="95f1f-308">*図 11 - フェデレーションされたテナントの Skype for Business メディア リレーによって中継されるメディア*</span><span class="sxs-lookup"><span data-stu-id="95f1f-308">*Figure 11 - Media relayed by Skype for Business Media Relay in federated tenant*</span></span>

<span data-ttu-id="95f1f-309">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="95f1f-309">Note that:</span></span>

- <span data-ttu-id="95f1f-310">フェデレーションされた Skype for Business クライアントからオンプレミスの Skype for Business サーバーへのシグナリングとメディアについては、この記事では説明しませんが、</span><span class="sxs-lookup"><span data-stu-id="95f1f-310">Signaling and media from the federated Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="95f1f-311">説明をわかりやすくするためにこれを図に示します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-311">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="95f1f-312">Teams と Skype for Business の間のシグナリングは、ゲートウェイによりブリッジされます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-312">Signaling between Teams and Skype for Business is bridged by a Gateway.</span></span>

- <span data-ttu-id="95f1f-313">メディアはこの場合、Skype for Business オンプレミス メディア リレーにより、フロー 2 経由で顧客ネットワークに中継されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-313">Media in this case is relayed by Skype for Business on-premises Media Relay to the customer network using flow 2.</span></span> <span data-ttu-id="95f1f-314">(フェデレーションされた顧客ネットワークのリモート メディア リレーへ Teams ユーザーからのトラフィックは、逆方向のトラフィックが流れ始めるまで、メディアリレーによって最初はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-314">(Note that traffic from Teams user to the remote Media Relay in the federated customer network will be initially blocked by the Media Relay until traffic in the reverse direction starts to flow.</span></span> <span data-ttu-id="95f1f-315">ただし、双方向フローは、双方向の接続を開きます)。</span><span class="sxs-lookup"><span data-stu-id="95f1f-315">However, the bidirectional flow will open connectivity in both directions.)</span></span>

<span data-ttu-id="95f1f-316">**直接 (ピアツーピア)**</span><span class="sxs-lookup"><span data-stu-id="95f1f-316">**Direct (peer-to-peer)**</span></span>

<span data-ttu-id="95f1f-317">[![Microsoft Teams オンライン通話フロー 図 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-317">[![Microsoft Teams Online Call Flows Figure 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span></span>

<span data-ttu-id="95f1f-318">*図 12 - 直接 (ピアツーピア)*</span><span class="sxs-lookup"><span data-stu-id="95f1f-318">*Figure 12 - Direct (peer-to-peer)*</span></span>

### <a name="teams-hybrid-topology"></a><span data-ttu-id="95f1f-319">Teams ハイブリッド トポロジ</span><span class="sxs-lookup"><span data-stu-id="95f1f-319">Teams hybrid topology</span></span>

<span data-ttu-id="95f1f-320">このトポロジには、Skype for Business のオンプレミス展開を使用する Teams が含まれます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-320">This topology includes Teams with a Skype for Business on-premises deployment.</span></span>

<span data-ttu-id="95f1f-321">[![Microsoft Teams オンライン通話フロー 図 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-321">[![Microsoft Teams Online Call Flows Figure 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span></span>

<span data-ttu-id="95f1f-322">*図 13 - Teams ハイブリッド トポロジ*</span><span class="sxs-lookup"><span data-stu-id="95f1f-322">*Figure 13 - Teams hybrid topology*</span></span>

- <span data-ttu-id="95f1f-323">上の図の矢印の方向は、エンタープライズ境界での接続に影響を与える、通信の開始方向を反映します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-323">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="95f1f-324">メディアの UDP については、最初のパケットは逆方向に流れる場合がありますが、これらのパケットは、別の方向へのパケットが流れるまでブロックされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="95f1f-324">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="95f1f-325">Teams は、Skype for Business Online と並行して展開されます。そのため、クライアントは "Teams/SFB ユーザー" として表示されています。</span><span class="sxs-lookup"><span data-stu-id="95f1f-325">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user."</span></span>

<span data-ttu-id="95f1f-326">その他のフロー (Teams のトポロジへの追加)</span><span class="sxs-lookup"><span data-stu-id="95f1f-326">Additional flow (on top of Teams topology):</span></span>

- <span data-ttu-id="95f1f-327">**フロー 5 A** – 顧客ネットワーク内の Teams ユーザーと、顧客ネットワークのエッジにある Skype for Business オンプレミス メディア リレーとの間の、ピアツーピアのメディア フローを表します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-327">**Flow 5A** – Represents a peer-to-peer media flow between a Teams user within the customer network and a Skype for Business on-premises media relay at the customer network edge.</span></span>

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a><span data-ttu-id="95f1f-328">ユース ケース: Teams から Skype for Business へ、一対一</span><span class="sxs-lookup"><span data-stu-id="95f1f-328">Use case: Teams to Skype for Business one-to-one</span></span>

<span data-ttu-id="95f1f-329">**顧客ネットワーク内のハイブリッド**</span><span class="sxs-lookup"><span data-stu-id="95f1f-329">**Hybrid within the customer network**</span></span>

<span data-ttu-id="95f1f-330">[![Microsoft Teams オンライン通話フロー 図 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-330">[![Microsoft Teams Online Call Flows Figure 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span></span>

<span data-ttu-id="95f1f-331">*図 14 - 顧客ネットワーク内のハイブリッド*</span><span class="sxs-lookup"><span data-stu-id="95f1f-331">*Figure 14 - Hybrid within customer network*</span></span>

<span data-ttu-id="95f1f-332">Teams と Skype for Business の間のシグナリングは、ゲートウェイによりブリッジされます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-332">Signaling between Teams and Skype for Business is bridged by a gateway.</span></span> <span data-ttu-id="95f1f-333">ただし、メディアは顧客ネットワーク内で、フロー 5 経由でピアツーピアに直接ルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-333">However, media is routed directly peer-to-peer within the customer network using flow 5.</span></span>

<span data-ttu-id="95f1f-334">**ハイブリッドの顧客ネットワークから外部の Skype for Business ユーザーへ (Microsoft 365 または Office 365 により中継)**</span><span class="sxs-lookup"><span data-stu-id="95f1f-334">**Hybrid customer network with external Skype for Business user – relayed by Microsoft 365 or Office 365**</span></span>

<span data-ttu-id="95f1f-335">[![Microsoft Teams オンライン通話フロー 図 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-335">[![Microsoft Teams Online Call Flows Figure 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span></span>

<span data-ttu-id="95f1f-336">*図 15 - ハイブリッドの顧客ネットワークから外部の Skype for Business ユーザーへ (Office 365 により中継)*</span><span class="sxs-lookup"><span data-stu-id="95f1f-336">*Figure 15 - Hybrid customer network with external Skype for Business user - relayed by Office 365*</span></span>

<span data-ttu-id="95f1f-337">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="95f1f-337">Note that:</span></span>

- <span data-ttu-id="95f1f-338">Skype for Business クライアントからオンプレミスの Skype for Business サーバーへのシグナリングとメディアについては、この記事では説明しませんが、</span><span class="sxs-lookup"><span data-stu-id="95f1f-338">Signaling and media from the Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="95f1f-339">説明をわかりやすくするためにこれを図に示します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-339">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="95f1f-340">Teams と Skype for Business の間のシグナリングは、ゲートウェイによりブリッジされます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-340">Signaling between Teams and Skype for Business is bridged by a gateway.</span></span>

- <span data-ttu-id="95f1f-341">メディアは、 Teams トランスポート リレーを通して、フロー 4 経由で顧客ネットワークに中継されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-341">Media is relayed through Teams Transport Relay to the customer network through flow 4.</span></span>

<span data-ttu-id="95f1f-342">**ハイブリッドの顧客ネットワークから外部の Skype for Business ユーザーへ (オンプレミス エッジ により中継)**</span><span class="sxs-lookup"><span data-stu-id="95f1f-342">**Hybrid customer network with external Skype for Business user – relayed by on-premises Edge**</span></span>

<span data-ttu-id="95f1f-343">[![Microsoft Teams オンライン通話フロー 図 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-343">[![Microsoft Teams Online Call Flows Figure 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span></span>

<span data-ttu-id="95f1f-344">*図 16 - ハイブリッドの顧客ネットワークから外部の Skype for Business ユーザーへ (オンプレミス エッジ により中継)*</span><span class="sxs-lookup"><span data-stu-id="95f1f-344">*Figure 16 - Hybrid customer network with external Skype for Business user - relayed by on-premises Edge*</span></span>

<span data-ttu-id="95f1f-345">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="95f1f-345">Note that:</span></span>

- <span data-ttu-id="95f1f-346">Skype for Business クライアントからオンプレミスの Skype for Business サーバーへのシグナリングとメディアについては、この記事では説明しませんが、</span><span class="sxs-lookup"><span data-stu-id="95f1f-346">Signaling and media from Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="95f1f-347">説明をわかりやすくするためにこれを図に示します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-347">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="95f1f-348">シグナリングは、ゲートウェイによってブリッジされます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-348">Signaling is bridged by a gateway.</span></span>

- <span data-ttu-id="95f1f-349">メディアは、Skype for Business オンプレミス エッジ内の Skype for Business メディア リレーにより、フロー 5A 経由で顧客ネットワーク内の Teams ユーザーに中継されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-349">Media is relayed by Skype for Business Media Relay within Skype for Business on-premises Edge to Teams user within the customer network using media flow 5A.</span></span>

### <a name="teams-with-phone-system-direct-routing-topology"></a><span data-ttu-id="95f1f-350">電話システムのダイレクト ルーティングを使用する Teams のトポロジ</span><span class="sxs-lookup"><span data-stu-id="95f1f-350">Teams with Phone System Direct Routing topology</span></span>

<span data-ttu-id="95f1f-351">このトポロジには、電話システムのダイレクト ルーティングを使用する Teams が含まれます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-351">This topology includes Teams with Phone System Direct Routing.</span></span>

<span data-ttu-id="95f1f-352">ダイレクト ルーティングを使用すると、サポートされているオンプレミスの、顧客が所有するセッション ボーダー コントローラー (SBC) 機器デバイスを Microsoft 365 または Office 365 にペアリングし、次にテレフォニー トランクをそのデバイスに接続することにより、サードパーティ製公衆交換電話網 (PSTN) の サービス プロバイダーを利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="95f1f-352">Direct Routing enables you to use a third-party Public Switched Telephone Network (PSTN) service provider by pairing a supported on-premises customer-owned Session Border Controller (SBC) hardware device to Microsoft 365 or Office 365, and then connecting the telephony trunk to that device.</span></span>

<span data-ttu-id="95f1f-353">このシナリオをサポートするには、顧客は、Microsoft の認定パートナーのいずれかによりダイレクト ルーティング用に認定された SBC を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95f1f-353">To support this scenario, the customer must deploy a certified SBC for Direct Routing from one of Microsoft's certified partners.</span></span> <span data-ttu-id="95f1f-354">SBC は製造元の推奨通りに構成する必要があり、Microsoft 365 または Office 365 からのダイレクト UDP トラフィックがルーティング可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="95f1f-354">The SBC must be configured as recommended by the vendor, and be routable from Microsoft 365 or Office 365 for direct UDP traffic.</span></span> <span data-ttu-id="95f1f-355">メディアは、Teams および/または Skype for Business クライアントから SBC に直接流れることも (Teams ゲートウェイをバイパスして)、Teams ゲートウェイを通過することもできます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-355">The media may flow directly from Teams and/or the Skype for Business client to the SBC (bypassing the Teams gateway) or traverse through the Teams gateway.</span></span> <span data-ttu-id="95f1f-356">トランクが Teams ゲートウェイをバイパスするように構成されている場合は、SBC との接続は ICE に基づきます。SBC では ICE-Lite がサポートされ、Teams/Skype for Business のメディア エンドポイントでは ICE フル フォームがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-356">The connectivity with the SBC, when the trunk is configured to bypass the Teams gateway, is based on ICE, where SBC supports ICE-Lite, while the Teams/Skype for Business media endpoint supports ICE Full Form.</span></span>

<span data-ttu-id="95f1f-357">[![Microsoft Teams オンライン通話フロー 図 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-357">[![Microsoft Teams Online Call Flows Figure 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span></span>

<span data-ttu-id="95f1f-358">\*図 17 - 電話システムのダイレクト ルーティングを使用する Teams のトポロジ</span><span class="sxs-lookup"><span data-stu-id="95f1f-358">\*Figure 17 - Teams with Phone System Direct Routing topology</span></span>

<span data-ttu-id="95f1f-359">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="95f1f-359">Note that:</span></span>

- <span data-ttu-id="95f1f-360">上の図の矢印の方向は、エンタープライズ境界での接続に影響を与える、通信の開始方向を反映します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-360">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="95f1f-361">メディアの UDP については、最初のパケットは逆方向に流れる場合がありますが、これらのパケットは、別の方向へのパケットが流れるまでブロックされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="95f1f-361">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="95f1f-362">Teams は、Skype for Business Online と並行して展開されます。そのため、クライアントは "Teams/SFB ユーザー" として表示されています。</span><span class="sxs-lookup"><span data-stu-id="95f1f-362">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user."</span></span>

<span data-ttu-id="95f1f-363">その他のフロー (Teams のトポロジへの追加):</span><span class="sxs-lookup"><span data-stu-id="95f1f-363">Additional flows (on top of Teams online topology):</span></span>

- <span data-ttu-id="95f1f-364">**フロー 4'** - クラウド内の Teams メディア サーバーとオンプレミスの SBC との間の接続を確立するために使用される、Microsoft 365 または Office 365 から顧客ネットワークへのフローを表します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-364">**Flow 4'** - Represents a flow from Microsoft 365 or Office 365 to the customer network, used to establish a connection between the Teams media server in the cloud with the SBC on premises.</span></span>
- <span data-ttu-id="95f1f-365">**フロー 5B** - バイパス モードでの、顧客ネットワーク内の Teams ユーザーとバイパス モードのダイレクト ルーティング SBC のメディア フローを表します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-365">**Flow 5B** – Represents a media flow between the Teams user within the customer network with the Direct Routing SBC in bypass mode.</span></span>
- <span data-ttu-id="95f1f-366">**フロー 5C** – PSTN ヘアピン コール バイパス モードでの、ダイレクト ルーティング SBC と別のダイレクト ルーティング SBC と間のメディア フローを表します。 </span><span class="sxs-lookup"><span data-stu-id="95f1f-366">**Flow 5C** – Represents a media flow between the Direct Routing SBC to another Direct Routing SBC in a PSTN hairpin call bypass mode.</span></span>

<span data-ttu-id="95f1f-367">**ダイレクト ルーティングによる内部ユーザー (メディアはTeams トランスポート リレーが中継)**</span><span class="sxs-lookup"><span data-stu-id="95f1f-367">**Internal user with Direct Routing (media relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="95f1f-368">[![Microsoft Teams オンライン通話フロー 図 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-368">[![Microsoft Teams Online Call Flows Figure 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span></span>

<span data-ttu-id="95f1f-369">*図 18 - ダイレクト ルーティングによる内部ユーザー (メディアは Teams トランスポート リレーが中継)*</span><span class="sxs-lookup"><span data-stu-id="95f1f-369">*Figure 18 - Internal user with Direct Routing (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="95f1f-370">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="95f1f-370">Note that:</span></span>

- <span data-ttu-id="95f1f-371">SBC には、Microsoft 365 または Office 365 からルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="95f1f-371">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="95f1f-372">SBC から Microsoft 365 または Office 365 へのシグナリングおよびメディアは、フロー4 および/またはフロー 4' を使用します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-372">Signaling and media from the SBC to Microsoft 365 or Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="95f1f-373">顧客ネットワーク内のクライアントから Microsoft 365 または Office 365 へのシグナリングおよびメディアは、フロー 4 を使用します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-373">Signaling and media from the client within the customer network to Microsoft 365 or Office 365 use flow 4.</span></span>

<span data-ttu-id="95f1f-374">**ダイレクト ルーティングを使用するリモート ユーザー (メディアは メディア サーバー (MP) 経由でルーティング)**</span><span class="sxs-lookup"><span data-stu-id="95f1f-374">**Remote user with Direct Routing (media is routed through a media server (MP))**</span></span>

<span data-ttu-id="95f1f-375">[![Microsoft Teams オンライン通話フロー 図 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-375">[![Microsoft Teams Online Call Flows Figure 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span></span>

<span data-ttu-id="95f1f-376">*図 19 - ダイレクト ルーティングを使用するリモート ユーザー (メディアはメディア サーバー (MP) 経由でルーティング)*</span><span class="sxs-lookup"><span data-stu-id="95f1f-376">*Figure 19 - Remote user with Direct Routing (media is routed through a media server (MP))*</span></span>

<span data-ttu-id="95f1f-377">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="95f1f-377">Note that:</span></span>

- <span data-ttu-id="95f1f-378">SBC には、Microsoft 365 または Office 365 からルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="95f1f-378">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="95f1f-379">SBC から Microsoft 365 または Office 365 へのシグナリングおよびメディアは、フロー4 および/またはフロー 4' を使用します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-379">Signaling and media from the SBC to Microsoft 365 or Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="95f1f-380">インターネット上のクライアントから Microsoft 365 または Office 365 へのシグナリングおよびメディアは、フロー 3 を使用します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-380">Signaling and media from the client on the Internet to Microsoft 365 or Office 365 use flow 3.</span></span>

<span data-ttu-id="95f1f-381">**内部ユーザーのダイレクト ルーティング (メディアはバイパス)**</span><span class="sxs-lookup"><span data-stu-id="95f1f-381">**Internal user Direct Routing (media bypass)**</span></span>

<span data-ttu-id="95f1f-382">[![Microsoft Teams オンライン通話フロー 図 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-382">[![Microsoft Teams Online Call Flows Figure 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span></span>

<span data-ttu-id="95f1f-383">*図 20 - 内部ユーザーのダイレクト ルーティング (メディアはバイパス)*</span><span class="sxs-lookup"><span data-stu-id="95f1f-383">*Figure 20 - Internal user Direct Routing (media bypass)*</span></span>

<span data-ttu-id="95f1f-384">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="95f1f-384">Note that:</span></span>

- <span data-ttu-id="95f1f-385">SBC には、Microsoft 365 または Office 365 からルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="95f1f-385">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="95f1f-386">SBC から Microsoft 365 または Office 365 へのシグナリングおよびその逆のシグナリングは、フロー4 および/またはフロー 4' を使用します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-386">Signaling from SBC to Microsoft 365 or Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="95f1f-387">顧客ネットワーク内のクライアントから Microsoft 365 または Office 365 へのシグナリングは、フロー 4 を使用します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-387">Signaling from client within the customer network to Microsoft 365 or Office 365 use flow 4.</span></span>

- <span data-ttu-id="95f1f-388">顧客ネットワーク内のクライアントから顧客ネットワーク内の SBC へのメディアは、フロー 5B を使用します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-388">Media from client within the customer network to SBC within the customer network use flow 5B.</span></span>

<span data-ttu-id="95f1f-389">**ダイレクト ルーティングによるリモート ユーザー (メディアのパイパスは Teams トランスポート リレーが中継)**</span><span class="sxs-lookup"><span data-stu-id="95f1f-389">**Remote user with Direct Routing (media bypass relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="95f1f-390">[![Microsoft Teams オンライン通話フロー 図 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-390">[![Microsoft Teams Online Call Flows Figure 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span></span>

<span data-ttu-id="95f1f-391">*図 21 - ダイレクト ルーティングによるリモート ユーザー (メディアのパイパスは Teams トランスポート リレーが中継)*</span><span class="sxs-lookup"><span data-stu-id="95f1f-391">*Figure 21 - Remote user with Direct Routing (media bypass relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="95f1f-392">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="95f1f-392">Note that:</span></span>

- <span data-ttu-id="95f1f-393">SBC には、Microsoft 365 または Office 365 およびインターネットからルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="95f1f-393">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365 and Internet.</span></span>

- <span data-ttu-id="95f1f-394">SBC から Microsoft 365 または Office 365 へのシグナリングおよびその逆のシグナリングは、フロー4 および/またはフロー 4' を使用します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-394">Signaling from the SBC to Microsoft 365 or Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="95f1f-395">インターネット上のクライアントから Microsoft 365 または Office 365 へのシグナリングは、フロー 3 を使用します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-395">Signaling from the client on the Internet to Microsoft 365 or Office 365 uses flow 3.</span></span>

- <span data-ttu-id="95f1f-396">インターネット上のクライアントから顧客ネットワーク内の SBC へのメディアでは フロー 3 および 4 が使用されTeams トランスポート リレーにより中継されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-396">Media from the client on the Internet to the SBC within the customer network uses flows 3 and 4, relayed by Teams Transport Relay.</span></span>

<span data-ttu-id="95f1f-397">**ダイレクト ルーティングによるリモート ユーザー (メディアのバイパスはダイレクト)**</span><span class="sxs-lookup"><span data-stu-id="95f1f-397">**Remote user Direct Routing (media bypass direct)**</span></span>

<span data-ttu-id="95f1f-398">[![Microsoft Teams オンライン通話フロー 図 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-398">[![Microsoft Teams Online Call Flows Figure 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span></span>

<span data-ttu-id="95f1f-399">*図 22 - リモート ユーザーのダイレクト ルーティング (メディアのバイパスはダイレクト)*</span><span class="sxs-lookup"><span data-stu-id="95f1f-399">*Figure 22 - Remote user Direct Routing (media bypass direct)*</span></span>

<span data-ttu-id="95f1f-400">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="95f1f-400">Note that:</span></span>

- <span data-ttu-id="95f1f-401">SBC には、Microsoft 365 または Office 365 およびインターネットからルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="95f1f-401">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365 and the Internet.</span></span>

- <span data-ttu-id="95f1f-402">SBC から Microsoft 365 または Office 365 へのシグナリングおよびその逆のシグナリングは、フロー4 および/またはフロー 4' を使用します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-402">Signaling from the SBC to Microsoft 365 or Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="95f1f-403">インターネット上のクライアントから Microsoft 365 または Office 365 へのシグナリングは、フロー 3 を使用します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-403">Signaling from the client on the Internet to Microsoft 365 or Office 365 uses flow 3.</span></span>

- <span data-ttu-id="95f1f-404">インターネット上のクライアントから顧客ネットワーク内の SBC へのメディアは、 フロー 2 を使用します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-404">Media from the client on the Internet to the SBC within the customer network uses flow 2.</span></span>

<span data-ttu-id="95f1f-405">**ダイレクト ルーティング (メディア バイパス) – PSTN ヘアピン コール (通話の転送を原因とする)**</span><span class="sxs-lookup"><span data-stu-id="95f1f-405">**Direct Routing (media bypass) – PSTN hairpin call (due to call forward/transfer)**</span></span>

<span data-ttu-id="95f1f-406">[![Microsoft Teams オンライン通話フロー 図 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-406">[![Microsoft Teams Online Call Flows Figure 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span></span>

<span data-ttu-id="95f1f-407">*図 23 - ダイレクト ルーティング (メディア バイパス) – PSTN ヘアピン コール (通話の転送を原因とする)*</span><span class="sxs-lookup"><span data-stu-id="95f1f-407">*Figure 23 - Direct Routing (media bypass) - PSTN hairpin call (due to call forward/transfer)*</span></span>

<span data-ttu-id="95f1f-408">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="95f1f-408">Note that:</span></span>

- <span data-ttu-id="95f1f-409">SBC には、Microsoft 365 または Office 365 からルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="95f1f-409">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="95f1f-410">SBC から Microsoft 365 または Office 365 へのシグナリングおよびその逆のシグナリングは、フロー4 および/またはフロー 4' を使用します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-410">Signaling from the SBC to Microsoft 365 or Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="95f1f-411">PSTN から PSTN への通話のヘアピンが発生すると、クライアントはシグナリングおよびメディア ループに含まれなくなります。</span><span class="sxs-lookup"><span data-stu-id="95f1f-411">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="95f1f-412">顧客ネットワーク内の SBC インスタンス A から顧客ネットワーク内の SBC インスタンス B までのメディア (A と B は同じインスタンスの可能性もあります) は、フロー 5C を使用します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-412">Media from SBC instance A within the customer network to SBC instance B within the customer network (where, A and B can be the same instance) uses flow 5C.</span></span>

<span data-ttu-id="95f1f-413">**ダイレクト ルーティング (メディアは Microsoft 365 または Office 365 を経由) – 2 つのテナントの間での PSTN ヘアピン コール**</span><span class="sxs-lookup"><span data-stu-id="95f1f-413">**Direct Routing (media through Microsoft 365 or Office 365) – PSTN hairpin call across two tenants**</span></span>

<span data-ttu-id="95f1f-414">[![Microsoft Teams オンライン通話フロー 図 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-414">[![Microsoft Teams Online Call Flows Figure 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span></span>

<span data-ttu-id="95f1f-415">*図 24 - ダイレクト ルーティング (メディアは Microsoft 365 または Office 365 を経由) – 2 つのテナントの間での PSTN ヘアピン コール*</span><span class="sxs-lookup"><span data-stu-id="95f1f-415">*Figure 24 - Direct Routing (media through Microsoft 365 or Office 365) – PSTN hairpin call across two tenants*</span></span>

<span data-ttu-id="95f1f-416">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="95f1f-416">Note that:</span></span>

- <span data-ttu-id="95f1f-417">SBC には、Microsoft 365 または Office 365 からルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="95f1f-417">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="95f1f-418">SBC から Microsoft 365 または Office 365 へのシグナリングおよびその逆のシグナリングは、フロー4 および/またはフロー 4' を使用します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-418">Signaling from the SBC to Microsoft 365 or Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="95f1f-419">PSTN から PSTN への通話のヘアピンが発生すると、クライアントはシグナリングおよびメディア ループに含まれなくなります。</span><span class="sxs-lookup"><span data-stu-id="95f1f-419">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="95f1f-420">顧客ネットワーク X 内の SBC インスタンス A から SBC インスタンス B へのメディアは、Microsoft 365 またはOffice 365 のメディア サーバー経由で中継される必要があり、バイパス モードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="95f1f-420">Media from SBC instance A within the customer network X to SBC instance B must be relayed through the Microsoft 365 or Office 365 Media Server and can't use bypass mode.</span></span>

## <a name="teams-with-express-route-optimization"></a><span data-ttu-id="95f1f-421">Express Route による Teams の最適化</span><span class="sxs-lookup"><span data-stu-id="95f1f-421">Teams with Express Route optimization</span></span>

<span data-ttu-id="95f1f-422">[![Microsoft Teams オンライン通話フロー 図 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-422">[![Microsoft Teams Online Call Flows Figure 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span></span>

<span data-ttu-id="95f1f-423">*図 25 - Express Route による Teams の最適化*</span><span class="sxs-lookup"><span data-stu-id="95f1f-423">*Figure 25 - Teams with Express Route optimization*</span></span>

<span data-ttu-id="95f1f-424">Express Route が正当化されて展開されているケースでは、Teams のフローはフロー 4 からフロー 1 に、またフロー 4' からフロー 1' に再ルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-424">In the case that Express Route is justified and deployed, then Teams flows could be re-routed from flow 4 to flow 1 and from flow 4' to flow 1'.</span></span> <span data-ttu-id="95f1f-425">ただし、Teams アプリケーションは、フロー 4 および 4' 経由のインターネット上の Microsoft 365 または Office 365 のフローに強く依存するため、これらのフローはブロックされないことが必要があります。</span><span class="sxs-lookup"><span data-stu-id="95f1f-425">However, the Teams application has a hard dependency on other Microsoft 365 or Office 365 flows over the Internet using flows 4 and 4'; hence these flows must not be blocked.</span></span>

<span data-ttu-id="95f1f-426">Skype for Business のハイブリッド エッジ トラフィックは、外部ユーザーとの通信および他のテナントとのフェデレーションを行うために、Express Route ではなくインターネットにルーティングされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="95f1f-426">Note that Skype for Business hybrid Edge traffic is routed to the Internet and not to Express Route to communicate with external users and federate with other tenants.</span></span>

<span data-ttu-id="95f1f-427">非対称のフローを防ぐには、再ルーティングは双方向に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="95f1f-427">To prevent asymmetrical flows, re-routing must be in both directions.</span></span> <span data-ttu-id="95f1f-428">つまり、顧客ネットワーク内のアドレスは、(最適化のために) インターネットまたは Express Route のいずれを経由してもルーティング可能ですが、両方を経由することはできません。</span><span class="sxs-lookup"><span data-stu-id="95f1f-428">In other words, an address within the customer network is routable either through Internet or Express Route, based on optimization, but not through both.</span></span>


<span data-ttu-id="95f1f-429">**顧客ネットワークから外部ユーザーへ (メディアは Teams トランスポート リレーが中継):**</span><span class="sxs-lookup"><span data-stu-id="95f1f-429">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="95f1f-430">[![Microsoft Teams オンライン通話フロー 図 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span><span class="sxs-lookup"><span data-stu-id="95f1f-430">[![Microsoft Teams Online Call Flows Figure 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span></span>

<span data-ttu-id="95f1f-431">*図 26 - 顧客ネットワークから外部ユーザーへ (メディアは Teams トランスポート リレーが中継)*</span><span class="sxs-lookup"><span data-stu-id="95f1f-431">*Figure 26 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="95f1f-432">**大まかな手順:**</span><span class="sxs-lookup"><span data-stu-id="95f1f-432">**High Level Steps:**</span></span>

1. <span data-ttu-id="95f1f-433">顧客ネットワーク内の Teams ユーザーが、フロー 2 経由で URL ドメイン名 (DNS) を解決します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-433">Teams User within customer network resolves URL domain name (DNS) using flow2.</span></span>
1. <span data-ttu-id="95f1f-434">顧客ネットワーク内の Teams ユーザーが、フロー 1 経由で Teams トランスポート リレーでメディア リレー ポートを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-434">Teams User within customer network allocates a media Relay port on Teams Transport Relay using flow 1.</span></span>
1. <span data-ttu-id="95f1f-435">顧客ネットワーク内の Teams ユーザーが、フロー 1 経由で 「招待状」 を ICE 候補と共に Microsoft 365 または Office 365 に送信します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-435">Teams User within customer network sends "invite" with ICE candidates using flow 1 to Microsoft 365 or Office 365.</span></span>
1. <span data-ttu-id="95f1f-436">Microsoft 365 または Office 365 は、フロー3 を使用して外部の Teams ユーザーに通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-436">Microsoft 365 or Office 365 sends notification to external Teams user using flow 3.</span></span>
1. <span data-ttu-id="95f1f-437">Teams の外部ユーザーが、フロー 3 経由で Teams トランスポート リレーでメディア リレー ポートを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-437">Teams external user allocates a media Relay port on Teams Transport Relay using flow 3.</span></span>
1. <span data-ttu-id="95f1f-438">Teams の外部ユーザーが、フロー 3 経由で「回答」 を ICE 候補と共に送信し、これはフロー 1 経由で Teams ユーザー A に再び転送されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-438">Teams external user sends "answer" with ICE candidates using flow 3, which is forwarded back to Teams user A using Flow 1.</span></span>
1. <span data-ttu-id="95f1f-439">Teams ユーザー A および Teams ユーザー B が ICE 接続テストを実行してフロー 1 および フロー 3 を選択し、これらは Teams トランスポート リレーにより中継されます。</span><span class="sxs-lookup"><span data-stu-id="95f1f-439">Teams User A and Teams User B invoke ICE connectivity tests and selects flows 1 and 3, which are relayed by Teams Transport Relay.</span></span>
1. <span data-ttu-id="95f1f-440">Teams ユーザーは、フロー 1 とフロー 3 を使用して、Microsoft 365 または Office 365 にテレメトリを送信します。</span><span class="sxs-lookup"><span data-stu-id="95f1f-440">Teams Users send telemetry to Microsoft 365 or Office 365 using flows 1 and 3.</span></span>

> [!NOTE]
> <span data-ttu-id="95f1f-441">フロー 4 を要求する他のマイクロ サービスへの Teams の依存をサポートするために、フロー 4 を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="95f1f-441">Flow 4 must be enabled to support dependencies of Teams application on other micro-services that mandates flow 4.</span></span>