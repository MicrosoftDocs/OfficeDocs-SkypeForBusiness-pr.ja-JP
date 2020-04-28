---
title: Microsoft Teams 通話のフロー
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
description: チームがさまざまなトポロジで Office 365 フローを使用する方法、およびピアツーピアメディア通信に使用される固有のチームフローについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dd0a5155766ee86bdf03219cdfcbb50cc220177d
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904989"
---
# <a name="microsoft-teams-call-flows"></a><span data-ttu-id="0d0c4-103">Microsoft Teams 通話のフロー</span><span class="sxs-lookup"><span data-stu-id="0d0c4-103">Microsoft Teams call flows</span></span>

> [!TIP]
> <span data-ttu-id="0d0c4-104">このセッションでは、チームがネットワークを活用する方法と、最適なネットワーク接続を計画する方法について説明します。 [Teams ネットワーク計画](https://aka.ms/teams-networking)。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-104">Watch this session to learn how Teams leverages your network and how to plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking).</span></span>

## <a name="overview"></a><span data-ttu-id="0d0c4-105">概要</span><span class="sxs-lookup"><span data-stu-id="0d0c4-105">Overview</span></span>

<span data-ttu-id="0d0c4-106">この記事では、さまざまなトポロジで Teams が Office 365 のコールフローを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-106">This article describes how Teams uses Office 365 call flows in various topologies.</span></span> <span data-ttu-id="0d0c4-107">また、ピアツーピアメディア通信に使用される固有のチームフローについても説明します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-107">In addition, it describes unique Teams flows that are used for peer-to-peer media communication.</span></span> <span data-ttu-id="0d0c4-108">このドキュメントでは、ネットワーク上でこれらのフロー、目的、およびその発生元と終了が説明されています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-108">The document describes these flows, their purpose, and their origin and termination on the network.</span></span> <span data-ttu-id="0d0c4-109">この記事の目的に応じて、次のことを前提とします。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-109">For purposes of this article, assume the following:</span></span>

- <span data-ttu-id="0d0c4-110">Flow X は、オンプレミスの Office 365 クライアントによって、クラウドの Office 365 サービスと通信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-110">Flow X is used by the on-premises Office 365 client to communicate with the Office 365 service in the cloud.</span></span> <span data-ttu-id="0d0c4-111">これは、顧客ネットワークから発信され、Office 365 のエンドポイントとして終了します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-111">It originates from the customer network, and it terminates as an endpoint in Office 365.</span></span>

- <span data-ttu-id="0d0c4-112">Flow Y は、オンプレミスの Office 365 クライアントによって、Office 365 が依存しているインターネット上のサービスと通信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-112">Flow Y is used by the on-premises Office 365 client to communicate with a service on the Internet that Office 365 has a dependency on.</span></span> <span data-ttu-id="0d0c4-113">これは、顧客ネットワークから発信され、インターネット上のエンドポイントとして終了します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-113">It originates from the customer network, and it terminates as an endpoint on the Internet.</span></span>

<span data-ttu-id="0d0c4-114">この記事では、次の情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-114">This article covers the following information:</span></span>

- <span data-ttu-id="0d0c4-115">**背景**。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-115">**Background**.</span></span> <span data-ttu-id="0d0c4-116">Office 365 フローのスキャン、トラフィックの種類、顧客ネットワークから Office 365 サービスエンドポイントへの相互運用性、サードパーティ製コンポーネントとの相互運用性、およびチームがメディアフローを選択するために使用する原則などの背景情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-116">Provides background information such as networks that Office 365 flows may traverse, types of traffic, connectivity guidance from the customer network to Office 365 service endpoints, interoperability with third-party components, and principles that are used by Teams to select media flows.</span></span>

- <span data-ttu-id="0d0c4-117">**さまざまなトポロジでのコールフロー**。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-117">**Call flows in various topologies**.</span></span> <span data-ttu-id="0d0c4-118">さまざまなトポロジでのコールフローの使い方を示します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-118">Illustrates the use of call flows in various topologies.</span></span> <span data-ttu-id="0d0c4-119">各トポロジについて、サポートされているすべてのフローを列挙し、これらのフローがさまざまなユースケースでどのように使用されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-119">For each topology, the section enumerates all supported flows and illustrates how these flows are used in several use cases.</span></span> <span data-ttu-id="0d0c4-120">各ユースケースについて、フロー図を使ってフローの順序および選択を記述します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-120">For each use case, it describes the sequence and selection of flows using a flow diagram.</span></span>

- <span data-ttu-id="0d0c4-121">**エクスプレスルートの最適化を行っているチーム**。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-121">**Teams with Express Route optimization**.</span></span> <span data-ttu-id="0d0c4-122">簡易ルートを使用して最適化を展開するときに、これらのフローがどのように使用されるかを説明します。シンプルなトポロジで示されています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-122">Describes how these flows are used when Express Route is deployed for optimization, illustrated using a simple topology.</span></span>

## <a name="background"></a><span data-ttu-id="0d0c4-123">背景</span><span class="sxs-lookup"><span data-stu-id="0d0c4-123">Background</span></span>

### <a name="network-segments"></a><span data-ttu-id="0d0c4-124">ネットワークセグメント</span><span class="sxs-lookup"><span data-stu-id="0d0c4-124">Network segments</span></span>

<span data-ttu-id="0d0c4-125">**顧客ネットワーク**。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-125">**Customer network**.</span></span> <span data-ttu-id="0d0c4-126">これは、管理および管理するネットワークセグメントです。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-126">This is the network segment that you control and manage.</span></span> <span data-ttu-id="0d0c4-127">これには、お客さまのお客さまのお客様への接続 (有線またはワイヤレス、オフィスビル間の接続、オンプレミスのデータセンターへの接続、インターネットプロバイダへの接続、その他のプライベートピアリングなど) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-127">This includes all customer connections within customer offices, whether wired or wireless, connections between office buildings, connections to on-premises datacenters, and your connections to Internet providers, Express Route, or any other private peering.</span></span>

<span data-ttu-id="0d0c4-128">通常、顧客ネットワークには、ファイアウォールやプロキシサーバーを備えたネットワーク境界がいくつかあります。これにより、組織のセキュリティポリシーが適用されます。また、設定して構成した特定のネットワークトラフィックのみを許可します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-128">Typically, a customer network has several network perimeters with firewalls and/or proxy servers, which enforce your organization's security policies, and that only allow certain network traffic that you have set up and configured.</span></span> <span data-ttu-id="0d0c4-129">このネットワークを管理するため、ネットワークのパフォーマンスを直接制御できます。また、ネットワーク上のサイトと365ネットワークの両方でパフォーマンスを検証するために、ネットワークの評価を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-129">Because you manage this network, you have direct control over the performance of the network, and we recommend that you complete network assessments to validate performance both within sites in your network and from your network to the Office 365 network.</span></span>

<span data-ttu-id="0d0c4-130">**インターネット**。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-130">**Internet**.</span></span> <span data-ttu-id="0d0c4-131">これは、顧客ネットワークの外部から Office 365 に接続しているユーザーが使用する、全体的なネットワークの一部であるネットワークセグメントです。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-131">This is the network segment that is part of your overall network that will be used by users who are connecting to Office 365 from outside of the customer network.</span></span> <span data-ttu-id="0d0c4-132">また、顧客ネットワークから Office 365 への一部のトラフィックでも使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-132">It is also used by some traffic from the customer network to Office 365.</span></span>

<span data-ttu-id="0d0c4-133">**アクセスした、またはゲストプライベートネットワーク**。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-133">**Visited or guest private network**.</span></span> <span data-ttu-id="0d0c4-134">これは、顧客ネットワークの外部のネットワークセグメントであり、公共のインターネットでは使用できません。ユーザーとそのゲストは (たとえば、ホームプライベートネットワークや、チームを展開しない企業のプライベートネットワークなどであり、チームのサービスとやり取りするユーザーとそのユーザーが存在する可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-134">This is the network segment outside your customer network, but not in the public Internet, that your users and their guests may visit (for example, a home private network or an enterprise private network, that does not deploy Teams, where your users and their customers that interact with Teams services may reside).</span></span>

> [!NOTE]
> <span data-ttu-id="0d0c4-135">Office 365 への接続は、これらのネットワークにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-135">Connectivity to Office 365 is also applicable to these networks.</span></span>

<span data-ttu-id="0d0c4-136">**Office 365**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-136">**Office 365**.</span></span> <span data-ttu-id="0d0c4-137">これは、Office 365 サービスをサポートするネットワークセグメントです。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-137">This is the network segment that supports Office 365 services.</span></span> <span data-ttu-id="0d0c4-138">これは、世界各地のお客様のネットワークに近接したエッジを使用して世界中に配布されています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-138">It is distributed worldwide with edges in proximity to the customer network in most locations.</span></span> <span data-ttu-id="0d0c4-139">機能には、トランスポートリレー、会議サーバー、メディアプロセッサが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-139">Functions include Transport Relay, conferencing server, and Media Processor.</span></span>

<span data-ttu-id="0d0c4-140">**簡易ルート (省略可能)**。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-140">**Express Route (optional)**.</span></span> <span data-ttu-id="0d0c4-141">これは、Office 365 ネットワークへの専用接続を提供する、全体的なネットワークの一部であるネットワークセグメントです。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-141">This is the network segment that is part of your overall network that will give you a dedicated, private connection to the Office 365 network.</span></span>

### <a name="types-of-traffic"></a><span data-ttu-id="0d0c4-142">トラフィックのタイプ</span><span class="sxs-lookup"><span data-stu-id="0d0c4-142">Types of traffic</span></span>

<span data-ttu-id="0d0c4-143">**リアルタイムメディア**。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-143">**Real-time media**.</span></span> <span data-ttu-id="0d0c4-144">オーディオ、ビデオ、画面共有のワークロードをサポートする、リアルタイムトランスポートプロトコル (RTP) 内にカプセル化されたデータ。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-144">Data encapsulated within Real-time Transport Protocol (RTP) that supports audio, video, and screen sharing workloads.</span></span> <span data-ttu-id="0d0c4-145">通常、メディアトラフィックは非常に待機時間が高いため、このトラフィックは可能な限り多くのパスを使用し、トランスポート層プロトコルとして UDP または TCP を使うことをお勧めします。これは、品質の観点から対話的なリアルタイムメディアを作成するのに最適なトランスポートです。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-145">In general, media traffic is highly latency sensitive, so you would want this traffic to take the most direct path possible, and to use UDP versus TCP as the transport layer protocol, which is the best transport for interactive real time media from a quality perspective.</span></span> <span data-ttu-id="0d0c4-146">(最後の手段として、メディアは TCP/IP を使用でき、HTTP プロトコルでもトンネリングできることに注意してください。品質への影響が悪いため、お勧めしません)。RTP フローは SRTP を使って保護され、ペイロードのみが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-146">(Note that as a last resort, media can use TCP/IP and also be tunneled within the HTTP protocol, but it is not recommended due to bad quality implications.) RTP flow is secured using SRTP, in which only the payload is encrypted.</span></span>

<span data-ttu-id="0d0c4-147">**シグナリング**。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-147">**Signaling**.</span></span> <span data-ttu-id="0d0c4-148">クライアントとサーバーの間の通信リンク、またはアクティビティ (通話の開始時など) を制御するために使用される他のクライアント。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-148">The communication link between the client and server, or other clients that are used to control activities (for example, when a call is initiated), and deliver instant messages.</span></span> <span data-ttu-id="0d0c4-149">ほとんどのシグナルトラフィックでは、HTTPS ベースの REST インターフェイスが使用されますが、シナリオによっては (たとえば、Office 365 とセッション境界コントローラー間の接続)、SIP プロトコルを使います。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-149">Most signaling traffic uses the HTTPS-based REST interfaces, though in some scenarios (for example, connection between Office 365 and a Session Border Controller) it uses SIP protocol.</span></span> <span data-ttu-id="0d0c4-150">このトラフィックは待ち時間に非常に敏感であることを理解しておく必要がありますが、エンドポイント間の待機時間が数秒を超えると、サービスが停止したり、タイムアウトしたりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-150">It's important to understand that this traffic is much less sensitive to latency but may cause service outages or call timeouts if latency between the endpoints exceeds several seconds.</span></span>

### <a name="connectivity-to-office-365"></a><span data-ttu-id="0d0c4-151">Office 365 への接続</span><span class="sxs-lookup"><span data-stu-id="0d0c4-151">Connectivity to Office 365</span></span>

<span data-ttu-id="0d0c4-152">チーム[にはインターネットへの接続](https://docs.microsoft.com/office365/enterprise/assessing-network-connectivity)が必要。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-152">Teams requires [connectivity to the Internet](https://docs.microsoft.com/office365/enterprise/assessing-network-connectivity).</span></span> <span data-ttu-id="0d0c4-153">Teams のエンドポイント Url と IP アドレス範囲は、 [Office 365 url と ip アドレス範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)に記載されています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-153">Teams endpoint URLs and IP address ranges are listed in [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> <span data-ttu-id="0d0c4-154">(TCP ポート80と443、および UDP ポート3478から3481への接続を開く必要があることに注意してください)。さらに、Teams は Skype for Business Online に依存しているため、インターネットにも接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-154">(Note that open connectivity to TCP ports 80 and 443, and to UDP ports 3478 through 3481, is required.) Furthermore, Teams has a dependency on Skype for Business Online, which must also be connected to the Internet.</span></span>

<span data-ttu-id="0d0c4-155">Teams メディアフロー接続は、標準の IETF 対話型接続確立 (ICE) 手順を使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-155">Teams media flows connectivity is implemented using standard IETF Interactive Connectivity Establishment (ICE) procedures.</span></span>

### <a name="interoperability-restrictions"></a><span data-ttu-id="0d0c4-156">相互運用性の制限</span><span class="sxs-lookup"><span data-stu-id="0d0c4-156">Interoperability restrictions</span></span>

<span data-ttu-id="0d0c4-157">**サードパーティメディアリレー**。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-157">**Third-party media relays**.</span></span> <span data-ttu-id="0d0c4-158">Teams メディアフロー (つまり、いずれかのメディアエンドポイントが Teams である場合) は、Teams または Skype for Business のネイティブメディアリレーのみをスキャンすることができます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-158">A Teams media flow (that is, where one of the media endpoints is Teams) may traverse only Teams or Skype for Business native media relays.</span></span> <span data-ttu-id="0d0c4-159">サードパーティのメディアリレーとの相互運用性はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-159">Interoperability with a third-party media relay is not supported.</span></span> <span data-ttu-id="0d0c4-160">(PSTN でのサードパーティの SBC は、RTP/RTCP ストリームを終了し、SRTP を使ってセキュリティで保護されているため、次のホップには中継しないことに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-160">(Note that a third-party SBC on the boundary with PSTN must terminate RTP/RTCP stream, secured using SRTP, and not relay it to the next hop.)</span></span>

<span data-ttu-id="0d0c4-161">**サードパーティ SIP プロキシサーバー**。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-161">**Third-party SIP proxy servers**.</span></span> <span data-ttu-id="0d0c4-162">サードパーティの SBC/ゲートウェイでシグナリングされたチームまたは Skype for Business のネイティブ SIP プロキシをスキャンするチーム。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-162">A Teams signaling SIP dialog with a third-party SBC and/or gateway may traverse Teams or Skype for Business native SIP proxies.</span></span> <span data-ttu-id="0d0c4-163">サードパーティの SIP プロキシとの相互運用性はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-163">Interoperability with a third-party SIP proxy is not supported.</span></span>

<span data-ttu-id="0d0c4-164">**サードパーティの B2BUA (または SBC)**。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-164">**Third-party B2BUA (or SBC)**.</span></span> <span data-ttu-id="0d0c4-165">PSTN との間の Teams メディアフローは、サードパーティの SBC によって終了します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-165">A Teams media flow to and from the PSTN is terminated by a third-party SBC.</span></span> <span data-ttu-id="0d0c4-166">ただし、Teams ネットワーク内のサードパーティの SBC との相互運用性 (サードパーティの SBC は2つのチームまたは Skype for Business のエンドポイントを使用している場合) はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-166">However, interoperability with a third-party SBC within the Teams network (where a third-party SBC mediates two Teams or Skype for Business endpoints) is not supported.</span></span>

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a><span data-ttu-id="0d0c4-167">Microsoft Teams で推奨されないテクノロジ</span><span class="sxs-lookup"><span data-stu-id="0d0c4-167">Technologies that are not recommended with Microsoft Teams</span></span>

<span data-ttu-id="0d0c4-168">**VPN ネットワーク**。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-168">**VPN network**.</span></span> <span data-ttu-id="0d0c4-169">メディアトラフィック (またはフロー 2) にはお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-169">It is not recommended for media traffic (or flow 2').</span></span> <span data-ttu-id="0d0c4-170">VPN クライアントでは、vpn[トンネルをバイパスするように Lync メディアを有効にする](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210)ことで指定されているように、境界 vpn を使って、外部の vpn 以外のすべてのユーザーと同様にメディアトラフィックをルーティングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-170">The VPN client should use split VPN and route media traffic like any external non-VPN user, as specified in [Enabling Lync media to bypass a VPN tunnel](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210).</span></span>

> [!NOTE]
> <span data-ttu-id="0d0c4-171">このタイトルは Lync を示していますが、チームにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-171">Although the title indicates Lync, it is applicable to Teams as well.</span></span>

<span data-ttu-id="0d0c4-172">**パケット図形**。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-172">**Packet shapers**.</span></span> <span data-ttu-id="0d0c4-173">どのような種類のパケット snippers、パケット検査、またはパケット shaper デバイスは推奨されないため、品質が大幅に低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-173">Any kind of packet snippers, packet inspection, or packet shaper devices are not recommended and may degrade quality significantly.</span></span>

### <a name="principles"></a><span data-ttu-id="0d0c4-174">指針</span><span class="sxs-lookup"><span data-stu-id="0d0c4-174">Principles</span></span>

<span data-ttu-id="0d0c4-175">Microsoft Teams のコールフローを理解するのに役立つ4つの一般的な原則があります。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-175">There are four general principles that help you understand call flows for Microsoft Teams:</span></span>

- <span data-ttu-id="0d0c4-176">Microsoft Teams の会議は、最初の参加者が参加したのと同じ地域で Office 365 によってホストされています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-176">A Microsoft Teams conference is hosted by Office 365 in the same region where the first participant joined.</span></span> <span data-ttu-id="0d0c4-177">(一部のトポロジではこの規則に例外がある場合は、このドキュメントで説明されていて、適切なコールフローで示されることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-177">(Note that if there are exceptions to this rule in some topologies, they will be described in this document and illustrated by an appropriate call flow.)</span></span>

- <span data-ttu-id="0d0c4-178">Office 365 の Teams メディアエンドポイントは、通話の種類に基づくメディア処理のニーズに基づいて使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-178">A Teams media endpoint in Office 365 is used based on media processing needs and not based on call type.</span></span> <span data-ttu-id="0d0c4-179">(たとえば、ポイントツーポイントの通話では、クラウドのメディアエンドポイントを使用して、議事録や記録のためにメディアの処理を行うことができます。参加者が2人の会議では、クラウドのメディアエンドポイントを使用することはできません)。ただし、ほとんどの会議では、会議がホストされている場所に割り当てられる、ミキシングとルーティングの目的でメディアエンドポイントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-179">(For example, a point-to-point call may use a media endpoint in the cloud to process media for transcription or recording, while a conference with two participants may not use any media endpoint in the cloud.) However, most conferences will use a media endpoint for mixing and routing purposes, allocated where the conference is hosted.</span></span> <span data-ttu-id="0d0c4-180">顧客のネットワークファイアウォールの制限により、クライアントからメディアエンドポイントに送信されたメディアトラフィックが直接ルーティングされる場合や、必要に応じて、Office 365 でトランスポートリレーを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-180">The media traffic sent from a client to the media endpoint may be routed directly or use a Transport Relay in Office 365 if required due to customer network firewall restrictions.</span></span>

- <span data-ttu-id="0d0c4-181">ピアツーピア通話用のメディアトラフィックは、通話がクラウドでメディアエンドポイントを必要としないことを前提として、利用可能な最も直接的なルートを受け取ります (前の原則を参照)。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-181">Media traffic for peer-to-peer calls take the most direct route that is available, assuming that the call doesn't mandate a media endpoint in the cloud (see previous principle).</span></span> <span data-ttu-id="0d0c4-182">優先ルートはリモートピア (クライアント) に直接送信されますが、そのルートが利用できない場合は、1つ以上のトランスポートリレーがトラフィックを中継します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-182">The preferred route is direct to the remote peer (client), but if that route isn't available, then one or more Transport Relays will relay traffic.</span></span> <span data-ttu-id="0d0c4-183">メディアトラフィックは、メディアの品質に影響を与えるため、パケットコントローラー、VPN サーバーなどの横にあるサーバーではないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-183">It is recommended that media traffic shall not transverse servers such as packet shapers, VPN servers, and so on, since this will impact the media quality.</span></span>

- <span data-ttu-id="0d0c4-184">シグナリングトラフィックは、常に最も近いサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-184">Signaling traffic always goes to the closest server to the user.</span></span>

<span data-ttu-id="0d0c4-185">選択されているメディアパスの詳細については、「 [Microsoft Teams でのメディアフローの概要-BRK4016](https://www.youtube.com/watch?v=1tmHMIlAQdo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-185">To learn more about the details on the media path that is chosen, see [Understanding Media Flows in Microsoft Teams - BRK4016](https://www.youtube.com/watch?v=1tmHMIlAQdo).</span></span>

## <a name="call-flows-in-various-topologies"></a><span data-ttu-id="0d0c4-186">さまざまなトポロジでのコールフロー</span><span class="sxs-lookup"><span data-stu-id="0d0c4-186">Call flows in various topologies</span></span>

### <a name="teams-topology"></a><span data-ttu-id="0d0c4-187">Teams のトポロジ</span><span class="sxs-lookup"><span data-stu-id="0d0c4-187">Teams topology</span></span>

<span data-ttu-id="0d0c4-188">このトポロジは、Skype for Business Server や電話システムの直接ルーティングなど、オンプレミスの展開がなくてもクラウドから Teams サービスを利用する顧客によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-188">This topology is used by customers that leverage Teams services from the cloud without any on-premises deployment, such as Skype for Business Server or Phone System Direct Routing.</span></span> <span data-ttu-id="0d0c4-189">さらに、Office 365 へのインターフェイスは、Azure Express Route を使わずにインターネット経由で行われます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-189">In addition, the interface to Office 365 is done over the Internet without Azure Express Route.</span></span>

<span data-ttu-id="0d0c4-190">[![Microsoft Teams Online の通話フロー図01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-190">[![Microsoft Teams Online Call Flows Figure 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span></span>

<span data-ttu-id="0d0c4-191">*図 1-Teams のトポロジ*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-191">*Figure 1 - Teams topology*</span></span>

<span data-ttu-id="0d0c4-192">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-192">Note that:</span></span>

- <span data-ttu-id="0d0c4-193">上の図の矢印の方向は、企業境界での接続に影響を与える通信の開始方向を反映しています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-193">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="0d0c4-194">メディア用に UDP の場合は、最初のパケットが逆方向に流れる場合がありますが、これらのパケットは、他の方向のパケットが流れるまでブロックされることがあります。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-194">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>
- <span data-ttu-id="0d0c4-195">Teams は Skype for Business Online と並行して展開されるため、クライアントは "Teams/SFB ユーザー" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-195">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user."</span></span>

<span data-ttu-id="0d0c4-196">詳細については、次の記事の後のオプションのトポロジを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-196">You can find more information on the following optional topologies later in the article:</span></span>

- <span data-ttu-id="0d0c4-197">Skype for Business のオンプレミスの展開については、「 **Teams ハイブリッドトポロジ**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-197">Skype for Business on-premises deployment is described in **Teams hybrid topology**.</span></span>
- <span data-ttu-id="0d0c4-198">電話システムの直接ルーティング (PSTN 接続用) については、「**ダイレクトルーティングトポロジを使用した Teams**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-198">Phone System Direct Routing (for PSTN connectivity) is described in **Teams with Direct Routing topology**.</span></span>
- <span data-ttu-id="0d0c4-199">エクスプレスルートについては、「 **Express route の最適化」を**参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-199">Express Route is described in **Teams with Express Route optimization**.</span></span>

<span data-ttu-id="0d0c4-200">**フローの説明**:</span><span class="sxs-lookup"><span data-stu-id="0d0c4-200">**Flow descriptions**:</span></span>

- <span data-ttu-id="0d0c4-201">**フロー 2** –ユーザーのチームエクスペリエンスの一部として、顧客ネットワーク上のユーザーによって開始されたフローを表します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-201">**Flow 2** – Represents a flow initiated by a user on the customer network to the Internet as a part of the user's Teams experience.</span></span> <span data-ttu-id="0d0c4-202">これらのフローの例としては、DNS とピアツーピアメディアがあります。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-202">Examples of these flows are DNS and peer-to-peer media.</span></span>
- <span data-ttu-id="0d0c4-203">**フロー 2 '** –リモートのモバイルチームユーザーによって開始されたフロー (顧客ネットワークへの VPN を含む) を表します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-203">**Flow 2'** – Represents a flow initiated by a remote mobile Teams user, with VPN to the customer network.</span></span>
- <span data-ttu-id="0d0c4-204">**フロー 3** –リモートのモバイルチームユーザーによって開始されたフロー (Office 365 またはチームのエンドポイント) を表します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-204">**Flow 3** – Represents a flow initiated by a remote mobile Teams user to Office 365/Teams endpoints.</span></span>
- <span data-ttu-id="0d0c4-205">**フロー 4** –顧客ネットワーク上のユーザーによって開始されたフロー (Office 365 またはチームのエンドポイント) を表します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-205">**Flow 4** – Represents a flow initiated by a user on the customer network to Office 365/Teams endpoints.</span></span>
- <span data-ttu-id="0d0c4-206">**フロー 5** – teams ユーザーと別のチームまたは顧客ネットワーク内の Skype for business ユーザーとの間のピアツーピアメディアフローを表します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-206">**Flow 5** – Represents a peer-to-peer media flow between a Teams user and another Teams or Skype for Business user within the customer network.</span></span>
- <span data-ttu-id="0d0c4-207">**フロー 6** –リモートのモバイルチームユーザーと別のリモートモバイルチーム、またはインターネット上の Skype for business ユーザーとの間のピアツーピアメディアフローを表します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-207">**Flow 6** – Represents a peer-to-peer media flow between a remote mobile Teams user and another remote mobile Teams or Skype for Business user over the Internet.</span></span>

#### <a name="use-case-one-to-one"></a><span data-ttu-id="0d0c4-208">ユースケース: 1 対1</span><span class="sxs-lookup"><span data-stu-id="0d0c4-208">Use case: One-to-one</span></span>

<span data-ttu-id="0d0c4-209">1対1の通話では、発信者が IP アドレス/ポート (中継によって表示されるクライアントのパブリック IP アドレスなど) で構成される一連の候補を取得する共通モデルを使います。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-209">One-to-one calls use a common model in which the caller will obtain a set of candidates consisting of IP addresses/ports, including local, relay, and reflexive (public IP address of client as seen by the relay) candidates.</span></span> <span data-ttu-id="0d0c4-210">発信者は、これらの候補を、通話先に送信します。また、同様の候補を取得し、呼び出し元に送信します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-210">The caller sends these candidates to the called party; the called party also obtains a similar set of candidates and sends them to the caller.</span></span> <span data-ttu-id="0d0c4-211">STUN connectivity のチェックメッセージは、どの発信者/通話相手側メディアパスが機能し、最適な作業パスが選択されているかを確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-211">STUN connectivity check messages are used to find which caller/called party media paths work, and the best working path is selected.</span></span> <span data-ttu-id="0d0c4-212">メディア (SRTP を使ってセキュリティ保護された RTP/RTCP パケット) は、選択した候補ペアを使って送信されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-212">Media (that is, RTP/RTCP packets secured using SRTP) are then sent using the selected candidate pair.</span></span> <span data-ttu-id="0d0c4-213">トランスポートリレーは、Office 365 の一部として展開されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-213">The Transport relay is deployed as part of Office 365.</span></span>

<span data-ttu-id="0d0c4-214">ローカル IP アドレス/ポート候補または再帰的候補が接続されている場合、クライアント間 (または NAT を使用) 間の直接パスがメディア用に選択されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-214">If the local IP address/port candidates or the reflexive candidates have connectivity, then the direct path between the clients (or using a NAT) will be selected for media.</span></span> <span data-ttu-id="0d0c4-215">クライアントが顧客ネットワーク上にある場合は、ダイレクトパスを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-215">If the clients are both on the customer network, then the direct path should be selected.</span></span> <span data-ttu-id="0d0c4-216">これには、お客様のネットワーク内で直接の UDP 接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-216">This requires direct UDP connectivity within the customer network.</span></span> <span data-ttu-id="0d0c4-217">クライアントが両方とも nomadic クラウドユーザーである場合は、NAT/ファイアウォールによっては、メディアに直接接続が使用されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-217">If the clients are both nomadic cloud users, then depending on the NAT/firewall, media may use direct connectivity.</span></span>

<span data-ttu-id="0d0c4-218">1つのクライアントが顧客ネットワーク上にあり、一方が外部 (たとえば、モバイルクラウドユーザー) のクライアントである場合は、ローカルまたは再帰の候補の間の直接接続が機能していることはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-218">If one client is internal on the customer network and one client is external (for example, a mobile cloud user), then it is unlikely that direct connectivity between the local or reflexive candidates is working.</span></span> <span data-ttu-id="0d0c4-219">この場合、いずれかのクライアントからトランスポートリレー候補のいずれかを使用することをお勧めします (たとえば、内部クライアントは、Office 365 のトランスポートリレーからリレー候補を取得している必要があります)。外部クライアントは、転送された、RTP/RTCP パケットをトランスポートリレーに送信できます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-219">In this case, an option is to use one of the Transport Relay candidates from either client (for example, the internal client obtained a relay candidate from the Transport relay in Office 365; the external client needs to be able to send STUN/RTP/RTCP packets to the transport relay).</span></span> <span data-ttu-id="0d0c4-220">別の方法として、内部クライアントが、モバイルクラウドクライアントによって取得された relay 候補に送信されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-220">Another option is the internal client sends to the relay candidate obtained by the mobile cloud client.</span></span> <span data-ttu-id="0d0c4-221">メディアの UDP 接続は強くお勧めしますが、TCP はサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-221">Note that, although UDP connectivity for media is highly recommended, TCP is supported.</span></span>

<span data-ttu-id="0d0c4-222">**高レベルの手順**:</span><span class="sxs-lookup"><span data-stu-id="0d0c4-222">**High-level steps**:</span></span>

1. <span data-ttu-id="0d0c4-223">Teams ユーザーは、フロー2を使って URL ドメイン名 (DNS) を解決します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-223">Teams User A resolves URL domain name (DNS) using flow 2.</span></span>
1. <span data-ttu-id="0d0c4-224">Teams ユーザー A は、flow 4 を使って、Teams トランスポートリレーにメディアリレーポートを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-224">Teams User A allocates a media Relay port on Teams Transport Relay using flow 4.</span></span>
1. <span data-ttu-id="0d0c4-225">Teams ユーザー A は、フロー 4 365 を使用して、ICE 候補を使って "招待" を送信します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-225">Teams User A sends "invite" with ICE candidates using flow 4 to Office 365.</span></span>
1. <span data-ttu-id="0d0c4-226">Office 365 は、flow 4 を使ってチームユーザー B に通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-226">Office 365 sends notification to Teams User B using flow 4.</span></span>
1. <span data-ttu-id="0d0c4-227">Teams ユーザー B は、flow 4 を使って Teams トランスポートリレーにメディアリレーポートを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-227">Teams User B allocates a media Relay port on Teams Transport Relay using flow 4.</span></span>
1. <span data-ttu-id="0d0c4-228">Teams ユーザー B はフロー4を使用して、ICE 候補を使って "answer" を送信します。フロー4を使って Teams ユーザー A に戻されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-228">Teams User B sends "answer" with ICE candidates using flow 4, which is forwarded back to Teams User A using Flow 4.</span></span>
1. <span data-ttu-id="0d0c4-229">Teams ユーザー A と Teams ユーザー B が ICE 接続テストを呼び出し、最適なメディアパスが選択されています (さまざまなユースケースについては、以下の図を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-229">Teams User A and Teams User B invoke ICE connectivity tests and the best available media path is selected (see diagrams below for various use cases).</span></span>
1. <span data-ttu-id="0d0c4-230">Teams ユーザーは、フロー4を使ってテレメトリを Office 365 に送信します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-230">Teams Users send telemetry to Office 365 using flow 4.</span></span>

<span data-ttu-id="0d0c4-231">**顧客ネットワーク内:**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-231">**Within customer network:**</span></span>

<span data-ttu-id="0d0c4-232">[![Microsoft Teams Online の通話フロー図02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-232">[![Microsoft Teams Online Call Flows Figure 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span></span>

<span data-ttu-id="0d0c4-233">*図 2-顧客ネットワーク内*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-233">*Figure 2 - Within customer network*</span></span>

<span data-ttu-id="0d0c4-234">手順7では、ピアツーピアメディアフロー5が選択されています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-234">In step 7, peer-to-peer media flow 5 is selected.</span></span>

<span data-ttu-id="0d0c4-235">メディアは双方向です。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-235">Media is bidirectional.</span></span> <span data-ttu-id="0d0c4-236">フロー5の方向は、このドキュメント内のすべてのフローと一貫性のある接続の観点から、1つのサイドが通信を開始することを示します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-236">The direction of flow 5 indicates that one side initiates the communication from a connectivity perspective, consistent with all the flows in this document.</span></span> <span data-ttu-id="0d0c4-237">この場合、どちらのエンドポイントも顧客のネットワーク内にあるため、どの方向を使用するかは関係ありません。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-237">In this case, it doesn't matter which direction is used because both endpoints are within the customer network.</span></span>

<span data-ttu-id="0d0c4-238">**外部ユーザーに対する顧客ネットワーク (メディアトランスポートリレーによって中継されるメディア):**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-238">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="0d0c4-239">[![Microsoft Teams Online の通話フロー図03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-239">[![Microsoft Teams Online Call Flows Figure 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span></span>

<span data-ttu-id="0d0c4-240">*図 3-外部ユーザーへの顧客ネットワーク (Teams トランスポートリレーによるメディアの中継)*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-240">*Figure 3 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="0d0c4-241">手順7では、[顧客ネットワーク] から [Office 365] のフロー3、[リモートモバイルチームユーザーから Office 365 へのフロー 3] が選択されています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-241">In step 7, flow 4, from customer network to Office 365, and flow 3, from remote mobile Teams user to Office 365, are selected.</span></span> <span data-ttu-id="0d0c4-242">これらのフローは、Office 365 内の Teams トランスポートリレーによって中継されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-242">These flows are relayed by Teams Transport Relay within Office 365.</span></span>

<span data-ttu-id="0d0c4-243">[メディア] は、双方向で接続の観点から通信を開始する側を示します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-243">Media is bidirectional, where direction indicates which side initiates the communication from a connectivity perspective.</span></span> <span data-ttu-id="0d0c4-244">この場合、さまざまなトランスポートプロトコルとアドレスを使用して、シグナルおよびメディアにこれらのフローが使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-244">In this case, these flows are used for signaling and media, using different transport protocols and addresses.</span></span>

<span data-ttu-id="0d0c4-245">**外部ユーザー (ダイレクトメディア) に対する顧客ネットワーク:**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-245">**Customer network to external user (direct media):**</span></span>

<span data-ttu-id="0d0c4-246">[![Microsoft Teams Online の通話フロー図04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-246">[![Microsoft Teams Online Call Flows Figure 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span></span>

<span data-ttu-id="0d0c4-247">*図 4-外部ユーザー (ダイレクトメディア) に対する顧客ネットワーク*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-247">*Figure 4 - Customer network to external user (direct media)*</span></span>

<span data-ttu-id="0d0c4-248">手順7では、[顧客ネットワークからインターネット (クライアントのピア) へのフロー 2] が選択されています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-248">In step 7, flow 2, from customer network to the Internet (client's peer), is selected.</span></span>

- <span data-ttu-id="0d0c4-249">リモートモバイルユーザーのダイレクトメディア (Office 365 経由では中継されません) はオプションです。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-249">Direct media with remote mobile user (not relayed through Office 365) is optional.</span></span> <span data-ttu-id="0d0c4-250">つまり、お客様は、このパスをブロックして、Office 365 でトランスポートリレー経由でメディアパスを強制することができます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-250">In other words, customer may block this path to enforce a media path through Transport Relay in Office 365.</span></span>

- <span data-ttu-id="0d0c4-251">メディアは双方向です。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-251">Media is bidirectional.</span></span> <span data-ttu-id="0d0c4-252">フロー2からリモートモバイルユーザーまでの方向は、一方のサイドが接続の観点から通信を開始することを示します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-252">The direction of flow 2 to remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

<span data-ttu-id="0d0c4-253">**内部ユーザーに対する VPN ユーザー (Teams トランスポートリレーによって中継されるメディア)**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-253">**VPN user to internal user (media relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="0d0c4-254">[![Microsoft Teams Online の通話フロー図05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-254">[![Microsoft Teams Online Call Flows Figure 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span></span>

<span data-ttu-id="0d0c4-255">*図 5-内部ユーザーに対する VPN ユーザー (Teams トランスポートリレーによって中継されるメディア)*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-255">*Figure 5 - VPN user to internal user (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="0d0c4-256">VPN と顧客ネットワーク間のシグナリングはフロー 2 ' を使用しています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-256">Signaling between the VPN to the customer network is using flow 2'.</span></span> <span data-ttu-id="0d0c4-257">顧客ネットワークと Office 365 間のシグナリングはフロー4を使用しています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-257">Signaling between the customer network and Office 365 is using flow 4.</span></span> <span data-ttu-id="0d0c4-258">ただし、メディアは VPN をバイパスし、Office 365 の Teams メディアリレーを通じて、フロー3と4を使ってルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-258">However, media bypasses the VPN and is routed using flows 3 and 4 through Teams media relay in Office 365.</span></span>

<span data-ttu-id="0d0c4-259">**内部ユーザー (ダイレクトメディア) に対する VPN ユーザー**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-259">**VPN user to internal user (direct media)**</span></span>

<span data-ttu-id="0d0c4-260">[![Microsoft Teams Online の通話フロー図06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-260">[![Microsoft Teams Online Call Flows Figure 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span></span>

<span data-ttu-id="0d0c4-261">*図 6-VPN ユーザーと内部ユーザー (ダイレクトメディア)*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-261">*Figure 6 - VPN user to internal user (direct media)*</span></span>

<span data-ttu-id="0d0c4-262">VPN と顧客ネットワーク間のシグナリングはフロー 2 ' を使用しています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-262">Signaling between the VPN to the customer network is using flow 2'.</span></span> <span data-ttu-id="0d0c4-263">顧客ネットワークと Office 365 間のシグナリングはフロー4を使用しています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-263">Signaling between the customer network and Office 365 is using flow 4.</span></span> <span data-ttu-id="0d0c4-264">ただし、メディアは VPN をバイパスし、ユーザーのネットワークからインターネットへのフロー2を使ってルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-264">However, media bypasses the VPN and is routed using flow 2 from the customer network to the Internet.</span></span>

<span data-ttu-id="0d0c4-265">メディアは双方向です。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-265">Media is bidirectional.</span></span> <span data-ttu-id="0d0c4-266">リモートモバイルユーザーのフロー2の方向は、一方のサイドが接続の観点から通信を開始することを示します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-266">The direction of flow 2 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

<span data-ttu-id="0d0c4-267">**外部ユーザー (ダイレクトメディア) に対する VPN ユーザー**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-267">**VPN user to external user (direct media)**</span></span>

<span data-ttu-id="0d0c4-268">[![Microsoft Teams の通話フロー図07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-268">[![Microsoft Teams call flows Figure 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span></span>

<span data-ttu-id="0d0c4-269">*図 7-VPN ユーザーから外部ユーザーへの接続 (ダイレクトメディア)*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-269">*Figure 7 - VPN user to external user (direct media)*</span></span>

<span data-ttu-id="0d0c4-270">VPN ユーザーと顧客ネットワークとの間のシグナリングはフロー2を使用しており、フロー4を Office 365 に使用しています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-270">Signaling between the VPN user to the customer network is using flow 2' and using flow 4 to Office 365.</span></span> <span data-ttu-id="0d0c4-271">ただし、メディアは VPN をバイパスし、フロー6を使ってルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-271">However, media bypasses VPN and is routed using flow 6.</span></span>

<span data-ttu-id="0d0c4-272">メディアは双方向です。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-272">Media is bidirectional.</span></span> <span data-ttu-id="0d0c4-273">リモートモバイルユーザーへのフロー6の方向は、一方のサイドが接続の観点から通信を開始することを示します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-273">The direction of flow 6 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a><span data-ttu-id="0d0c4-274">使用例: Office 365 トランク経由でのチームと PSTN</span><span class="sxs-lookup"><span data-stu-id="0d0c4-274">Use Case: Teams to PSTN through Office 365 Trunk</span></span>

<span data-ttu-id="0d0c4-275">Office 365 には、公衆交換電話網 (PSTN) での通話の発信と受信を可能にする電話システムがあります。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-275">Office 365 has a Phone System that allows placing and receiving calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="0d0c4-276">PSTN トランクが電話システムの通話プランを使って接続されている場合、このユースケースには特別な接続要件はありません。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-276">If the PSTN trunk is connected using the Phone System Calling Plan, then there are no special connectivity requirements for this use case.</span></span> <span data-ttu-id="0d0c4-277">(独自のオンプレミス PSTN トランクを Office 365 に接続する場合は、電話システムのダイレクトルーティングを使うことができます)。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-277">(If you want to connect your own on-premises PSTN trunk to Office 365, you can use Phone System Direct Routing.)</span></span>

<span data-ttu-id="0d0c4-278">[![Microsoft Teams Online の通話フロー図08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-278">[![Microsoft Teams Online Call Flows Figure 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span></span>

<span data-ttu-id="0d0c4-279">*図 8-Office 365 トランク経由のチーム間の PSTN*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-279">*Figure 8 - Teams to PSTN through Office 365 Trunk*</span></span>

#### <a name="use-case-teams-meeting"></a><span data-ttu-id="0d0c4-280">使用例: Teams 会議</span><span class="sxs-lookup"><span data-stu-id="0d0c4-280">Use case: Teams meeting</span></span>

<span data-ttu-id="0d0c4-281">音声/ビデオ/画面共有 (VBSS) 会議サーバーは、Office 365 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-281">The audio/video/screen sharing (VBSS) conferencing server is part of Office 365.</span></span> <span data-ttu-id="0d0c4-282">これには、顧客ネットワークから到達可能である必要があり、Nomadic Cloud クライアントから到達可能である必要があるパブリック IP アドレスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-282">It has a public IP address that must be reachable from the customer network and must be reachable from a Nomadic Cloud client.</span></span> <span data-ttu-id="0d0c4-283">クライアント/エンドポイントごとに、会議サーバーに接続できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-283">Each client/endpoint needs to be able to connect to the conferencing server.</span></span>

<span data-ttu-id="0d0c4-284">内部クライアントでは、1対1の通話の場合と同じ方法で、ローカル、再帰、およびリレーの候補が取得されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-284">Internal clients will obtain local, reflexive, and relay candidates in the same manner as described for one-to-one calls.</span></span> <span data-ttu-id="0d0c4-285">クライアントは、招待状にこれらの候補を会議サーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-285">The clients will send these candidates to the conferencing server in an invite.</span></span> <span data-ttu-id="0d0c4-286">会議サーバーは、公開された IP アドレスを持っているため、relay を使用しません。そのため、ローカル IP アドレス候補で応答します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-286">The conferencing server does not use a relay since it has a publicly reachable IP address, so it responds with its local IP address candidate.</span></span> <span data-ttu-id="0d0c4-287">クライアントと会議サーバーは、1対1の通話の場合と同じ方法で接続性を確認します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-287">The client and conferencing server will check connectivity in the same manner described for one-to-one calls.</span></span>

<span data-ttu-id="0d0c4-288">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-288">Note that:</span></span>

- <span data-ttu-id="0d0c4-289">Teams クライアントは Skype for Business 会議に参加できず、Skype for Business クライアントは Teams 会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-289">Teams clients cannot join Skype for Business meetings, and Skype for Business clients cannot join Teams meetings.</span></span>

- <span data-ttu-id="0d0c4-290">PSTN ユーザーは、会議の開催者の PSTN 通話や会議のプロビジョニングに応じて、"ダイヤルイン" または "ダイヤルアウト" を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-290">A PSTN user optionally "Dials IN" or is "Dialed OUT", depending on the meeting's organizer PSTN Calling and/or conferencing provisioning.</span></span>

- <span data-ttu-id="0d0c4-291">ゲストユーザーまたはお客様のユーザーがゲストプライベートネットワークから参加できる場合があります。これは、厳密な規則で FW/NAT を使用して保護されています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-291">A guest user or a customer user may join from a guest private network, which is protected using FW/NAT with strict rules.</span></span>

<span data-ttu-id="0d0c4-292">[![Microsoft Teams Online の通話フロー図09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-292">[![Microsoft Teams Online Call Flows Figure 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span></span>

<span data-ttu-id="0d0c4-293">*図 9-Teams 会議*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-293">*Figure 9 - Teams Meeting*</span></span>

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a><span data-ttu-id="0d0c4-294">使用例: オンプレミスの Skype for Business とのフェデレーション</span><span class="sxs-lookup"><span data-stu-id="0d0c4-294">Use case: Federation with Skype for Business on premises</span></span>

<span data-ttu-id="0d0c4-295">**Office 365 で Teams トランスポートリレーによって中継されるメディア**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-295">**Media relayed by Teams Transport Relay in Office 365**</span></span>

<span data-ttu-id="0d0c4-296">[![Microsoft Teams Online の通話フロー図10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-296">[![Microsoft Teams Online Call Flows Figure 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span></span>

<span data-ttu-id="0d0c4-297">*図 10-Office 365 で Teams トランスポートリレーによって中継されるメディア*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-297">*Figure 10 - Media relayed by Teams Transport Relay in Office 365*</span></span>

<span data-ttu-id="0d0c4-298">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-298">Note that:</span></span>

- <span data-ttu-id="0d0c4-299">フェデレーションとは、2つのテナント間の通信を定義することです。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-299">Federation is, by definition, a communication between two tenants.</span></span> <span data-ttu-id="0d0c4-300">この場合、federates を使用するテナント A は、オンプレミスの Skype for Business を使用するテナント B と共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-300">In this case, tenant A, which uses Teams, federates with tenant B, which uses Skype for Business on premises.</span></span> <span data-ttu-id="0d0c4-301">テナント B でも Office 365 を使用している場合、Skype for Business クライアントでは、フロー3を使って Office 365 に接続していました。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-301">If tenant B is also using Office 365, then the Skype for Business client would have used flow 3 to connect with Office 365.</span></span>

- <span data-ttu-id="0d0c4-302">フェデレーションされた Skype for Business クライアントからオンプレミスの Skype for business Server へのシグナルおよびメディアは、このドキュメントの範囲外です。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-302">Signaling and media from the federated Skype for Business client to on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="0d0c4-303">ただし、わかりやすくするために、ここで示しています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-303">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="0d0c4-304">チームと Skype for Business の間のシグナリングは、Office 365 のゲートウェイによってブリッジされます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-304">Signaling between Teams and Skype for Business is bridged by a gateway in Office 365.</span></span>

- <span data-ttu-id="0d0c4-305">このケースのメディアは、Office 365 の Teams トランスポートリレーによって、フロー4を使って顧客ネットワークとリモートの Skype for Business クライアントに中継されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-305">Media in this case is relayed by Teams Transport Relay in Office 365 to the customer network and remote Skype for Business client using flow 4.</span></span>

<span data-ttu-id="0d0c4-306">**フェデレーションテナントでの Skype for Business メディアリレーによるメディアの中継**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-306">**Media relayed by Skype for Business Media Relay in federated tenant**</span></span>

<span data-ttu-id="0d0c4-307">[![Microsoft Teams Online の通話フロー図11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-307">[![Microsoft Teams Online Call Flows Figure 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span></span>

<span data-ttu-id="0d0c4-308">*図 11-フェデレーションされたテナントでの Skype for Business メディアリレーによるメディアの中継*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-308">*Figure 11 - Media relayed by Skype for Business Media Relay in federated tenant*</span></span>

<span data-ttu-id="0d0c4-309">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-309">Note that:</span></span>

- <span data-ttu-id="0d0c4-310">フェデレーションされた Skype for Business クライアントから社内の Skype for business Server へのシグナリングとメディアは、このドキュメントの範囲外です。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-310">Signaling and media from the federated Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="0d0c4-311">ただし、わかりやすくするために、ここで示しています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-311">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="0d0c4-312">チームと Skype for Business の間のシグナリングは、Office 365 のゲートウェイによってブリッジされます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-312">Signaling between Teams and Skype for Business is bridged by a Gateway in Office 365.</span></span>

- <span data-ttu-id="0d0c4-313">このケースのメディアは、フロー2を使って、Skype for Business のオンプレミスメディアリレーによって、お客様のネットワークに中継されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-313">Media in this case is relayed by Skype for Business on-premises Media Relay to the customer network using flow 2.</span></span> <span data-ttu-id="0d0c4-314">(Teams ユーザーからフェデレーションされた顧客ネットワークでのリモートメディアリレーへのトラフィックは、逆方向のトラフィックが流れるまでに、最初にメディアリレーによってブロックされることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-314">(Note that traffic from Teams user to the remote Media Relay in the federated customer network will be initially blocked by the Media Relay until traffic in the reverse direction starts to flow.</span></span> <span data-ttu-id="0d0c4-315">ただし、双方向フローは両方の方向に接続を開きます。)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-315">However, the bidirectional flow will open connectivity in both directions.)</span></span>

<span data-ttu-id="0d0c4-316">**Direct (ピアツーピア)**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-316">**Direct (peer-to-peer)**</span></span>

<span data-ttu-id="0d0c4-317">[![Microsoft Teams Online の通話フロー図12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-317">[![Microsoft Teams Online Call Flows Figure 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span></span>

<span data-ttu-id="0d0c4-318">*図 12-直接 (ピアツーピア)*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-318">*Figure 12 - Direct (peer-to-peer)*</span></span>

### <a name="teams-hybrid-topology"></a><span data-ttu-id="0d0c4-319">Teams ハイブリッドトポロジ</span><span class="sxs-lookup"><span data-stu-id="0d0c4-319">Teams hybrid topology</span></span>

<span data-ttu-id="0d0c4-320">このトポロジには、Skype for Business のオンプレミス展開を含む Teams が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-320">This topology includes Teams with a Skype for Business on-premises deployment.</span></span>

<span data-ttu-id="0d0c4-321">[![Microsoft Teams Online の通話フロー図13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-321">[![Microsoft Teams Online Call Flows Figure 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span></span>

<span data-ttu-id="0d0c4-322">*図 13-Teams ハイブリッドトポロジ*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-322">*Figure 13 - Teams hybrid topology*</span></span>

- <span data-ttu-id="0d0c4-323">上の図の矢印の方向は、企業境界での接続に影響を与える通信の開始方向を反映しています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-323">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="0d0c4-324">メディア用に UDP の場合は、最初のパケットが逆方向に流れる場合がありますが、これらのパケットは、他の方向のパケットが流れるまでブロックされることがあります。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-324">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="0d0c4-325">Teams は Skype for Business Online と並行して展開されるため、クライアントは "Teams/SFB ユーザー" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-325">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user."</span></span>

<span data-ttu-id="0d0c4-326">追加のフロー (チームトポロジの一番上):</span><span class="sxs-lookup"><span data-stu-id="0d0c4-326">Additional flow (on top of Teams topology):</span></span>

- <span data-ttu-id="0d0c4-327">**フロー 5a** –顧客ネットワーク内の Teams ユーザーと、顧客ネットワーク edge での Skype for business のオンプレミスメディアリレーとの間のピアツーピアメディアフローを表します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-327">**Flow 5A** – Represents a peer-to-peer media flow between a Teams user within the customer network and a Skype for Business on-premises media relay at the customer network edge.</span></span>

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a><span data-ttu-id="0d0c4-328">ユースケース: チームと Skype for Business の一対一</span><span class="sxs-lookup"><span data-stu-id="0d0c4-328">Use case: Teams to Skype for Business one-to-one</span></span>

<span data-ttu-id="0d0c4-329">**顧客ネットワーク内のハイブリッド**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-329">**Hybrid within the customer network**</span></span>

<span data-ttu-id="0d0c4-330">[![Microsoft Teams のオンライン通話フロー図14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-330">[![Microsoft Teams Online Call Flows Figure 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span></span>

<span data-ttu-id="0d0c4-331">*図 14-顧客ネットワーク内のハイブリッド*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-331">*Figure 14 - Hybrid within customer network*</span></span>

<span data-ttu-id="0d0c4-332">チームと Skype for Business の間のシグナリングは、Office 365 のゲートウェイによってブリッジされます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-332">Signaling between Teams and Skype for Business is bridged by a gateway in Office 365.</span></span> <span data-ttu-id="0d0c4-333">ただし、メディアは、フロー5を使って顧客のネットワーク内で直接ピアツーピアにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-333">However, media is routed directly peer-to-peer within the customer network using flow 5.</span></span>

<span data-ttu-id="0d0c4-334">**外部の Skype for Business ユーザーとのハイブリッド顧客ネットワーク– Office 365 によって中継される**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-334">**Hybrid customer network with external Skype for Business user – relayed by Office 365**</span></span>

<span data-ttu-id="0d0c4-335">[![Microsoft Teams Online の通話フロー図15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-335">[![Microsoft Teams Online Call Flows Figure 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span></span>

<span data-ttu-id="0d0c4-336">*図 15-外部の Skype for Business ユーザーとのハイブリッド顧客ネットワーク (Office 365 による中継)*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-336">*Figure 15 - Hybrid customer network with external Skype for Business user - relayed by Office 365*</span></span>

<span data-ttu-id="0d0c4-337">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-337">Note that:</span></span>

- <span data-ttu-id="0d0c4-338">Skype for Business クライアントからオンプレミスの Skype for Business Server へのシグナリングとメディアは、このドキュメントの範囲外です。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-338">Signaling and media from the Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="0d0c4-339">ただし、わかりやすくするために、ここで示しています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-339">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="0d0c4-340">チームと Skype for Business の間のシグナリングは、Office 365 のゲートウェイによってブリッジされます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-340">Signaling between Teams and Skype for Business is bridged by a gateway in Office 365.</span></span>

- <span data-ttu-id="0d0c4-341">メディアは、Office 365 の Teams トランスポートリレーを通じて、フロー4経由で顧客ネットワークに中継されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-341">Media is relayed through Teams Transport Relay in Office 365 to the customer network through flow 4.</span></span>

<span data-ttu-id="0d0c4-342">**外部の Skype for Business ユーザーを使用したハイブリッド顧客ネットワーク-オンプレミスエッジによる中継**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-342">**Hybrid customer network with external Skype for Business user – relayed by on-premises Edge**</span></span>

<span data-ttu-id="0d0c4-343">[![Microsoft Teams Online の通話フロー図16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-343">[![Microsoft Teams Online Call Flows Figure 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span></span>

<span data-ttu-id="0d0c4-344">*図 16-外部の Skype for Business ユーザーを使用したハイブリッド顧客ネットワーク-オンプレミスエッジによる中継*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-344">*Figure 16 - Hybrid customer network with external Skype for Business user - relayed by on-premises Edge*</span></span>

<span data-ttu-id="0d0c4-345">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-345">Note that:</span></span>

- <span data-ttu-id="0d0c4-346">Skype for Business クライアントからオンプレミスの Skype for business Server へのシグナリングとメディアは、このドキュメントの範囲外です。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-346">Signaling and media from Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="0d0c4-347">ただし、わかりやすくするために、ここで示しています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-347">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="0d0c4-348">シグナリングは、Office 365 のゲートウェイでブリッジされます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-348">Signaling is bridged by a gateway in Office 365.</span></span>

- <span data-ttu-id="0d0c4-349">メディアは、Skype for Business オンプレミスエッジ内の skype for Business メディアリレーによって、メディアフロー5A を使用して、顧客ネットワーク内の Teams ユーザーに中継されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-349">Media is relayed by Skype for Business Media Relay within Skype for Business on-premises Edge to Teams user within the customer network using media flow 5A.</span></span>

### <a name="teams-with-phone-system-direct-routing-topology"></a><span data-ttu-id="0d0c4-350">電話システムのダイレクトルーティングトポロジを使用しているチーム</span><span class="sxs-lookup"><span data-stu-id="0d0c4-350">Teams with Phone System Direct Routing topology</span></span>

<span data-ttu-id="0d0c4-351">このトポロジには、電話システムのダイレクトルーティングを行うチームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-351">This topology includes Teams with Phone System Direct Routing.</span></span>

<span data-ttu-id="0d0c4-352">ダイレクトルーティングでは、サポートされているオンプレミスのユーザー所有のセッションボーダーコントローラー (SBC) ハードウェアデバイスを Office 365 にペアリングし、そのデバイスにテレフォニートランクを接続して、サードパーティの公衆交換電話網 (PSTN) サービスプロバイダーを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-352">Direct Routing enables you to use a third-party Public Switched Telephone Network (PSTN) service provider by pairing a supported on-premises customer-owned Session Border Controller (SBC) hardware device to Office 365, and then connecting the telephony trunk to that device.</span></span>

<span data-ttu-id="0d0c4-353">このシナリオをサポートするには、お客様は Microsoft 認定パートナーの1つから直接ルーティングするための認定された SBC を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-353">To support this scenario, the customer must deploy a certified SBC for Direct Routing from one of Microsoft's certified partners.</span></span> <span data-ttu-id="0d0c4-354">SBC は、ベンダーによって推奨されるように構成する必要があります。また、直接 UDP トラフィック用に Office 365 からルーティングすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-354">The SBC must be configured as recommended by the vendor, and be routable from Office 365 for direct UDP traffic.</span></span> <span data-ttu-id="0d0c4-355">メディアは、Teams から直接、または Skype for Business クライアントから SBC (Teams のゲートウェイを経由しない) に、または Teams のゲートウェイを通過する場合があります。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-355">The media may flow directly from Teams and/or the Skype for Business client to the SBC (bypassing the Teams gateway) or traverse through the Teams gateway.</span></span> <span data-ttu-id="0d0c4-356">樹幹が Teams ゲートウェイをバイパスするように構成されている場合、SBC を使った接続は氷に基づいています。 SBC は ICE をサポートしていますが、Teams/Skype for Business media endpoint は ice Full フォームをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-356">The connectivity with the SBC, when the trunk is configured to bypass the Teams gateway, is based on ICE, where SBC supports ICE-Lite, while the Teams/Skype for Business media endpoint supports ICE Full Form.</span></span>

<span data-ttu-id="0d0c4-357">[![Microsoft Teams Online の通話フロー図17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-357">[![Microsoft Teams Online Call Flows Figure 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span></span>

<span data-ttu-id="0d0c4-358">\* 図 17-電話システムのダイレクトルーティングトポロジを使用したチーム</span><span class="sxs-lookup"><span data-stu-id="0d0c4-358">\*Figure 17 - Teams with Phone System Direct Routing topology</span></span>

<span data-ttu-id="0d0c4-359">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-359">Note that:</span></span>

- <span data-ttu-id="0d0c4-360">上の図の矢印の方向は、企業境界での接続に影響を与える通信の開始方向を反映しています。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-360">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="0d0c4-361">メディア用に UDP の場合は、最初のパケットが逆方向に流れる場合がありますが、これらのパケットは、他の方向のパケットが流れるまでブロックされることがあります。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-361">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="0d0c4-362">Teams は Skype for Business Online と並行して展開されるため、クライアントは "Teams/SFB ユーザー" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-362">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user."</span></span>

<span data-ttu-id="0d0c4-363">追加のフロー (Teams online トポロジの一番上):</span><span class="sxs-lookup"><span data-stu-id="0d0c4-363">Additional flows (on top of Teams online topology):</span></span>

- <span data-ttu-id="0d0c4-364">**Flow 4 '** -Office 365 から顧客ネットワークへのフローを表します。これを使用して、お客様は、クラウドの Teams メディアサーバーと SBC オンプレミスの間の接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-364">**Flow 4'** - Represents a flow from Office 365 to the customer network, used to establish a connection between the Teams media server in the cloud with the SBC on premises.</span></span>
- <span data-ttu-id="0d0c4-365">**Flow 5b** –お客様のネットワーク内の Teams ユーザー間のメディアフローを表します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-365">**Flow 5B** – Represents a media flow between the Teams user within the customer network with the Direct Routing SBC in bypass mode.</span></span>
- <span data-ttu-id="0d0c4-366">**フロー 5c** – PSTN 転送 call バイパスモードで、ダイレクトルーティングの sbc と別のダイレクトルーティングの sbc 間のメディアフローを表します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-366">**Flow 5C** – Represents a media flow between the Direct Routing SBC to another Direct Routing SBC in a PSTN hairpin call bypass mode.</span></span>

<span data-ttu-id="0d0c4-367">**直接ルーティングを使用する内部ユーザー (Office 365 で Teams トランスポートリレーによって中継されるメディア)**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-367">**Internal user with Direct Routing (media relayed by Teams Transport Relay in Office 365)**</span></span>

<span data-ttu-id="0d0c4-368">[![Microsoft Teams Online の通話フロー図18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-368">[![Microsoft Teams Online Call Flows Figure 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span></span>

<span data-ttu-id="0d0c4-369">*図 18-直接ルーティングを使用する内部ユーザー (Office 365 で Teams トランスポートリレーによって中継されたメディア)*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-369">*Figure 18 - Internal user with Direct Routing (media relayed by Teams Transport Relay in Office 365)*</span></span>

<span data-ttu-id="0d0c4-370">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-370">Note that:</span></span>

- <span data-ttu-id="0d0c4-371">SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-371">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="0d0c4-372">SBC から Office 365 へのシグナリングおよびメディアの場合は、flow 4 または flow 4 を使います。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-372">Signaling and media from the SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="0d0c4-373">顧客ネットワーク内のクライアントから Office 365 へのシグナリングとメディアの送信は、flow 4 を使います。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-373">Signaling and media from the client within the customer network to Office 365 use flow 4.</span></span>

<span data-ttu-id="0d0c4-374">**直接ルーティングを使用するリモートユーザー (メディアは、Office 365 でメディアサーバー (MP) 経由でルーティングされます)**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-374">**Remote user with Direct Routing (media is routed through a media server (MP) in Office 365)**</span></span>

<span data-ttu-id="0d0c4-375">[![Microsoft Teams Online の通話フロー図19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-375">[![Microsoft Teams Online Call Flows Figure 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span></span>

<span data-ttu-id="0d0c4-376">*図 19-直接ルーティングを使用しているリモートユーザー (メディアは、Office 365 でメディアサーバー (MP) 経由でルーティングされます)*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-376">*Figure 19 - Remote user with Direct Routing (media is routed through a media server (MP) in Office 365)*</span></span>

<span data-ttu-id="0d0c4-377">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-377">Note that:</span></span>

- <span data-ttu-id="0d0c4-378">SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-378">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="0d0c4-379">SBC から Office 365 へのシグナリングおよびメディアの場合は、flow 4 または flow 4 を使います。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-379">Signaling and media from the SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="0d0c4-380">インターネット上のクライアントから Office 365 へのシグナリングとメディアの流れ3を使用します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-380">Signaling and media from the client on the Internet to Office 365 use flow 3.</span></span>

<span data-ttu-id="0d0c4-381">**内部ユーザー直接ルーティング (メディアバイパス)**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-381">**Internal user Direct Routing (media bypass)**</span></span>

<span data-ttu-id="0d0c4-382">[![Microsoft Teams Online の通話フロー図20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-382">[![Microsoft Teams Online Call Flows Figure 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span></span>

<span data-ttu-id="0d0c4-383">*図 20-内部ユーザー直接ルーティング (メディアバイパス)*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-383">*Figure 20 - Internal user Direct Routing (media bypass)*</span></span>

<span data-ttu-id="0d0c4-384">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-384">Note that:</span></span>

- <span data-ttu-id="0d0c4-385">SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-385">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="0d0c4-386">SBC から Office 365 およびその逆のシグナリングでは、flow 4 またはフロー4のどちらか一方または両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-386">Signaling from SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="0d0c4-387">顧客ネットワーク内のクライアントから Office 365 へのシグナリングは、flow 4 を使います。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-387">Signaling from client within the customer network to Office 365 use flow 4.</span></span>

- <span data-ttu-id="0d0c4-388">顧客ネットワーク内のクライアントから、顧客ネットワーク内の SBC までのメディア。フロー5B を使用します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-388">Media from client within the customer network to SBC within the customer network use flow 5B.</span></span>

<span data-ttu-id="0d0c4-389">**直接ルーティングを使用するリモートユーザー (Office 365 の Teams トランスポートリレーによって中継されたメディアのバイパス)**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-389">**Remote user with Direct Routing (media bypass relayed by Teams Transport Relay in Office 365)**</span></span>

<span data-ttu-id="0d0c4-390">[![Microsoft Teams Online の通話フロー図21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-390">[![Microsoft Teams Online Call Flows Figure 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span></span>

<span data-ttu-id="0d0c4-391">*図 21-直接ルーティングを使用するリモートユーザー (Office 365 の Teams トランスポートリレーによって中継されるメディア)*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-391">*Figure 21 - Remote user with Direct Routing (media bypass relayed by Teams Transport Relay in Office 365)*</span></span>

<span data-ttu-id="0d0c4-392">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-392">Note that:</span></span>

- <span data-ttu-id="0d0c4-393">SBC には、Office 365 およびインターネットからルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-393">The SBC must have a public IP address that is routable from Office 365 and Internet.</span></span>

- <span data-ttu-id="0d0c4-394">SBC から Office 365、またはその逆のシグナリングでは、flow 4 またはフロー4のいずれかまたは両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-394">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="0d0c4-395">インターネット上のクライアントから Office 365 への通知では、flow 3 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-395">Signaling from the client on the Internet to Office 365 uses flow 3.</span></span>

- <span data-ttu-id="0d0c4-396">インターネット上のクライアントからお客様のネットワーク内の SBC へのメディアは、フロー3と4を使い、Office 365 の Teams トランスポートリレーによって中継されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-396">Media from the client on the Internet to the SBC within the customer network uses flows 3 and 4, relayed by Teams Transport Relay in Office 365.</span></span>

<span data-ttu-id="0d0c4-397">**リモートユーザーの直接ルーティング (メディアバイパスダイレクト)**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-397">**Remote user Direct Routing (media bypass direct)**</span></span>

<span data-ttu-id="0d0c4-398">[![Microsoft Teams Online の通話フロー図22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-398">[![Microsoft Teams Online Call Flows Figure 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span></span>

<span data-ttu-id="0d0c4-399">*図 22-リモートユーザーの直接ルーティング (メディアバイパスダイレクト)*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-399">*Figure 22 - Remote user Direct Routing (media bypass direct)*</span></span>

<span data-ttu-id="0d0c4-400">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-400">Note that:</span></span>

- <span data-ttu-id="0d0c4-401">SBC には、Office 365 およびインターネットからルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-401">The SBC must have a public IP address that is routable from Office 365 and the Internet.</span></span>

- <span data-ttu-id="0d0c4-402">SBC から Office 365、またはその逆のシグナリングでは、flow 4 またはフロー4のいずれかまたは両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-402">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="0d0c4-403">インターネット上のクライアントから Office 365 への通知では、flow 3 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-403">Signaling from the client on the Internet to Office 365 uses flow 3.</span></span>

- <span data-ttu-id="0d0c4-404">インターネット上のクライアントから顧客ネットワーク内の SBC までのメディアは、フロー2を使用します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-404">Media from the client on the Internet to the SBC within the customer network uses flow 2.</span></span>

<span data-ttu-id="0d0c4-405">**直接ルーティング (メディアバイパス) – PSTN 転送通話 (通話転送/転送のため)**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-405">**Direct Routing (media bypass) – PSTN hairpin call (due to call forward/transfer)**</span></span>

<span data-ttu-id="0d0c4-406">[![Microsoft Teams Online の通話フロー図23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-406">[![Microsoft Teams Online Call Flows Figure 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span></span>

<span data-ttu-id="0d0c4-407">*図 23-直接ルーティング (メディアバイパス)-PSTN 転送通話 (通話転送/転送のため)*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-407">*Figure 23 - Direct Routing (media bypass) - PSTN hairpin call (due to call forward/transfer)*</span></span>

<span data-ttu-id="0d0c4-408">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-408">Note that:</span></span>

- <span data-ttu-id="0d0c4-409">SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-409">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="0d0c4-410">SBC から Office 365、またはその逆のシグナリングでは、flow 4 またはフロー4のいずれかまたは両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-410">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="0d0c4-411">クライアントは、通話が PSTN から PSTN に hairpinned された後に、シグナリングおよびメディアループを終了します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-411">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="0d0c4-412">顧客ネットワーク内の SBC インスタンス A から、顧客ネットワーク内の SBC インスタンス B へのメディア (場所 A と B は同じインスタンスである可能性があります) は、フロー5C を使用します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-412">Media from SBC instance A within the customer network to SBC instance B within the customer network (where, A and B can be the same instance) uses flow 5C.</span></span>

<span data-ttu-id="0d0c4-413">**直接ルーティング (Office 365 経由のメディア) –2つのテナント間での PSTN 転送通話**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-413">**Direct Routing (media through Office 365) – PSTN hairpin call across two tenants**</span></span>

<span data-ttu-id="0d0c4-414">[![Microsoft Teams Online の通話フロー図24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-414">[![Microsoft Teams Online Call Flows Figure 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span></span>

<span data-ttu-id="0d0c4-415">*図 24-ダイレクトルーティング (Office 365 経由のメディア) –2つのテナント間での PSTN 転送通話*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-415">*Figure 24 - Direct Routing (media through Office 365) – PSTN hairpin call across two tenants*</span></span>

<span data-ttu-id="0d0c4-416">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-416">Note that:</span></span>

- <span data-ttu-id="0d0c4-417">SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-417">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="0d0c4-418">SBC から Office 365、またはその逆のシグナリングでは、flow 4 またはフロー4のいずれかまたは両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-418">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="0d0c4-419">クライアントは、通話が PSTN から PSTN に hairpinned された後に、シグナリングおよびメディアループを終了します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-419">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="0d0c4-420">顧客ネットワーク X から SBC インスタンス B 内の SBC インスタンスからのメディアは、Office 365 メディアサーバーを通じて中継され、バイパスモードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-420">Media from SBC instance A within the customer network X to SBC instance B must be relayed through the Office 365 Media Server and can't use bypass mode.</span></span>

## <a name="teams-with-express-route-optimization"></a><span data-ttu-id="0d0c4-421">エクスプレスルートの最適化を使用しているチーム</span><span class="sxs-lookup"><span data-stu-id="0d0c4-421">Teams with Express Route optimization</span></span>

<span data-ttu-id="0d0c4-422">[![Microsoft Teams Online の通話フロー図25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-422">[![Microsoft Teams Online Call Flows Figure 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span></span>

<span data-ttu-id="0d0c4-423">*図 25-簡易ルートの最適化を使用したチーム*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-423">*Figure 25 - Teams with Express Route optimization*</span></span>

<span data-ttu-id="0d0c4-424">エクスプレスルートが両端揃えで展開されている場合、チームフローはフロー4からフロー1に、フロー4からフロー1に再ルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-424">In the case that Express Route is justified and deployed, then Teams flows could be re-routed from flow 4 to flow 1 and from flow 4' to flow 1'.</span></span> <span data-ttu-id="0d0c4-425">ただし、Teams アプリケーションは、フロー4と4を使って、インターネット経由で他の Office 365 フローに対して困難な依存関係を持っています。そのため、これらのフローはブロックしないでください。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-425">However, the Teams application has a hard dependency on other Office 365 flows over the Internet using flows 4 and 4'; hence these flows must not be blocked.</span></span>

<span data-ttu-id="0d0c4-426">Skype for Business ハイブリッドエッジトラフィックは、インターネットにルーティングされるため、外部ユーザーと通信したり、他のテナントとフェデレーションを行ったりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-426">Note that Skype for Business hybrid Edge traffic is routed to the Internet and not to Express Route to communicate with external users and federate with other tenants.</span></span>

<span data-ttu-id="0d0c4-427">非対称のフローを防ぐために、再ルーティングは両方の方向で行われる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-427">To prevent asymmetrical flows, re-routing must be in both directions.</span></span> <span data-ttu-id="0d0c4-428">つまり、顧客ネットワーク内のアドレスは、インターネットまたはエクスプレスルート (最適化に基づく) を介してルーティングされますが、両方を経由することはできません。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-428">In other words, an address within the customer network is routable either through Internet or Express Route, based on optimization, but not through both.</span></span>


<span data-ttu-id="0d0c4-429">**外部ユーザーに対する顧客ネットワーク (メディアトランスポートリレーによって中継されるメディア):**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-429">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="0d0c4-430">[![Microsoft Teams Online の通話フロー図26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span><span class="sxs-lookup"><span data-stu-id="0d0c4-430">[![Microsoft Teams Online Call Flows Figure 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span></span>

<span data-ttu-id="0d0c4-431">*図 26-外部ユーザーへの顧客ネットワーク (Teams トランスポートリレーによるメディアの中継)*</span><span class="sxs-lookup"><span data-stu-id="0d0c4-431">*Figure 26 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="0d0c4-432">**高レベルの手順:**</span><span class="sxs-lookup"><span data-stu-id="0d0c4-432">**High Level Steps:**</span></span>

1. <span data-ttu-id="0d0c4-433">顧客ネットワーク内の Teams ユーザーは、flow2 を使って URL ドメイン名 (DNS) を解決します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-433">Teams User within customer network resolves URL domain name (DNS) using flow2.</span></span>
1. <span data-ttu-id="0d0c4-434">顧客ネットワーク内の teams ユーザーは、フロー1を使用して Teams トランスポートリレーにメディアリレーポートを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-434">Teams User within customer network allocates a media Relay port on Teams Transport Relay using flow 1.</span></span>
1. <span data-ttu-id="0d0c4-435">顧客ネットワーク内の Teams ユーザーは、flow 1 から Office 365 への "招待" を、ICE 候補と共に送信します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-435">Teams User within customer network sends "invite" with ICE candidates using flow 1 to Office 365.</span></span>
1. <span data-ttu-id="0d0c4-436">Office 365 はフロー3を使って外部 Teams ユーザーに通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-436">Office 365 sends notification to external Teams user using flow 3.</span></span>
1. <span data-ttu-id="0d0c4-437">Teams の外部ユーザーは、flow 3 を使用して Teams トランスポートリレーにメディアリレーポートを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-437">Teams external user allocates a media Relay port on Teams Transport Relay using flow 3.</span></span>
1. <span data-ttu-id="0d0c4-438">Teams の外部ユーザーはフロー3を使って氷の候補で "answer" を送信します。フロー1を使って Teams ユーザー A に戻されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-438">Teams external user sends "answer" with ICE candidates using flow 3, which is forwarded back to Teams user A using Flow 1.</span></span>
1. <span data-ttu-id="0d0c4-439">Teams ユーザー A と Teams ユーザー B は、ICE 接続テストを呼び出し、フロー1と3を選択します。これは、Office 365 の Teams トランスポートリレーによって中継されます。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-439">Teams User A and Teams User B invoke ICE connectivity tests and selects flows 1 and 3, which are relayed by Teams Transport Relay in Office 365.</span></span>
1. <span data-ttu-id="0d0c4-440">Teams ユーザーは、フロー1と3を使用して、Office 365 にテレメトリを送信します。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-440">Teams Users send telemetry to Office 365 using flows 1 and 3.</span></span>

> [!NOTE]
> <span data-ttu-id="0d0c4-441">フロー4は、フロー4を設定する他のマイクロサービスで Teams アプリケーションの依存関係をサポートするために有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d0c4-441">Flow 4 must be enabled to support dependencies of Teams application on other micro-services that mandates flow 4.</span></span>
