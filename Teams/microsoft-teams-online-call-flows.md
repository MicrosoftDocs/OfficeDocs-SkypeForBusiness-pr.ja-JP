---
title: Microsoft Teams の通話フロー
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 06/08/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
description: Teams で Office 365 のフローがさまざまなトポロジで使用される方法について説明します。
ms.openlocfilehash: ecdeb6dc4e1e7219dc8c01c710877437661e0ceb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232160"
---
# <a name="microsoft-teams-call-flows"></a><span data-ttu-id="b9472-103">Microsoft Teams の通話フロー</span><span class="sxs-lookup"><span data-stu-id="b9472-103">Microsoft Teams call flows</span></span>

> [!Tip]
> <span data-ttu-id="b9472-104">Teams でのネットワークの活用方法と最適なネットワーク接続を計画する方法については、次のセッションをご覧ください: [Teams のネットワーク計画](https://aka.ms/teams-networking)</span><span class="sxs-lookup"><span data-stu-id="b9472-104">Watch the following session to learn how Teams leverages your network and how to plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking)</span></span>

## <a name="overview"></a><span data-ttu-id="b9472-105">概要</span><span class="sxs-lookup"><span data-stu-id="b9472-105">Overview</span></span>
<span data-ttu-id="b9472-106">この記事では、Teams で Office 365 の通話フローがさまざまなトポロジで使用される方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9472-106">This article describes how Teams uses Office 365 call flows in various topologies.</span></span> <span data-ttu-id="b9472-107">また、ピアツーピアのメディア コミュニケーションで使用される固有の Teams のフローについても説明します。</span><span class="sxs-lookup"><span data-stu-id="b9472-107">In addition, it describes unique Teams flows that are used for peer-to-peer media communication.</span></span> <span data-ttu-id="b9472-108">この記事では、これらのフロー、その目的、ネットワーク上でのフローの始端と終端について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9472-108">The document describes these flows, their purpose, and their origin and termination on the network.</span></span> <span data-ttu-id="b9472-109">この記事では次のことを想定しています。</span><span class="sxs-lookup"><span data-stu-id="b9472-109">For purposes of this article, assume the following:</span></span>

- <span data-ttu-id="b9472-110">Flow X は、オンプレミスの Office 365 クライアントがクラウドの Office 365 サービスと通信するために使用します。</span><span class="sxs-lookup"><span data-stu-id="b9472-110">Flow X is used by the on-premises Office 365 client to communicate with the Office 365 service in the cloud.</span></span> <span data-ttu-id="b9472-111">これは、顧客ネットワークが始端となり、Office 365 のエンドポイントとして終端します。</span><span class="sxs-lookup"><span data-stu-id="b9472-111">It originates from the customer network, and it terminates as an endpoint in Office 365.</span></span>

- <span data-ttu-id="b9472-112">フロー Y は、Office 365 が依存しているインターネット上のサービスと通信するためにオンプレミスの Office 365 クライアントによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-112">Flow Y is used by the on-premises Office 365 client to communicate with a service on the Internet that Office 365 has a dependency on.</span></span> <span data-ttu-id="b9472-113">これは、顧客ネットワークが始端となり、インターネットのエンドポイントとして終端します。</span><span class="sxs-lookup"><span data-stu-id="b9472-113">It originates from the customer network, and it terminates as an endpoint on the Internet.</span></span>

<span data-ttu-id="b9472-114">このトピックには次のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9472-114">The usage model contains the following sections.</span></span>

- <span data-ttu-id="b9472-115">**背景** - Office 365 フローが通過する可能性があるネットワーク、トラフィックの種類、顧客のネットワークから Office 365 のサービス エンドポイントへの接続に関するガイダンス、サードパーティ製のコンポーネントとの相互運用性、Teams がメディア フローの選択に使用する原則などの背景情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b9472-115">**Background** - Provides background information, such as networks that Office 365 flows may traverse, type of traffic, connectivity guidance from the customer network to Office 365 service endpoints, interoperability with third-party components, and principles that are used by Teams to select media flows.</span></span>

- <span data-ttu-id="b9472-116">**さまざまなトポロジでの通話フロー** - さまざまなトポロジでの通話フローの使用例を示します。</span><span class="sxs-lookup"><span data-stu-id="b9472-116">**Call flows in various topologies** - Illustrates the use of call flows in various topologies.</span></span> <span data-ttu-id="b9472-117">このセクションでは、各トポロジについて、サポートされるすべてのフローを列挙し、これらのフローの使用方法をいくつかのユース ケースを使って示します。</span><span class="sxs-lookup"><span data-stu-id="b9472-117">For each topology, the section enumerates all supported flows and illustrates how these flows are used via several use cases.</span></span> <span data-ttu-id="b9472-118">各ユース ケースについて、フローの順序とセクションをフローの図を用いて示します。</span><span class="sxs-lookup"><span data-stu-id="b9472-118">For each use case, it describes the sequence and selection of flows via a flow diagram.</span></span> 

- <span data-ttu-id="b9472-119">**Express Route による Teams の最適化** - 最適化のために Express Route が展開された場合にこれらのフローがどのように使用されるかを、単純なトポロジを用いて説明します。</span><span class="sxs-lookup"><span data-stu-id="b9472-119">**Teams with Express Route optimization** - Describes how these flows are used when Express Route is deployed for optimization, illustrated via a simple topology.</span></span>

## <a name="background"></a><span data-ttu-id="b9472-120">背景</span><span class="sxs-lookup"><span data-stu-id="b9472-120">Background</span></span>
### <a name="network-segments"></a><span data-ttu-id="b9472-121">ネットワーク セグメント</span><span class="sxs-lookup"><span data-stu-id="b9472-121">Network Segments</span></span>
<span data-ttu-id="b9472-122">**顧客ネットワーク**: これは、管理者が制御および管理するネットワーク セグメントです。</span><span class="sxs-lookup"><span data-stu-id="b9472-122">**Your network** This is the network segment that is part of your overall network that you control and manage.</span></span> <span data-ttu-id="b9472-123">これには、顧客のオフィス内の有線または無線によるすべての顧客の接続、オフィスビル間の接続、オンプレミス データセンターへの接続に加え、インターネット プロバイダー、ExpressRoute、またはプライベート ピアリングへの接続が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9472-123">This includes all of your connections within your offices, whether wired or wireless, between office buildings, to on-premises datacenters, and your connections to Internet providers or ExpressRoute partners.</span></span> 

<span data-ttu-id="b9472-124">通常、顧客ネットワークには、ファイアウォールおよび/またはプロキシサーバーを使用して組織のセキュリティポリシーを適用するネットワーク境界が複数あり、設定と構成を行った特定のネットワーク トラフィックのみが許可されるようになっています。</span><span class="sxs-lookup"><span data-stu-id="b9472-124">Typically, a customer network has several network perimeters with firewalls and/or proxy servers, which enforce your organization's security policies, and that only allow certain network traffic that you have set up and configured.</span></span> <span data-ttu-id="b9472-125">このネットワークの管理を行うのは管理者であるため、管理者はネットワークのパフォーマンスを直接管理できます。ネットワーク上のサイトとネットワークから Office 365 ネットワークの接続の両方のパフォーマンスについて、ネットワーク評価を行うことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b9472-125">Because you manage this network, you have direct control over the performance of the network, and it is highly recommended that you complete network assessments to validate performance both within sites in your network and from your network to the Office 365 network.</span></span> 

<span data-ttu-id="b9472-126">**インターネット**: これはネットワーク全体の一部で、顧客ネットワークの外部から Office 365 に接続するユーザーによって使用されるネットワーク セグメント。</span><span class="sxs-lookup"><span data-stu-id="b9472-126">**Internet** This is the network segment that is part of your overall network that will be used by users who are connecting to Skype for Business Online from outside of your network, and is used for all connections when ExpressRoute isn't configured.</span></span> <span data-ttu-id="b9472-127">また、顧客ネットワークから Office 365 への一部のトラフィックにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-127">It is also used by some traffic from the customer network to Office 365.</span></span> 

<span data-ttu-id="b9472-128">**訪問先 / ゲスト ネットワーク**: 顧客ネットワークの外部にある、ユーザーおよび/またはそれらのユーザーのゲストが訪問することができるネットワーク セグメントで、公衆インターネットには含まれません。</span><span class="sxs-lookup"><span data-stu-id="b9472-128">**Visited/Guest private network**: This is the network segment outside your customer network, but not in the public Internet, that your users and/or their guests may visit.</span></span> <span data-ttu-id="b9472-129">たとえば、Teams のサービスを操作するユーザーおよび/またはそれらのユーザーの顧客が利用する、Teams が展開されていない家庭のプライベート ネットワークや企業のプライベート ネットワークなどを含みます。</span><span class="sxs-lookup"><span data-stu-id="b9472-129">For example, home private network or an Enterprise private network, that does not deploy Teams, where your users and/or their customers that interact with Teams services may reside.</span></span>

><span data-ttu-id="b9472-130">**注**: Office 365 への接続は、これらのネットワークにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-130">**Note**: Connectivity to Office 365 is also applicable to these networks.</span></span>

<span data-ttu-id="b9472-131">**Office 365**: これは、Office 365 サービスをサポートするネットワーク セグメントです。</span><span class="sxs-lookup"><span data-stu-id="b9472-131">**Office 365**: This is the network segment that supports Office 365 services.</span></span> <span data-ttu-id="b9472-132">これは世界中に分散しているネットワークで、ほとんどの場所で顧客ネットワークに近接するエッジを使用しています。</span><span class="sxs-lookup"><span data-stu-id="b9472-132">It is distributed worldwide with edges in proximity to the customer network in most locations.</span></span> <span data-ttu-id="b9472-133">この記事で取り扱う機能には、トランスポート リレー、会議サーバー、メディア プロセッサが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9472-133">Functions mentioned in this document include Transport Relay, conferencing server, and Media Processor.</span></span> 

<span data-ttu-id="b9472-134">**Express Route (オプション)**: これはネットワーク全体の一部で、Office 365 ネットワークへの専用のプライベート接続を提供するネットワーク セグメントです。</span><span class="sxs-lookup"><span data-stu-id="b9472-134">**Express Route (optional)**: This is the network segment that is part of your overall network that will give you a dedicated, private connection to the Office 365 network.</span></span>

### <a name="types-of-traffic"></a><span data-ttu-id="b9472-135">トラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="b9472-135">Types of traffic</span></span>

<span data-ttu-id="b9472-136">**リアルタイム メディア**: オーディオ、ビデオ、および画面共有のワークロードをサポートする RTP (リアルタイム転送プロトコル) 内にカプセル化されたデータ。</span><span class="sxs-lookup"><span data-stu-id="b9472-136">**Real-time media**: Data encapsulated within RTP (Real-time Transport Protocol) that supports audio, video and screen sharing workloads.</span></span> <span data-ttu-id="b9472-137">一般的に、メディア トラッフィックは遅延に対して非常に敏感なため、このトラフィックはできるだけ直接的な経路を使用し、トランスポート層プロトコルとして TCP ではなく、品質の点で対話的なリアルタイム メディアには最良のトランスポートである UDP を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9472-137">In general, media traffic is highly latency sensitive, so you would want this traffic to take the most direct path possible, and to use UDP versus TCP as the transport layer protocol, which is the best transport for interactive real time media from a quality perspective.</span></span> <span data-ttu-id="b9472-138">(注: 最後の手段として、メディアには TCP/IP を使用し、HTTP プロトコル内でトンネリングすることができますが、品質に悪影響を与える可能性があるため、お勧めできません)。RTP フローは SRTP を介して保護され、ペイロードのみが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-138">(Note: As a last resort, media can use TCP/IP and also be tunneled within the HTTP protocol, but it is not recommended due to bad quality implications.) RTP flow is secured via SRTP, in which only the payload is encrypted.</span></span>

<span data-ttu-id="b9472-139">**シグナリング**: クライアントとサーバーまたはその他のクライアントとの間の通信リンクで、アクティビティ (たとえば、通話が開始された場合など) の制御とインスタント メッセージの配信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-139">**Signaling**: The communication link between the client and server, or other clients that are used to control activities (for example, when a call is initiated), and deliver instant messages.</span></span> <span data-ttu-id="b9472-140">ほとんどのシグナリング トラフィックは HTTPS ベースの REST インターフェイスを使用しますが、一部の シナリオ (Office 365 とセッション ボーダー コントローラーの間の接続など) では、SIP プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="b9472-140">Most signaling traffic uses the HTTPS-based REST interfaces, though in some scenarios (for example, connection between Office 365 and a Session Border Controller) it uses SIP protocol.</span></span> <span data-ttu-id="b9472-141">このトラフィックは遅延に対してあまり敏感ではありませんが、エンドポイント間に数秒を超える遅延があった場合、サービス停止や通話のタイムアウトが発生する可能性がある点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="b9472-141">It's important to understand that this traffic is much less sensitive to latency but may cause service outages or call timeouts if latency between the endpoints exceeds several seconds.</span></span> 

### <a name="connectivity-to-office-365"></a><span data-ttu-id="b9472-142">Office 365 への接続</span><span class="sxs-lookup"><span data-stu-id="b9472-142">Connectivity to Office 365</span></span>

<span data-ttu-id="b9472-143">Teams を使用するには、[インターネットへの接続が必要です](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10)。</span><span class="sxs-lookup"><span data-stu-id="b9472-143">Teams requires [connectivity to the Internet](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10).</span></span> <span data-ttu-id="b9472-144">Teams のエンドポイントの URL と IP アドレスの範囲は、「[Office 365 の URL と IP アドレスの範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="b9472-144">Teams endpoint URLs and IP address ranges are listed in [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> <span data-ttu-id="b9472-145">(注: TCP ポート 80 および 443、UDP ポート 3478〜3481 へのオープン接続が必要です。) さらに、Teams は Skype for Business Online に依存しているため、Skype for Business Online もインターネットに接続されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9472-145">(Note: Open connectivity to TCP ports 80 and 443, and to UDP ports 3478 through 3481 is required.) Furthermore, Teams has a dependency on Skype for Business Online, which must also be connected to the Internet.</span></span>

<span data-ttu-id="b9472-146">Teams のメディア フロー接続は、標準の IETF ICE (Interactive Connectivity Establishment) の手順を通して実装されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-146">Teams media flows connectivity is implemented via standard IETF ICE (Interactive Connectivity Establishment) procedures.</span></span>

### <a name="interoperability-restrictions"></a><span data-ttu-id="b9472-147">相互運用性の制限</span><span class="sxs-lookup"><span data-stu-id="b9472-147">Interoperability restrictions</span></span>
<span data-ttu-id="b9472-148">**サードパーティのメディア リレー**: Teams のメディア フロー (つまり、いずれかのメディア エンドポイントが Teams である場合) は、Teams または Skype for Business のネイティブ メディア リレーのみを通過できます。</span><span class="sxs-lookup"><span data-stu-id="b9472-148">**Third party media relays**: A Teams media flow (that is, one of the media endpoints is Teams) may traverse only Teams or Skype for Business native media relays.</span></span> <span data-ttu-id="b9472-149">サードパーティ製メディア リレーとの相互運用性は、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b9472-149">Interoperability with a third party media relay is not supported.</span></span> <span data-ttu-id="b9472-150">(注: PSTN との境界にあるサードパーティの SBC は、RTP/RTCP ストリーム を終了し、SRTP を介して保護されている必要があり、次のホップにリレーさせることはできません)。</span><span class="sxs-lookup"><span data-stu-id="b9472-150">(Note: A third party SBC on the boundary with PSTN must terminate RTP/RTCP stream, secured via SRTP, and not relay it to the next hop.)</span></span>

<span data-ttu-id="b9472-151">**サードパーティの SIP プロキシ サーバー**: サードパーティの SBC および/またはゲートウェイを使用する Teams のシグナリング SIP ダイアログは、 Teams または Skype for Business のネイティブ SIP プロキシを通過できます。</span><span class="sxs-lookup"><span data-stu-id="b9472-151">**Third party SIP proxy servers**: A Teams signaling SIP dialog with a third party SBC and/or gateway may traverse Teams or Skype for Business native SIP proxies.</span></span> <span data-ttu-id="b9472-152">サードパーティ製 SIP プロキシとの相互運用性は、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b9472-152">Interoperability with a third party SIP proxy is not supported.</span></span>

<span data-ttu-id="b9472-153">**サードパーティの B2BUA (つまり、SBC)**: PSTN との間の Teams のメディア フローは、サードパーティの SBC により終端されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-153">**Third party B2BUA (that is, SBC)**: A Teams media flow from/to the PSTN is terminated by a third party SBC.</span></span> <span data-ttu-id="b9472-154">ただし、Teams ネットワーク内のサードパーティーの SBC との相互運用性 (つまり、サードパーティの SBC が Teams と Skype for Business の 2 つのエンドポイントを仲介) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b9472-154">However, interoperability with a third party SBC within the Teams network (that is, a third party SBC mediates two Teams/Skype for Business endpoints) is not supported.</span></span>

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a><span data-ttu-id="b9472-155">Microsoft Teams で推奨されないテクノロジ</span><span class="sxs-lookup"><span data-stu-id="b9472-155">Technologies that are not recommended with Microsoft Teams</span></span>

<span data-ttu-id="b9472-156">**VPN ネットワーク**: メディア トラフィック (フロー 2 に該当) に使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="b9472-156">**VPN network**: It is not recommended for media traffic (that is, flow 2').</span></span> <span data-ttu-id="b9472-157">https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/ で指定されるように、VPN クライアントはスプリット VPN を使用し、外部の 非 VPN ユーザーなどのメディア トラフィックをルーティングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9472-157">The VPN client should use split VPN and route media traffic like any external non-VPN user, as specified in https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/.</span></span>

><span data-ttu-id="b9472-158">**注**: 題名は Lync となっていますが、Teams にも適用できます。</span><span class="sxs-lookup"><span data-stu-id="b9472-158">**Note**: Although the title is Lync, it is applicable to Teams as well.</span></span>

<span data-ttu-id="b9472-159">**パケット シェーパー**: あらゆる種類のパケット スニッパー、パケット検査、またはパケット シェーパーのデバイスの使用はお勧めしません。品質が大きく低下する場合があります。</span><span class="sxs-lookup"><span data-stu-id="b9472-159">**Packet shapers**: Any kind of packet snippers, packet inspection, or packet shaper devices are not recommended and may degrade quality significantly.</span></span> 

### <a name="principles"></a><span data-ttu-id="b9472-160">原則</span><span class="sxs-lookup"><span data-stu-id="b9472-160">Principles</span></span>
<span data-ttu-id="b9472-161">Microsoft Teams の通話フローを理解するのに役立つ、4つの一般的な原則があります。</span><span class="sxs-lookup"><span data-stu-id="b9472-161">There are four general principles that help you understand call flows for Microsoft Teams:</span></span>
 
1.  <span data-ttu-id="b9472-162">Microsoft Teams の会議は、最初の参加者が参加したのと同じ地域の Office 365 によってホストされます。</span><span class="sxs-lookup"><span data-stu-id="b9472-162">A Microsoft Teams conference is hosted by Office 365 in the same region where the first participant joined.</span></span> <span data-ttu-id="b9472-163">(注: トポロジによってこのルールの例外が発生する場合については、記事で説明します。適切な通話フローも示されます。)</span><span class="sxs-lookup"><span data-stu-id="b9472-163">(Note: If there will be exceptions to this rule in some topologies, then they will be described in this document, and illustrated by an appropriate call flow.)</span></span>

2.  <span data-ttu-id="b9472-164">Office 365 の Teams メディア エンドポイントは、通話の種類に基づいてではなく、メディア処理のニーズに基づいて使用されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-164">A Teams media endpoint in Office 365 is used based on media processing needs and not based on call type.</span></span> <span data-ttu-id="b9472-165">(たとえば、ポイントツーポイントの通話では、トランスクリプションおよび/または録音のためのメディア処理に、クラウド内のメディア エンドポイントを使用する場合がありますが、参加者が 2 人の会議ではクラウド内のメディア エンドポイントを使用しない場合があります。) ただし、ほとんどの会議では、ミキシングおよびルーティングのために、会議がホストされる場所に割り当てられているメディア エンドポイントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-165">(For example, a point-to-point call may use a media endpoint in the cloud to process media for transcription and/or recording, while a conference with two participants may not use any media endpoint in the cloud.) However, most conferences will use a media endpoint for mixing and routing purposes, allocated where the conference is hosted.</span></span> <span data-ttu-id="b9472-166">クライアントからメディア エンドポイントに送信されるメディア トラフィックは、直接ルーティングされる場合と、顧客ネットワークのファイアウォール制限のために必要な場合は、Office 365 のトランスポート リレーを使用する場合とがあります。</span><span class="sxs-lookup"><span data-stu-id="b9472-166">The media traffic sent from a client to the media endpoint may be routed directly or use a Transport Relay in Office 365 if required due to customer network firewall restrictions.</span></span> 

3.  <span data-ttu-id="b9472-167">ピアツーピア通話のメディア トラフィックは、通話でクラウド内のメディア エンドポイントが要求されていない限り (上の項目 2 を参照)、使用できる最も直接的なルートを使用します。</span><span class="sxs-lookup"><span data-stu-id="b9472-167">Media traffic for peer-to-peer calls take the most direct route that is available, assuming that the call doesn't mandate a media endpoint in the cloud (see #2 above).</span></span> <span data-ttu-id="b9472-168">リモート ピア (クライアント) への直接のルートが優先されますが、このルートが利用できない場合は、1 つまたは複数のトランスポート リレーがトラフィックを中継します。</span><span class="sxs-lookup"><span data-stu-id="b9472-168">The preferred route is direct to the remote peer (client), but if that route isn't available due to firewall blocking the traffic or something like that, then one or more Edge servers will relay traffic.</span></span> <span data-ttu-id="b9472-169">メディアの品質に影響を与えるため、メディア トラフィックがパケット シェーパーや VPN サーバーなどのサーバーを通過しないことが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-169">It is recommended that media traffic shall not transverse servers such as packet shapers, VPN servers, and so on, since this will impact the media quality.</span></span>

4.  <span data-ttu-id="b9472-170">シグナリング トラフィックは、常にユーザーに最も近いサーバーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-170">Signaling traffic always goes to the closest server to the user.</span></span> 

<span data-ttu-id="b9472-171">選択されるメディア パスの詳細については、「https://www.youtube.com/watch?v=1tmHMIlAQdo」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9472-171">To learn more about the details on the media path that is chosen, please see https://www.youtube.com/watch?v=1tmHMIlAQdo.</span></span>

## <a name="call-flows-in-various-topologies"></a><span data-ttu-id="b9472-172">さまざまなトポロジにおける通話フロー</span><span class="sxs-lookup"><span data-stu-id="b9472-172">Call flows in various topologies</span></span>
### <a name="teams-topology"></a><span data-ttu-id="b9472-173">Teams のトポロジ</span><span class="sxs-lookup"><span data-stu-id="b9472-173">Teams topology</span></span>
<span data-ttu-id="b9472-174">このトポロジは、Skype for Business Server や電話システムのダイレクト ルーティングなどのオンプレミスの展開がない状態でクラウドから Teams のサービスを利用するお客様に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-174">This topology is used by customers that leverage Teams services from the cloud without any on-premises deployment, such as Skype for Business Server or Phone System Direct Routing.</span></span> <span data-ttu-id="b9472-175">また、Office 365 のインターフェイスは、Azure Express Route を使用せずにインターネット経由で実行されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-175">In addition, the interface to Office 365 is done via the Internet without Azure Express Route.</span></span> 

<span data-ttu-id="b9472-176">[![Microsoft Teams オンライン通話フロー 図 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-176">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span></span>

<span data-ttu-id="b9472-177">*図 1 - Teams のトポロジ*</span><span class="sxs-lookup"><span data-stu-id="b9472-177">*Figure 1 - Teams topology*</span></span>

<span data-ttu-id="b9472-178">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b9472-178">Note that:</span></span>

- <span data-ttu-id="b9472-179">上の図の矢印の方向は、エンタープライズ境界での接続に影響を与える、通信の開始方向を反映します。</span><span class="sxs-lookup"><span data-stu-id="b9472-179">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="b9472-180">メディアの UDP については、最初のパケットは逆方向に流れる場合がありますが、これらのパケットは、別の方向へのパケットが流れるまでブロックされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b9472-180">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>
- <span data-ttu-id="b9472-181">Teams は、Skype for Business Online と並行して展開されます。そのため、クライアントは "Teams/SFB ユーザー" として表示されています。</span><span class="sxs-lookup"><span data-stu-id="b9472-181">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user".</span></span>

<span data-ttu-id="b9472-182">次のオプションのトポロジの詳細については、この記事の後の方で説明します。</span><span class="sxs-lookup"><span data-stu-id="b9472-182">You can find more information on the following optional topologies later in the article:</span></span>

- <span data-ttu-id="b9472-183">Skype for Business のオンプレミスの展開については、「**Teams ハイブリッド トポロジ**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9472-183">Skype for Business on-premises deployment is described in **Teams  hybrid topology**.</span></span>
- <span data-ttu-id="b9472-184">電話システムのダイレクト ルーティング (PSTN 接続用) については、「**電話システムのダイレクト ルーティングを使用する Teams のトポロジ**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9472-184">Phone System Direct Routing (for PSTN connectivity) is described in **Teams with Direct Routing topology**.</span></span>
- <span data-ttu-id="b9472-185">Express Route については、「**Express Route による Teams の最適化**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9472-185">Express Route is described in  **Teams with Express Route optimization**.</span></span>

<span data-ttu-id="b9472-186">**フローの説明**</span><span class="sxs-lookup"><span data-stu-id="b9472-186">**Flow descriptions**:</span></span>
- <span data-ttu-id="b9472-187">**フロー 2** – ユーザーが、Teams の操作の一部として顧客ネットワーク上で開始するインターネットへのフローを表します。</span><span class="sxs-lookup"><span data-stu-id="b9472-187">**Flow 2** – Represents a flow initiated by a user on the customer network to the Internet as a part of the user's Teams experience.</span></span> <span data-ttu-id="b9472-188">この種類のフローの例は、DNS とピアツーピア メディアです。</span><span class="sxs-lookup"><span data-stu-id="b9472-188">Examples of these flows are DNS and peer-to-peer media.</span></span>
- <span data-ttu-id="b9472-189">**フロー 2'** – Teams のリモート モバイル ユーザーが VPN を使用して開始する顧客ネットワークへフローを表します。</span><span class="sxs-lookup"><span data-stu-id="b9472-189">**Flow 2'** – Represents a flow initiated by a remote mobile Teams user, with VPN to the customer network.</span></span> 
- <span data-ttu-id="b9472-190">**フロー 3** – Teams のリモート モバイル ユーザーが開始する Office 365/Teams のエンドポイントへのフローを表します。</span><span class="sxs-lookup"><span data-stu-id="b9472-190">**Flow 3** – Represents a flow initiated by a remote mobile Teams user to Office 365/Teams endpoints.</span></span> 
- <span data-ttu-id="b9472-191">**フロー 4** – 顧客ネットワーク上のユーザーが開始する Office 365/Teams のエンドポイントへのフローを表します。</span><span class="sxs-lookup"><span data-stu-id="b9472-191">**Flow 4** – Represents a flow initiated by a user on the customer network to Office 365/Teams endpoints.</span></span>
- <span data-ttu-id="b9472-192">**フロー 5** – Teams ユーザーと別の Teams ユーザーまたは顧客ネットワーク内の Skype for Business ユーザーの間のピアツーピア メディア フローを表します。</span><span class="sxs-lookup"><span data-stu-id="b9472-192">**Flow 5** – Represents a peer-to-peer media flow between a Teams user and another Teams or Skype for Business user within the customer network.</span></span>
- <span data-ttu-id="b9472-193">**フロー 6** – Teams のリモート モバイル ユーザーと別の Teams のリモート モバイル ユーザーまたは Skype for Business ユーザーの間の、インターネットを介したピアツーピア メディア フローを表します。</span><span class="sxs-lookup"><span data-stu-id="b9472-193">**Flow 6** – Represents a peer-to-peer media flow between a remote mobile Teams user and another remote mobile Teams or Skype for Business user over the Internet.</span></span>

#### <a name="use-case-one-to-one"></a><span data-ttu-id="b9472-194">ユース ケース: 一対一</span><span class="sxs-lookup"><span data-stu-id="b9472-194">Use case: One-to-one</span></span>
<span data-ttu-id="b9472-195">一対一の通話では共通のモデルが使用され、発信者は、ローカル、リレー、および再帰 (リレーから見える、クライアントのパブリック IP アドレス) の候補を含む、IP アドレス/ポートから成る候補のセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="b9472-195">One-to-one calls use a common model in which the caller will obtain a set of candidates consisting of IP addresses/ports--including local, relay, and reflexive (public IP address of client as seen by the relay) candidates.</span></span> <span data-ttu-id="b9472-196">発信者は、これらの候補を通話相手に送信します。通話を受けた相手は、同様の候補のセットを取得し、それを発信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="b9472-196">The caller sends these candidates to the called party; the called party also obtains a similar set of candidates and sends them to the caller.</span></span> <span data-ttu-id="b9472-197">STUN 接続確認メッセージは、発信者/受信者のメディア パスはどれが機能しているかを判断し、機能しているパスの中から最適のもの選択します。</span><span class="sxs-lookup"><span data-stu-id="b9472-197">STUN connectivity check messages are used to find which caller/called party media paths work, and the best working path is selected.</span></span> <span data-ttu-id="b9472-198">その後、選択された候補のペアを使用してメディア (つまり、SRTP を介して保護された RTP/RTCP パケット) が送信されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-198">Media (that is, RTP/RTCP packets secured via SRTP) are then sent using the selected candidate pair.</span></span> <span data-ttu-id="b9472-199">トランスポートリレーは、 Office 365 の一部として展開されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-199">The Transport relay is deployed as part of Office 365.</span></span>

<span data-ttu-id="b9472-200">ローカル IP アドレス/ポートの候補または再帰候補に接続がある場合、クライアント間のダイレクト パス (または NAT 経由) がメディア用に選択されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-200">If the local IP address/port candidates or the reflexive candidates have connectivity, then the direct path between the clients (or via a NAT) will be selected for media.</span></span> <span data-ttu-id="b9472-201">クライアントが両方とも顧客ネットワーク上にいる場合は、ダイレクト パスが選択されるはずです。</span><span class="sxs-lookup"><span data-stu-id="b9472-201">If the clients are both on the customer network, then the direct path should be selected.</span></span> <span data-ttu-id="b9472-202">これには、顧客ネットワーク内での UDP への直接接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="b9472-202">This requires direct UDP connectivity within the customer network.</span></span> <span data-ttu-id="b9472-203">クライアントが両方とも Nomadic Crowd のユーザーである場合、NAT/ファイアウォールによっては、メディアは直接接続を使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b9472-203">If the clients are both nomadic cloud users, then depending on the NAT/firewall, media may use direct connectivity.</span></span>

<span data-ttu-id="b9472-204">一方のクライアントが顧客ネットワーク内にいて、もう一方のクライアントが外部にいる (モバイル クラウド ユーザーなど) 場合、ローカル候補と再帰候補の間の直接接続は正常に機能しません。</span><span class="sxs-lookup"><span data-stu-id="b9472-204">If one client is internal on the customer network and one client is external (for example, a mobile cloud user), then it is unlikely that direct connectivity between the local or reflexive candidates is working.</span></span> <span data-ttu-id="b9472-205">この場合、どちらかのクライアントが、トランスポート リレー候補のいずれかを使用するというオプションがあります (たとえば、内部のクライアントが Office 365 のトランスポート リレーからリレー候補を取得した場合は、外部のクライアントは STUN/RTP/RTCP パケットをトランスポート リレーに送信できる必要があります)。</span><span class="sxs-lookup"><span data-stu-id="b9472-205">In this case, an option is to use one of the Transport Relay candidates from either client (for example, the internal client obtained a relay candidate from the Transport relay in Office 365; the external client needs to be able to send STUN/RTP/RTCP packets to the transport relay).</span></span> <span data-ttu-id="b9472-206">別のオプションとして、内部のクライアントが、モバイル クラウド クライアントが取得したリレー候補に送信するというものです。</span><span class="sxs-lookup"><span data-stu-id="b9472-206">Another option is the internal client sends to the relay candidate obtained by the mobile cloud client.</span></span> <span data-ttu-id="b9472-207">メディアの場合は UDP 接続を強く推奨しますが、TCP もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b9472-207">Note that, although UDP connectivity for media is highly recommended, TCP is supported.</span></span>

<span data-ttu-id="b9472-208">**大まかな手順**:</span><span class="sxs-lookup"><span data-stu-id="b9472-208">**High-level steps**:</span></span>
1. <span data-ttu-id="b9472-209">Teams ユーザー A が、フロー 2 経由で URL ドメイン名 (DNS) を解決します。</span><span class="sxs-lookup"><span data-stu-id="b9472-209">Teams User A resolves URL domain name (DNS) via flow2</span></span>
2. <span data-ttu-id="b9472-210">Teams ユーザー A が、フロー 4 経由で Teams トランスポート リレーでメディア リレー ポートを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b9472-210">Teams User A allocates a media Relay port on Teams Transport Relay via flow 4</span></span>
3. <span data-ttu-id="b9472-211">Teams ユーザー A が、フロー 4 経由で "招待状" を ICE 候補と共に Office 365 に送信します。</span><span class="sxs-lookup"><span data-stu-id="b9472-211">Teams User A sends "invite" with ICE candidates via flow 4 to Office 365</span></span>
4. <span data-ttu-id="b9472-212">Office 365 が、フロー 4 経由で Teams ユーザー B に通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="b9472-212">Office 365 sends notification to Teams User B via flow 4</span></span>
5. <span data-ttu-id="b9472-213">Teams ユーザー B が、フロー 4 経由で Teams トランスポート リレーでメディア リレー ポートを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b9472-213">Teams User B allocates a media Relay port on Teams Transport Relay via flow 4</span></span>
6. <span data-ttu-id="b9472-214">Teams ユーザー B が、フロー 4 経由で "回答" を ICE 候補と共に送信し、これはフロー 4 経由で Teams ユーザー A に再び転送されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-214">Teams User B sends "answer" with ICE candidates via flow 4, which is forwarded back to Teams User A via Flow 4</span></span>
7. <span data-ttu-id="b9472-215">Teams ユーザー A および Teams ユーザー B が ICE 接続テストを実行し、最適なメディア パスが選択されます (下の図でさまざまなユース ケースをご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="b9472-215">Teams User A and Teams User B invoke ICE connectivity tests and the best available media path is selected (see diagrams below for various use cases)</span></span>
8. <span data-ttu-id="b9472-216">Teams ユーザーが、フロー4 経由でテレメトリを Office 365 に送信します。</span><span class="sxs-lookup"><span data-stu-id="b9472-216">Teams Users send telemetry to Office 365 via flow 4</span></span>

<span data-ttu-id="b9472-217">**顧客ネットワーク内:**</span><span class="sxs-lookup"><span data-stu-id="b9472-217">**Within customer network:**</span></span>

<span data-ttu-id="b9472-218">[![Microsoft Teams オンライン通話フロー 図 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-218">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span></span>

<span data-ttu-id="b9472-219">*図 2 - 顧客ネットワーク内*</span><span class="sxs-lookup"><span data-stu-id="b9472-219">*Figure 2 - Within customer network*</span></span>
 
<span data-ttu-id="b9472-220">手順 7 では、ピアツーピア メディア フロー 5 が選択されています。</span><span class="sxs-lookup"><span data-stu-id="b9472-220">In step 7, peer-to-peer media flow 5 is selected.</span></span>
 
<span data-ttu-id="b9472-221">メディアは双方向です。</span><span class="sxs-lookup"><span data-stu-id="b9472-221">Media is bidirectional.</span></span> <span data-ttu-id="b9472-222">フロー 5 の方向は、この記事のすべてのフローの場合と同様、一方が通信を開始したことを接続の観点から示します。</span><span class="sxs-lookup"><span data-stu-id="b9472-222">The direction of flow 5 indicates that one side initiates the communication from a connectivity perspective, consistent with all the flows in this document.</span></span> <span data-ttu-id="b9472-223">このケースでは両方のエンドポイントが顧客ネットワーク内にあるため、使用されている方向を考慮する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="b9472-223">In this case, it doesn't matter which direction is used because both endpoints are within the customer network.</span></span>

<span data-ttu-id="b9472-224">**顧客ネットワークから外部ユーザーへ (メディアは Teams トランスポート リレーが中継):**</span><span class="sxs-lookup"><span data-stu-id="b9472-224">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="b9472-225">[![Microsoft Teams オンライン通話フロー 図 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-225">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span></span>

<span data-ttu-id="b9472-226">*図 3 - 顧客ネットワークから外部ユーザーへ (メディアは Teams トランスポート リレーが中継):*</span><span class="sxs-lookup"><span data-stu-id="b9472-226">*Figure 3 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>
 
<span data-ttu-id="b9472-227">手順 7 では、フロー 4 (顧客ネットワークから Office 365) とフロー 3 (Teams リモート モバイル ユーザーから Office 365) が選択されています。</span><span class="sxs-lookup"><span data-stu-id="b9472-227">In step 7, flow 4, from customer network to Office 365, and flow 3, from remote mobile Teams user to Office 365, are selected.</span></span> <span data-ttu-id="b9472-228">これらのフローは、Office 365 内の Teams トランスポート リレーにより中継されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-228">These flows are relayed by Teams Transport Relay within Office 365.</span></span>

<span data-ttu-id="b9472-229">メディアは双方向で、どちら側が通信を開始したかを接続の観点から示します。</span><span class="sxs-lookup"><span data-stu-id="b9472-229">Media is bidirectional, where direction indicates which side initiates the communication from a connectivity perspective.</span></span> <span data-ttu-id="b9472-230">この場合、これらのフローは、異なるトランスポート プロトコルとアドレスを使用して、シグナリングとメディアに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-230">In this case, these flows are used for signaling and media, via different transport protocols and addresses.</span></span>

<span data-ttu-id="b9472-231">**顧客ネットワークから外付ユーザーへ (ダイレクト メディア):**</span><span class="sxs-lookup"><span data-stu-id="b9472-231">**Customer network to external user (direct media):**</span></span>

<span data-ttu-id="b9472-232">[![Microsoft Teams オンライン通話フロー 図 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-232">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span></span>

<span data-ttu-id="b9472-233">*図 4 - 顧客ネットワークから外部ユーザーへ (ダイレクト メディア)*</span><span class="sxs-lookup"><span data-stu-id="b9472-233">*Figure 4 - Customer network to external user (direct media)*</span></span>
 
<span data-ttu-id="b9472-234">手順 7 では、顧客ネットワークから インターネット (クライアントのピア) のフロー 2 が選択されています。</span><span class="sxs-lookup"><span data-stu-id="b9472-234">In step 7, flow 2, from customer network to Internet (client's peer), is selected.</span></span>
- <span data-ttu-id="b9472-235">モバイル ユーザー (Office 365 経由では中継されていないという意味) とのダイレクト メディアは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="b9472-235">Direct media with remote mobile user (that is, not relayed through Office 365) is optional.</span></span> <span data-ttu-id="b9472-236">Office 365 のトランスポート リレー経由のパスを強制するために、顧客はこのパスをブロックできることを意味します。</span><span class="sxs-lookup"><span data-stu-id="b9472-236">In other words, customer may block this path to enforce a media path through Transport Relay in Office 365.</span></span>

- <span data-ttu-id="b9472-237">メディアは双方向です。</span><span class="sxs-lookup"><span data-stu-id="b9472-237">Media is bidirectional.</span></span> <span data-ttu-id="b9472-238">モバイル ユーザーへのフロー 2 の方向は、一方が通信を開始したことを接続の観点から示します。</span><span class="sxs-lookup"><span data-stu-id="b9472-238">The direction of flow 2 to remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span> 

<span data-ttu-id="b9472-239">**VPN から内部ユーザーへ (メディアは Teams トランスポート リレーが中継)**</span><span class="sxs-lookup"><span data-stu-id="b9472-239">**VPN user to internal user (media relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="b9472-240">[![Microsoft Teams オンライン通話フロー 図 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-240">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span></span>

<span data-ttu-id="b9472-241">*図 5 - VPN から内部ユーザーへ (メディアは Teams トランスポート リレーが中継)*</span><span class="sxs-lookup"><span data-stu-id="b9472-241">*Figure 5 - VPN user to internal user (media relayed by Teams Transport Relay)*</span></span>
 
<span data-ttu-id="b9472-242">VPN と顧客ネットワークとの間のシグナリングは、フロー 2 経由で行われます。</span><span class="sxs-lookup"><span data-stu-id="b9472-242">Signaling between the VPN to the customer network is via flow 2'.</span></span> <span data-ttu-id="b9472-243">顧客ネットワークと Office 365 との間のシグナリングは、フロー 4 経由で行われます。</span><span class="sxs-lookup"><span data-stu-id="b9472-243">Signaling between the customer network and Office 365 is via flow 4.</span></span> <span data-ttu-id="b9472-244">ただし、メディアは VPN をバイパスし、Office 365 の Teams メディア リレーを介してフロー 3 とフロー 4 経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b9472-244">However, media bypasses the VPN and is routed via flows 3 and 4 through Teams media relay in Office 365.</span></span>

<span data-ttu-id="b9472-245">**VPN ユーザーから内部ユーザーへ (ダイレクトメディア)**</span><span class="sxs-lookup"><span data-stu-id="b9472-245">**VPN user to internal user (direct media)**</span></span>

<span data-ttu-id="b9472-246">[![Microsoft Teams オンライン通話フロー 図 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-246">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span></span>

<span data-ttu-id="b9472-247">*図 6 - VPN ユーザーから内部ユーザーへ (ダイレクトメディア)*</span><span class="sxs-lookup"><span data-stu-id="b9472-247">*Figure 6 - VPN user to internal user (direct media)*</span></span>

<span data-ttu-id="b9472-248">VPN と顧客ネットワークとの間のシグナリングは、フロー 2 経由で行われます。</span><span class="sxs-lookup"><span data-stu-id="b9472-248">Signaling between the VPN to the customer network is via flow 2'.</span></span> <span data-ttu-id="b9472-249">顧客ネットワークと Office 365 との間のシグナリングは、フロー 4 経由で行われます。</span><span class="sxs-lookup"><span data-stu-id="b9472-249">Signaling between the customer network and Office 365 is via flow 4.</span></span> <span data-ttu-id="b9472-250">ただし、メディアは VPN をバイパスし、フロー 2 (顧客ネットワークからインターネット) 経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b9472-250">However, media bypasses the VPN and is routed via flow 2 from the customer network to the Internet.</span></span>

<span data-ttu-id="b9472-251">メディアは双方向です。</span><span class="sxs-lookup"><span data-stu-id="b9472-251">Media is bidirectional.</span></span> <span data-ttu-id="b9472-252">モバイル ユーザーへのフロー 2 の方向は、一方が通信を開始したことを接続の観点から示します。</span><span class="sxs-lookup"><span data-stu-id="b9472-252">The direction of flow 2 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

<span data-ttu-id="b9472-253">**VPN ユーザーから外部ユーザーへ (ダイレクトメディア)**</span><span class="sxs-lookup"><span data-stu-id="b9472-253">**VPN user to external user (direct media)**</span></span>

<span data-ttu-id="b9472-254">[![Microsoft Teams オンライン通話フロー 図 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-254">[![Microsoft Teams call flows Figure 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span></span>

<span data-ttu-id="b9472-255">*図 7 - VPN ユーザーから外部ユーザーへ (ダイレクトメディア)*</span><span class="sxs-lookup"><span data-stu-id="b9472-255">*Figure 7 - VPN user to external user (direct media)*</span></span>

<span data-ttu-id="b9472-256">VPN からのシグナリングは、顧客ネットワークへはフロー 2' 経由で、Office 365 へはフロー 4 経由で行われます。</span><span class="sxs-lookup"><span data-stu-id="b9472-256">Signaling between the VPN user to the customer network is via flow 2' and via flow 4 to Office 365.</span></span> <span data-ttu-id="b9472-257">ただし、メディアは VPN をバイパスし、フロー 6 経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b9472-257">However, media bypasses VPN and is routed via flow 6.</span></span>

<span data-ttu-id="b9472-258">メディアは双方向です。</span><span class="sxs-lookup"><span data-stu-id="b9472-258">Media is bidirectional.</span></span> <span data-ttu-id="b9472-259">モバイル ユーザーへのフロー 6 の方向は、一方が通信を開始したことを接続の観点から示します。</span><span class="sxs-lookup"><span data-stu-id="b9472-259">The direction of flow 6 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a><span data-ttu-id="b9472-260">ユース ケース: Office 365 トランク経由で Teams から PSTN へ</span><span class="sxs-lookup"><span data-stu-id="b9472-260">Use Case: Teams to PSTN through Office 365 Trunk</span></span>
<span data-ttu-id="b9472-261">Office 365 には、公衆交換電話網 (PSTN) を使用して通話を発信および受信できる電話システムがあります。</span><span class="sxs-lookup"><span data-stu-id="b9472-261">Office 365 has a Phone System that allows placing and receiving calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="b9472-262">PSTN トランクが電話システムの通話プラン経由で接続されている場合、このユース ケースに関しては特別な接続要件はありません。</span><span class="sxs-lookup"><span data-stu-id="b9472-262">If the PSTN trunk is connected via the Phone System Calling Plan, then there are no special connectivity requirements for this use case.</span></span> <span data-ttu-id="b9472-263">(自社のオンプレミスの PSTN トランクを Office 365 に接続する場合は、電話システムのダイレクト ルーティングを使用できます。)</span><span class="sxs-lookup"><span data-stu-id="b9472-263">(If you want to connect your own on-premises PSTN trunk to Office 365, you can use Phone System Direct Routing.)</span></span>

<span data-ttu-id="b9472-264">[![Microsoft Teams オンライン通話フロー 図 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-264">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span></span>

<span data-ttu-id="b9472-265">*図 8 - Office 365 トランク経由で Teams から PSTN へ*</span><span class="sxs-lookup"><span data-stu-id="b9472-265">*Figure 8 - Teams to PSTN through Office 365 Trunk*</span></span>

#### <a name="use-case-teams-meeting"></a><span data-ttu-id="b9472-266">ユースケース: チーム会議</span><span class="sxs-lookup"><span data-stu-id="b9472-266">Use Case: Teams Meeting</span></span>

<span data-ttu-id="b9472-267">音声/ビデオ/画面共有 (VBSS) 会議サーバーは、Office 365 の一部です。</span><span class="sxs-lookup"><span data-stu-id="b9472-267">The audio/video/screen sharing (VBSS) conferencing server is part of Office 365.</span></span> <span data-ttu-id="b9472-268">これには顧客ネットワークから到達可能である必要があるパブリック IP アドレスが含まれ、これは、Nomadic Cloud のクライアントから到達可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9472-268">It has a public IP address that must be reachable from the customer network and must be reachable from a Nomadic Cloud client.</span></span> <span data-ttu-id="b9472-269">各クライアント/エンドポイントは、会議サーバーに接続できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9472-269">Each client/endpoint needs to be able to connect to the conferencing server.</span></span>

<span data-ttu-id="b9472-270">内部クライアントは、一対一の通話で説明したのと同じ方法でローカル、再帰、およびリレー候補を取得します。</span><span class="sxs-lookup"><span data-stu-id="b9472-270">Internal clients will obtain local, reflexive, and relay candidates in the same manner as described for one-to-one calls.</span></span> <span data-ttu-id="b9472-271">クライアントは、招待状にある会議サーバーにこれらの候補を送信します。</span><span class="sxs-lookup"><span data-stu-id="b9472-271">The clients will send these candidates to the conferencing server in an invite.</span></span> <span data-ttu-id="b9472-272">会議サーバーは、公開されている IP アドレスを持っているためにリレーを使用しません。そのため、会議サーバーのローカル IP アドレス候補が返されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-272">The conferencing server does not use a relay since it has a publicly reachable IP address, so it responds with its local IP address candidate.</span></span> <span data-ttu-id="b9472-273">クライアントと会議サーバーは、一対一の通話で説明したのと同じ方法で接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="b9472-273">The client and conferencing server will check connectivity in the same manner described for one-to-one calls.</span></span> 

<span data-ttu-id="b9472-274">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b9472-274">Note that:</span></span>

- <span data-ttu-id="b9472-275">Teams のクライアントは Skype for business 会議に参加できず、Skype for Business のクライアントは Teams 会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="b9472-275">Teams clients cannot join Skype for Business meetings, and Skype for Business clients cannot join Teams meetings.</span></span>

- <span data-ttu-id="b9472-276">PSTN ユーザーは、会議開催者の PSTN 通話および/または会議のプロビジョニングに応じて、"ダイヤル イン" または "ダイヤル アウト" することもできます。</span><span class="sxs-lookup"><span data-stu-id="b9472-276">A PSTN user optionally "Dials IN" or "Dialed OUT", depending on the meeting's organizer PSTN Calling and/or conferencing provisioning.</span></span> 

- <span data-ttu-id="b9472-277">ゲスト ユーザーまたは顧客ユーザーはゲスト プライベートネットワークに参加できます。このネットワークは、厳密なルールを適用して FW/NAT を介して保護されています。</span><span class="sxs-lookup"><span data-stu-id="b9472-277">A guest user or a customer user may join from a guest private network, which is protected via FW/NAT with strict rules.</span></span>

<span data-ttu-id="b9472-278">[![Microsoft Teams オンライン通話フロー 図 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-278">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span></span>

<span data-ttu-id="b9472-279">*図 9 - Teams 会議*</span><span class="sxs-lookup"><span data-stu-id="b9472-279">*Figure 9 - Teams Meeting*</span></span>

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a><span data-ttu-id="b9472-280">ユース ケース: Skype for Business オンプレミス とのフェデレーション</span><span class="sxs-lookup"><span data-stu-id="b9472-280">Use Case: Federation with Skype for Business on premises</span></span>

<span data-ttu-id="b9472-281">**Office 365 内の Teams トランスポート リレーにより中継されるメディア**</span><span class="sxs-lookup"><span data-stu-id="b9472-281">**Media relayed by Teams Transport Relay in Office 365**</span></span>

<span data-ttu-id="b9472-282">[![Microsoft Teams オンライン通話フロー 図 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-282">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span></span>

<span data-ttu-id="b9472-283">*図 10 - Office 365 内の Teams トランスポート リレーにより中継されるメディア*</span><span class="sxs-lookup"><span data-stu-id="b9472-283">*Figure 10 - Media relayed by Teams Transport Relay in Office 365*</span></span>

<span data-ttu-id="b9472-284">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b9472-284">Note that:</span></span>

- <span data-ttu-id="b9472-285">フェデレーションは、その性質上、2 つのテナント間の通信です。</span><span class="sxs-lookup"><span data-stu-id="b9472-285">Federation is, by definition, a communication between two tenants.</span></span> <span data-ttu-id="b9472-286">この例では、Teams を使用する テナント A は、Skype for Business オンプレミスを使用するテナント B とフェデレーションします。</span><span class="sxs-lookup"><span data-stu-id="b9472-286">In this case, tenant A, which uses Teams, federates with tenant B, which uses Skype for Business on premises.</span></span> <span data-ttu-id="b9472-287">もしテナント B も Office 365 を使用していた場合は、Skype for Business クライアントは Office 365 との接続にフロー 3 を使用していたはずです。</span><span class="sxs-lookup"><span data-stu-id="b9472-287">If tenant B is also using Office 365, then the Skype for Business client would have used flow 3 to connect with Office 365.</span></span>

- <span data-ttu-id="b9472-288">フェデレーションされた Skype for Business クライアントからオンプレミスの Skype for Business サーバーへのシグナリングとメディアについては、この記事では説明しませんが、</span><span class="sxs-lookup"><span data-stu-id="b9472-288">Signaling and media from the federated Skype for Business client to on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="b9472-289">説明をわかりやすくするためにこれを図に示します。</span><span class="sxs-lookup"><span data-stu-id="b9472-289">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="b9472-290">Teams と Skype for Business の間のシグナリングは、Office 365 のゲートウェイによりブリッジされます。</span><span class="sxs-lookup"><span data-stu-id="b9472-290">Signaling between Teams and Skype for Business is bridged by a gateway in Office 365.</span></span>

- <span data-ttu-id="b9472-291">メディアはこの場合、Office 365 内の Teams トランスポート リレーにより、フロー 4 経由で Skype for Business クライアントに中継されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-291">Media in this case is relayed by Teams Transport Relay in Office 365 to the customer network and remote Skype for Business client via flow 4.</span></span>

<span data-ttu-id="b9472-292">**フェデレーションされたテナントの Skype for Business メディア リレーによって中継されるメディア**</span><span class="sxs-lookup"><span data-stu-id="b9472-292">**Media relayed by Skype for Business Media Relay in federated tenant**</span></span>

<span data-ttu-id="b9472-293">[![Microsoft Teams オンライン通話フロー 図 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-293">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span></span>

<span data-ttu-id="b9472-294">*図 11 - フェデレーションされたテナントの Skype for Business メディア リレーによって中継されるメディア*</span><span class="sxs-lookup"><span data-stu-id="b9472-294">*Figure 11 - Media relayed by Skype for Business Media Relay in federated tenant*</span></span>

<span data-ttu-id="b9472-295">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b9472-295">Note that:</span></span>

- <span data-ttu-id="b9472-296">フェデレーションされた Skype for Business クライアントからオンプレミスの Skype for Business サーバーへのシグナリングとメディアについては、この記事では説明しませんが、</span><span class="sxs-lookup"><span data-stu-id="b9472-296">Signaling and media from the federated Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="b9472-297">説明をわかりやすくするためにこれを図に示します。</span><span class="sxs-lookup"><span data-stu-id="b9472-297">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="b9472-298">Teams と Skype for Business の間のシグナリングは、Office 365 のゲートウェイによりブリッジされます。</span><span class="sxs-lookup"><span data-stu-id="b9472-298">Signaling between Teams and Skype for Business is bridged by a Gateway in Office 365.</span></span>

- <span data-ttu-id="b9472-299">メディアはこの場合、Skype for Business オンプレミス メディア リレーにより、フロー 2 経由で顧客ネットワークに中継されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-299">Media in this case is relayed by Skype for Business on-premises Media Relay to the customer network via flow 2.</span></span> <span data-ttu-id="b9472-300">(フェデレーションされた顧客ネットワークのリモート メディア リレーへ Teams ユーザーからのトラフィックは、逆方向のトラフィックが流れ始めるまで、メディアリレーによって最初はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="b9472-300">(Note that traffic from Teams user to the remote Media Relay in the federated customer network will be initially blocked by the Media Relay until traffic in the reverse direction starts to flow.</span></span> <span data-ttu-id="b9472-301">ただし、双方向フローは、双方向の接続を開きます)。</span><span class="sxs-lookup"><span data-stu-id="b9472-301">However, the bidirectional flow will open connectivity in both directions.)</span></span>

<span data-ttu-id="b9472-302">**直接 (ピアツーピア)**</span><span class="sxs-lookup"><span data-stu-id="b9472-302">**Direct (peer-to-peer)**</span></span>

<span data-ttu-id="b9472-303">[![Microsoft Teams オンライン通話フロー 図 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-303">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span></span>

<span data-ttu-id="b9472-304">*図 12 - 直接 (ピアツーピア)*</span><span class="sxs-lookup"><span data-stu-id="b9472-304">*Figure 12 - Direct (peer-to-peer)*</span></span>

### <a name="teams-hybrid-topology"></a><span data-ttu-id="b9472-305">Teams ハイブリッド トポロジ</span><span class="sxs-lookup"><span data-stu-id="b9472-305">Teams hybrid topology</span></span>
<span data-ttu-id="b9472-306">このトポロジには、Skype for Business のオンプレミス展開を使用する Teams が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9472-306">This topology includes Teams with a Skype for Business on-premises deployment.</span></span>

<span data-ttu-id="b9472-307">[![Microsoft Teams オンライン通話フロー 図 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-307">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span></span>

<span data-ttu-id="b9472-308">*図 13 - Teams ハイブリッド トポロジ*</span><span class="sxs-lookup"><span data-stu-id="b9472-308">*Figure 13 - Teams hybrid topology*</span></span>
 
- <span data-ttu-id="b9472-309">上の図の矢印の方向は、エンタープライズ境界での接続に影響を与える、通信の開始方向を反映します。</span><span class="sxs-lookup"><span data-stu-id="b9472-309">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="b9472-310">メディアの UDP については、最初のパケットは逆方向に流れる場合がありますが、これらのパケットは、別の方向へのパケットが流れるまでブロックされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b9472-310">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="b9472-311">Teams は、Skype for Business Online と並行して展開されます。そのため、クライアントは "Teams/SFB ユーザー" として表示されています。</span><span class="sxs-lookup"><span data-stu-id="b9472-311">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user".</span></span>

<span data-ttu-id="b9472-312">その他のフロー (Teams のトポロジへの追加)</span><span class="sxs-lookup"><span data-stu-id="b9472-312">Additional flows (on top of Teams topology):</span></span>
- <span data-ttu-id="b9472-313">**フロー 5 A** – 顧客ネットワーク内の Teams ユーザーと、顧客ネットワークのエッジにある Skype for Business オンプレミス メディア リレーとの間の、ピアツーピアのメディア フローを表します。</span><span class="sxs-lookup"><span data-stu-id="b9472-313">**Flow 5A** – Represents a peer-to-peer media flow between a Teams user within the customer network and a Skype for Business on-premises media relay at the customer network edge.</span></span>

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a><span data-ttu-id="b9472-314">ユース ケース: Teams から Skype for Business へ、一対一</span><span class="sxs-lookup"><span data-stu-id="b9472-314">Use Case: Teams to Skype for Business one-to-one</span></span>
<span data-ttu-id="b9472-315">**顧客ネットワーク内のハイブリッド**</span><span class="sxs-lookup"><span data-stu-id="b9472-315">**Hybrid within the customer network**</span></span>

<span data-ttu-id="b9472-316">[![Microsoft Teams オンライン通話フロー 図 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-316">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span></span>

<span data-ttu-id="b9472-317">*図 14 - 顧客ネットワーク内のハイブリッド*</span><span class="sxs-lookup"><span data-stu-id="b9472-317">*Figure 14 - Hybrid within customer network*</span></span>
 
<span data-ttu-id="b9472-318">Teams と Skype for Business の間のシグナリングは、Office 365 のゲートウェイによりブリッジされます。</span><span class="sxs-lookup"><span data-stu-id="b9472-318">Signaling between Teams and Skype for Business is bridged by a gateway in Office 365.</span></span> <span data-ttu-id="b9472-319">ただし、メディアは顧客ネットワーク内で、フロー 5 経由でピアツーピアに直接ルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b9472-319">However, media is routed directly peer-to-peer within the customer network via flow 5.</span></span>

<span data-ttu-id="b9472-320">**ハイブリッドの顧客ネットワークから外部の Skype for Business ユーザーへ (Office 365 により中継)**</span><span class="sxs-lookup"><span data-stu-id="b9472-320">**Hybrid customer network with external Skype for Business user – relayed by Office 365**</span></span>

<span data-ttu-id="b9472-321">[![Microsoft Teams オンライン通話フロー 図 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-321">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span></span>

<span data-ttu-id="b9472-322">*図 15 - ハイブリッドの顧客ネットワークから外部の Skype for Business ユーザーへ (Office 365 により中継)*</span><span class="sxs-lookup"><span data-stu-id="b9472-322">*Figure 15 - Hybrid customer network with external Skype for Business user - relayed by Office 365*</span></span>

<span data-ttu-id="b9472-323">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b9472-323">Note that:</span></span>

- <span data-ttu-id="b9472-324">Skype for Business クライアントからオンプレミスの Skype for Business サーバーへのシグナリングとメディアについては、この記事では説明しませんが、</span><span class="sxs-lookup"><span data-stu-id="b9472-324">Signaling and media from the Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="b9472-325">説明をわかりやすくするためにこれを図に示します。</span><span class="sxs-lookup"><span data-stu-id="b9472-325">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="b9472-326">Teams と Skype for Business の間のシグナリングは、Office 365 のゲートウェイによりブリッジされます。</span><span class="sxs-lookup"><span data-stu-id="b9472-326">Signaling between Teams and Skype for Business is bridged by a gateway in Office 365.</span></span>

- <span data-ttu-id="b9472-327">メディアは、Office 365 内の Teams トランスポート リレーを通して、フロー 4 経由で顧客ネットワークに中継されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-327">Media is relayed through Teams Transport Relay in Office 365 to the customer network through flow 4.</span></span>

<span data-ttu-id="b9472-328">**ハイブリッドの顧客ネットワークから外部の Skype for Business ユーザーへ (オンプレミス エッジ により中継)**</span><span class="sxs-lookup"><span data-stu-id="b9472-328">**Hybrid customer network with external Skype for Business user – relayed by on-premises Edge**</span></span>

<span data-ttu-id="b9472-329">[![Microsoft Teams オンライン通話フロー 図 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-329">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span></span>

<span data-ttu-id="b9472-330">*図 16 - ハイブリッドの顧客ネットワークから外部の Skype for Business ユーザーへ (オンプレミス エッジ により中継)*</span><span class="sxs-lookup"><span data-stu-id="b9472-330">*Figure 16 - Hybrid customer network with external Skype for Business user - relayed by on-premises Edge*</span></span>
 
<span data-ttu-id="b9472-331">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b9472-331">Note that:</span></span>

- <span data-ttu-id="b9472-332">Skype for Business クライアントからオンプレミスの Skype for Business サーバーへのシグナリングとメディアについては、この記事では説明しませんが、</span><span class="sxs-lookup"><span data-stu-id="b9472-332">Signaling and media from Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="b9472-333">説明をわかりやすくするためにこれを図に示します。</span><span class="sxs-lookup"><span data-stu-id="b9472-333">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="b9472-334">シグナリングは、Office 365 のゲートウェイによってブリッジされます。</span><span class="sxs-lookup"><span data-stu-id="b9472-334">Signaling is bridged by a gateway in Office 365.</span></span>

- <span data-ttu-id="b9472-335">メディアは、Skype for Business オンプレミス エッジ内の Skype for Business メディア リレーにより、フロー 5A 経由で顧客ネットワーク内の Teams ユーザーに中継されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-335">Media is relayed by Skype for Business Media Relay within Skype for Business on-premises Edge to Teams user within the customer network via media flow 5A.</span></span>

### <a name="teams-with-phone-system-direct-routing-topology"></a><span data-ttu-id="b9472-336">電話システムのダイレクト ルーティングを使用する Teams のトポロジ</span><span class="sxs-lookup"><span data-stu-id="b9472-336">Teams with Phone System Direct Routing topology</span></span>
<span data-ttu-id="b9472-337">このトポロジには、電話システムのダイレクト ルーティングを使用する Teams が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9472-337">This topology includes Teams with Phone System Direct Routing.</span></span> 

<span data-ttu-id="b9472-338">ダイレクト ルーティングを使用すると、サポートされている顧客が所有するオンプレミスのセッション ボーダー コントローラー (SBC) 機器デバイスを Office 365 にペアリングし、次にテレフォニー トランクをそのデバイスに接続することにより、公衆交換電話網 (PSTN) のサードパーティ サービス プロバイダーを利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b9472-338">Direct Routing enables you to use a third-party Public Switched Telephone Network (PSTN) service provider by pairing a supported on-premises customer-owned Session Border Controller (SBC) hardware device to Office 365, and then connecting the telephony trunk to that device.</span></span> 

<span data-ttu-id="b9472-339">このシナリオをサポートするには、顧客は、Microsoft の認定パートナーのいずれかによりダイレクト ルーティング用に認定された SBC を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9472-339">To support this scenario, the customer must deploy a certified SBC for Direct Routing from one of Microsoft's certified partners.</span></span> <span data-ttu-id="b9472-340">SBC は製造元の推奨通りに構成する必要があり、Office 365 からのダイレクト UDP トラフィックがルーティング可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9472-340">The SBC must be configured as recommended by the vendor, and be routable from Office 365 for direct UDP traffic.</span></span> <span data-ttu-id="b9472-341">メディアは、Teams クライアントおよび/または Skype for Business クライアントから (Teams ゲートウェイをバイパスして) SBC に直接流れることも、Teams ゲートウェイを通過することもできます。</span><span class="sxs-lookup"><span data-stu-id="b9472-341">The media may flow directly from Teams and/or the Skype for Business client to the SBC (bypassing the Teams gateway) or traverse through the Teams gateway.</span></span> <span data-ttu-id="b9472-342">トランクが Teams ゲートウェイをバイパスするように構成されている場合は、SBC との接続は ICE に基づきます。SBC では ICE-Lite がサポートされ、Teams/Skype for Business のメディア エンドポイントでは ICE Full がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="b9472-342">The connectivity with the SBC, when the trunk is configured to bypass the Teams gateway, is based on ICE, where SBC supports ICE-Lite, while the Teams/Skype for Business media endpoint supports ICE Full.</span></span> 

<span data-ttu-id="b9472-343">[![Microsoft Teams オンライン通話フロー 図 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-343">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span></span>

<span data-ttu-id="b9472-344">\*図 17 - 電話システムのダイレクト ルーティングを使用する Teams のトポロジ</span><span class="sxs-lookup"><span data-stu-id="b9472-344">\*Figure 17 - Teams with Phone System Direct Routing topology</span></span>

<span data-ttu-id="b9472-345">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b9472-345">Note that:</span></span>

- <span data-ttu-id="b9472-346">上の図の矢印の方向は、エンタープライズ境界での接続に影響を与える、通信の開始方向を反映します。</span><span class="sxs-lookup"><span data-stu-id="b9472-346">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="b9472-347">メディアの UDP については、最初のパケットは逆方向に流れる場合がありますが、これらのパケットは、別の方向へのパケットが流れるまでブロックされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b9472-347">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="b9472-348">Teams は、Skype for Business Online と並行して展開されます。そのため、クライアントは "Teams/SFB ユーザー" として表示されています。</span><span class="sxs-lookup"><span data-stu-id="b9472-348">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user".</span></span>

<span data-ttu-id="b9472-349">その他のフロー (Teams のトポロジへの追加):</span><span class="sxs-lookup"><span data-stu-id="b9472-349">Additional flows (on top of Teams online topology):</span></span>
- <span data-ttu-id="b9472-350">**フロー 4'** - クラウド内の Teams メディア サーバーとオンプレミスの SBC との間の接続を確立するために使用される、Office 365 から顧客ネットワークへのフローを表します。</span><span class="sxs-lookup"><span data-stu-id="b9472-350">**Flow 4'** - Represents a flow from Office 365 to the customer network, used to establish a connection between the Teams media server in the cloud with the SBC on premises.</span></span>
- <span data-ttu-id="b9472-351">**フロー 5B** - バイパス モードでの、顧客ネットワーク内の Teams ユーザーとダイレクト ルーティング SBC のメディア フローを表します。</span><span class="sxs-lookup"><span data-stu-id="b9472-351">**Flow 5B** – Represents a media flow between the Teams user within the customer network with the Direct Routing SBC in bypass mode.</span></span>
- <span data-ttu-id="b9472-352">**フロー 5C** – PSTN ヘアピン コール バイパス モードでの、ダイレクト ルーティング SBC と別のダイレクト ルーティング SBC と間のメディア フローを表します。 </span><span class="sxs-lookup"><span data-stu-id="b9472-352">**Flow 5C** – Represents a media flow between the Direct Routing SBC to another Direct Routing SBC in a PSTN hairpin call bypass mode.</span></span>

<span data-ttu-id="b9472-353">**ダイレクト ルーティングによる内部ユーザー (メディアは Office 365 内の Teams トランスポート リレーが中継)**</span><span class="sxs-lookup"><span data-stu-id="b9472-353">**Internal user with Direct Routing (media relayed by Teams Transport Relay in Office 365)**</span></span>

<span data-ttu-id="b9472-354">[![Microsoft Teams オンライン通話フロー 図 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-354">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span></span>

<span data-ttu-id="b9472-355">*図 18 - ダイレクト ルーティングによる内部ユーザー (メディアは Office 365 内の Teams トランスポート リレーが中継)*</span><span class="sxs-lookup"><span data-stu-id="b9472-355">*Figure 18 - Internal user with Direct Routing (media relayed by Teams Transport Relay in Office 365)*</span></span>

<span data-ttu-id="b9472-356">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b9472-356">Note that:</span></span>
 
- <span data-ttu-id="b9472-357">SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="b9472-357">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="b9472-358">SBC から Office 365 へのシグナリングおよびメディア、およびその逆のシグナリングは、フロー4 および/またはフロー 4' を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9472-358">Signaling and media from the SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="b9472-359">顧客ネットワーク内のクライアントから Office 365 へのシグナリングおよびメディアは、フロー 4 を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9472-359">Signaling and media from the client within the customer network to Office 365 use flow 4.</span></span>


<span data-ttu-id="b9472-360">**ダイレクト ルーティングを使用するリモート ユーザー (メディアは Office 365 のメディア サーバー (MP) 経由でルーティング)**</span><span class="sxs-lookup"><span data-stu-id="b9472-360">**Remote user with Direct Routing (media is routed through a media server (MP) in Office 365)**</span></span>

<span data-ttu-id="b9472-361">[![Microsoft Teams オンライン通話フロー 図 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-361">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span></span>

<span data-ttu-id="b9472-362">*図 19 - ダイレクト ルーティングを使用するリモート ユーザー (メディアは Office 365 のメディア サーバー (MP) 経由でルーティング)*</span><span class="sxs-lookup"><span data-stu-id="b9472-362">*Figure 19 - Remote user with Direct Routing (media is routed through a media server (MP) in Office 365)*</span></span>
 
<span data-ttu-id="b9472-363">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b9472-363">Note that:</span></span>

- <span data-ttu-id="b9472-364">SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="b9472-364">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="b9472-365">SBC から Office 365 へのシグナリングおよびメディア、およびその逆のシグナリングは、フロー4 および/またはフロー 4' を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9472-365">Signaling and media from the SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="b9472-366">インターネット上のクライアントから Office 365 へのシグナリングおよびメディアは、フロー 3 を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9472-366">Signaling and media from the client on the Internet to Office 365 use flow 3.</span></span>

<span data-ttu-id="b9472-367">**内部ユーザーのダイレクト ルーティング (メディアはバイパス)**</span><span class="sxs-lookup"><span data-stu-id="b9472-367">**Internal user Direct Routing (media bypass)**</span></span>

<span data-ttu-id="b9472-368">[![Microsoft Teams オンライン通話フロー 図 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-368">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span></span>

<span data-ttu-id="b9472-369">*図 20 - 内部ユーザーのダイレクト ルーティング (メディアはバイパス)*</span><span class="sxs-lookup"><span data-stu-id="b9472-369">*Figure 20 - Internal user Direct Routing (media bypass)*</span></span>
 
<span data-ttu-id="b9472-370">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b9472-370">Note that:</span></span>

- <span data-ttu-id="b9472-371">SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="b9472-371">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="b9472-372">SBC から Office 365 へのシグナリングおよびその逆のシグナリングは、フロー4 および/またはフロー 4' を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9472-372">Signaling from SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="b9472-373">顧客ネットワーク内のクライアントから Office 365 へのシグナリングは、フロー 4 を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9472-373">Signaling from client within the customer network to Office 365 use flow 4.</span></span>

- <span data-ttu-id="b9472-374">顧客ネットワーク内のクライアントから顧客ネットワーク内の SBC へのメディアは、5B を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9472-374">Media from client within the customer network to SBC within the customer network use flow 5B.</span></span>

<span data-ttu-id="b9472-375">**ダイレクト ルーティングによるリモート ユーザー (メディアのパイパスは Office 365 内の Teams トランスポート リレーが中継)**</span><span class="sxs-lookup"><span data-stu-id="b9472-375">**Remote user with Direct Routing (media bypass relayed by Teams Transport Relay in Office 365)**</span></span>

<span data-ttu-id="b9472-376">[![Microsoft Teams オンライン通話フロー 図 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-376">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span></span>

<span data-ttu-id="b9472-377">*図 21 - ダイレクト ルーティングによるリモート ユーザー (メディアのパイパスは Office 365 内の Teams トランスポート リレーが中継)*</span><span class="sxs-lookup"><span data-stu-id="b9472-377">*Figure 21 - Remote user with Direct Routing (media bypass relayed by Teams Transport Relay in Office 365)*</span></span>

<span data-ttu-id="b9472-378">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b9472-378">Note that:</span></span>

- <span data-ttu-id="b9472-379">SBC には、Office 365 およびインターネットからルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="b9472-379">The SBC must have a public IP address that is routable from Office 365 and Internet.</span></span>

- <span data-ttu-id="b9472-380">SBC から Office 365 へのシグナリングおよびその逆のシグナリングは、フロー4 および/またはフロー 4' を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9472-380">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="b9472-381">インターネット上のクライアントから Office 365 へのシグナリングは、フロー 3 を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9472-381">Signaling from the client on the Internet to Office 365 uses flow 3.</span></span>

- <span data-ttu-id="b9472-382">インターネット上のクライアントから顧客ネットワーク内の SBC へのメディアでは フロー 3 および 4 が使用され、Office 365 内の Teams トランスポート リレーにより中継されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-382">Media from the client on the Internet to the SBC within the customer network uses flows 3 and 4, relayed by Teams Transport Relay in Office 365.</span></span> 

<span data-ttu-id="b9472-383">**リモート ユーザーのダイレクト ルーティング (メディアのバイパスはダイレクト)**</span><span class="sxs-lookup"><span data-stu-id="b9472-383">**Remote user Direct Routing (media bypass direct)**</span></span>

<span data-ttu-id="b9472-384">[![Microsoft Teams オンライン通話フロー 図 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-384">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span></span>

<span data-ttu-id="b9472-385">*図 22 - リモート ユーザーのダイレクト ルーティング (メディアのバイパスはダイレクト)*</span><span class="sxs-lookup"><span data-stu-id="b9472-385">*Figure 22 - Remote user Direct Routing (media bypass direct)*</span></span>
 
<span data-ttu-id="b9472-386">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b9472-386">Note that:</span></span>

- <span data-ttu-id="b9472-387">SBC には、Office 365 およびインターネットからルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="b9472-387">The SBC must have a public IP address that is routable from Office 365 and the Internet.</span></span>

- <span data-ttu-id="b9472-388">SBC から Office 365 へのシグナリングおよびその逆のシグナリングは、フロー4 および/またはフロー 4' を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9472-388">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="b9472-389">インターネット上のクライアントから Office 365 へのシグナリングは、フロー 3 を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9472-389">Signaling from the client on the Internet to Office 365 uses flow 3.</span></span>

- <span data-ttu-id="b9472-390">インターネット上のクライアントから顧客ネットワーク内の SBC へのメディアは、 フロー 2 を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9472-390">Media from the client on the Internet to the SBC within the customer network uses flow 2.</span></span>

<span data-ttu-id="b9472-391">**ダイレクト ルーティング (メディア バイパス) – PSTN ヘアピン コール (通話の転送を原因とする)**</span><span class="sxs-lookup"><span data-stu-id="b9472-391">**Direct Routing (media bypass) – PSTN hairpin call (due to call forward/transfer)**</span></span>

<span data-ttu-id="b9472-392">[![Microsoft Teams オンライン通話フロー 図 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-392">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span></span>

<span data-ttu-id="b9472-393">*図 23 - ダイレクト ルーティング (メディア バイパス) – PSTN ヘアピン コール (通話の転送を原因とする)*</span><span class="sxs-lookup"><span data-stu-id="b9472-393">*Figure 23 - Direct Routing (media bypass) - PSTN hairpin call (due to call forward/transfer)*</span></span>
 
<span data-ttu-id="b9472-394">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b9472-394">Note that:</span></span>

- <span data-ttu-id="b9472-395">SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="b9472-395">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="b9472-396">SBC から Office 365 へのシグナリングおよびその逆のシグナリングは、フロー4 および/またはフロー 4' を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9472-396">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="b9472-397">PSTN から PSTN への通話のヘアピンが発生すると、クライアントはシグナリングおよびメディア ループに含まれなくなります。</span><span class="sxs-lookup"><span data-stu-id="b9472-397">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="b9472-398">顧客ネットワーク内の SBC インスタンス A から顧客ネットワーク内の SBC インスタンス B までのメディア (A と B は同じインスタンスでも構いません) は、フロー 5C を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9472-398">Media from SBC instance A within the customer network to SBC instance B within the customer network (where, A and B can be the same instance) uses flow 5C.</span></span>

<span data-ttu-id="b9472-399">**ダイレクト ルーティング (メディアは Office 365 を経由) – 2 つのテナントの間での PSTN ヘアピン コール**</span><span class="sxs-lookup"><span data-stu-id="b9472-399">**Direct Routing (media through Office 365) – PSTN hairpin call across two tenants**</span></span>

<span data-ttu-id="b9472-400">[![Microsoft Teams オンライン通話フロー 図 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-400">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span></span>

<span data-ttu-id="b9472-401">*図 24 - ダイレクト ルーティング (メディアは Office 365 を経由) – 2 つのテナントの間での PSTN ヘアピン コール*</span><span class="sxs-lookup"><span data-stu-id="b9472-401">*Figure 24 - Direct Routing (media through Office 365) – PSTN hairpin call across two tenants*</span></span>
 
<span data-ttu-id="b9472-402">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b9472-402">Note that:</span></span>

- <span data-ttu-id="b9472-403">SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="b9472-403">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="b9472-404">SBC から Office 365 へのシグナリングおよびその逆のシグナリングは、フロー4 および/またはフロー 4' を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9472-404">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="b9472-405">PSTN から PSTN への通話のヘアピンが発生すると、クライアントはシグナリングおよびメディア ループに含まれなくなります。</span><span class="sxs-lookup"><span data-stu-id="b9472-405">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="b9472-406">顧客ネットワーク X 内の SBC インスタンス A からSBC インスタンス B へのメディアは、Office 365 メディア サーバー経由で中継される必要があり、バイパス モードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="b9472-406">Media from SBC instance A within the customer network X to SBC instance B must be relayed through the Office 365 Media Server and can't use bypass mode.</span></span>

## <a name="teams-with-express-route-optimization"></a><span data-ttu-id="b9472-407">Express Route による Teams の最適化</span><span class="sxs-lookup"><span data-stu-id="b9472-407">Teams with Express Route optimization</span></span>

<span data-ttu-id="b9472-408">[![Microsoft Teams オンライン通話フロー 図 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-408">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span></span>

<span data-ttu-id="b9472-409">*図 25 - Express Route による Teams の最適化*</span><span class="sxs-lookup"><span data-stu-id="b9472-409">*Figure 25 - Teams with Express Route optimization*</span></span>
 
<span data-ttu-id="b9472-410">Express Route が正当化されて展開されているケースでは、Teams のフローはフロー 4 からフロー 1 に、またフロー 4' からフロー 1' に再ルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="b9472-410">In the case that Express Route is justified and deployed, then Teams flows could be re-routed from flow 4 to flow 1 and from flow 4' to flow 1'.</span></span> <span data-ttu-id="b9472-411">ただし、Teams アプリケーションは、フロー 4 および 4' 経由のインターネット上の Office 365 フローに強く依存するため、これらのフローはブロックされない必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9472-411">However, Teams Application has a hard dependency on other Office 365 flows over the internet via flows 4 and 4'; hence these flows must not be blocked.</span></span> 

<span data-ttu-id="b9472-412">Skype for Business のハイブリッド エッジ トラフィックは、外部ユーザーとの通信および他のテナントとのフェデレーションを行うために、Express Route ではなくインターネットにルーティングされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b9472-412">Note that Skype for Business hybrid Edge traffic is routed to the Internet and not to Express Route to communicate with external users and federate with other tenants.</span></span> 

<span data-ttu-id="b9472-413">非対称のフローを防ぐには、再ルーティングは双方向に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9472-413">To prevent asymmetrical flows, re-routing must be in both directions.</span></span> <span data-ttu-id="b9472-414">つまり、顧客ネットワーク内のアドレスは、(最適化のために) インターネットまたは Express Route のいずれを経由してもルーティング可能ですが、両方を経由することはできません。</span><span class="sxs-lookup"><span data-stu-id="b9472-414">In other words, an address within the customer network is routable either through Internet or Express Route, based on optimization, but not through both.</span></span>

<span data-ttu-id="b9472-415">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b9472-415">For example:</span></span>

<span data-ttu-id="b9472-416">**顧客ネットワークから外部ユーザーへ (メディアは Teams トランスポート リレーが中継):**</span><span class="sxs-lookup"><span data-stu-id="b9472-416">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="b9472-417">[![Microsoft Teams オンライン通話フロー 図 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span><span class="sxs-lookup"><span data-stu-id="b9472-417">[![Microsoft Teams Online Call Flows](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span></span>

<span data-ttu-id="b9472-418">*図 26 - 顧客ネットワークから外部ユーザーへ (メディアは Teams トランスポート リレーが中継)*</span><span class="sxs-lookup"><span data-stu-id="b9472-418">*Figure 26 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>
 
<span data-ttu-id="b9472-419">**大まかな手順:**</span><span class="sxs-lookup"><span data-stu-id="b9472-419">**High Level Steps:**</span></span>
1. <span data-ttu-id="b9472-420">顧客ネットワーク内の Teams ユーザー A が、フロー 2 経由で URL ドメイン名 (DNS) を解決します。</span><span class="sxs-lookup"><span data-stu-id="b9472-420">Teams User within customer network resolves URL domain name (DNS) via flow2</span></span>
2. <span data-ttu-id="b9472-421">顧客ネットワーク内の Teams ユーザーが、フロー 1 経由で Teams トランスポート リレーでメディア リレー ポートを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b9472-421">Teams User within customer network allocates a media Relay port on Teams Transport Relay via flow 1</span></span>
3. <span data-ttu-id="b9472-422">顧客ネットワーク内の Teams ユーザーが、フロー 1 経由で "招待状" を ICE 候補と共に Office 365 に送信します。</span><span class="sxs-lookup"><span data-stu-id="b9472-422">Teams User within customer network sends "invite" with ICE candidates via flow 1 to Office 365</span></span>
4. <span data-ttu-id="b9472-423">Office 365 が、フロー 3 経由で Teams の外部ユーザーに通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="b9472-423">OFFICE 365 sends notification to external Teams user via flow 3</span></span>
5. <span data-ttu-id="b9472-424">Teams の外部ユーザーが、フロー 3 経由で Teams トランスポート リレーでメディア リレー ポートを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b9472-424">Teams external user allocates a media Relay port on Teams Transport Relay via flow 3</span></span>
6. <span data-ttu-id="b9472-425">Teams の外部ユーザーが、フロー 3 経由 "回答" を ICE 候補と共に送信し、これはフロー 1 経由で Teams ユーザー A に再び転送されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-425">Teams external user sends "answer" with ICE candidates via flow 3, which is forwarded back to Teams user A via Flow 1</span></span>
7. <span data-ttu-id="b9472-426">Teams ユーザー A および Teams ユーザー B が ICE 接続テストを実行してフロー 1 および フロー 3 を選択し、これらは Office 365 内の Teams トランスポート リレーにより中継されます。</span><span class="sxs-lookup"><span data-stu-id="b9472-426">Teams User A and Teams User B invoke ICE connectivity tests and selects flows 1 and 3, which are relayed by Teams Transport Relay in Office 365</span></span>
8. <span data-ttu-id="b9472-427">Teams ユーザーが、フロー 1 およびフロー 3 経由でテレメトリを Office 365 に送信します。</span><span class="sxs-lookup"><span data-stu-id="b9472-427">Teams Users send telemetry to Office 365 via flows 1 and 3</span></span>

><span data-ttu-id="b9472-428">**注**: フロー 4 を要求する他のマイクロ サービスへの Teams の依存をサポートするために、フロー 4 を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9472-428">**Note**: Flow 4 must be enabled to support dependencies of Teams application on other micro-services that mandates flow 4.</span></span>
