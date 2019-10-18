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
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: さまざまなトポロジで Teams が Office 365 フローを使用する方法について説明します。
ms.openlocfilehash: 91be46f556419dfd1ba8c52a99b8f06a19c63542
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573414"
---
# <a name="microsoft-teams-call-flows"></a><span data-ttu-id="9be3c-103">Microsoft Teams 通話のフロー</span><span class="sxs-lookup"><span data-stu-id="9be3c-103">Microsoft Teams call flows</span></span>

> [!Tip]
> <span data-ttu-id="9be3c-104">チームでネットワークを活用する方法と、最適なネットワーク接続を計画する方法については、次のセッションをご覧ください。 [Teams ネットワーク計画](https://aka.ms/teams-networking)</span><span class="sxs-lookup"><span data-stu-id="9be3c-104">Watch the following session to learn how Teams leverages your network and how to plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking)</span></span>

## <a name="overview"></a><span data-ttu-id="9be3c-105">概要</span><span class="sxs-lookup"><span data-stu-id="9be3c-105">Overview</span></span>
<span data-ttu-id="9be3c-106">この記事では、さまざまなトポロジで Teams が Office 365 のコールフローを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-106">This article describes how Teams uses Office 365 call flows in various topologies.</span></span> <span data-ttu-id="9be3c-107">また、ピアツーピアメディア通信に使用される固有のチームフローについても説明します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-107">In addition, it describes unique Teams flows that are used for peer-to-peer media communication.</span></span> <span data-ttu-id="9be3c-108">このドキュメントでは、ネットワーク上でこれらのフロー、目的、およびその発生元と終了が説明されています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-108">The document describes these flows, their purpose, and their origin and termination on the network.</span></span> <span data-ttu-id="9be3c-109">この記事の目的に応じて、次のことを前提とします。</span><span class="sxs-lookup"><span data-stu-id="9be3c-109">For purposes of this article, assume the following:</span></span>

- <span data-ttu-id="9be3c-110">Flow X は、オンプレミスの Office 365 クライアントによって、クラウドの Office 365 サービスと通信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-110">Flow X is used by the on-premises Office 365 client to communicate with the Office 365 service in the cloud.</span></span> <span data-ttu-id="9be3c-111">これは、顧客ネットワークから発信され、Office 365 のエンドポイントとして終了します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-111">It originates from the customer network, and it terminates as an endpoint in Office 365.</span></span>

- <span data-ttu-id="9be3c-112">Flow Y は、オンプレミスの Office 365 クライアントによって、Office 365 が依存しているインターネット上のサービスと通信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-112">Flow Y is used by the on-premises Office 365 client to communicate with a service on the Internet that Office 365 has a dependency on.</span></span> <span data-ttu-id="9be3c-113">これは、顧客ネットワークから発信され、インターネット上のエンドポイントとして終了します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-113">It originates from the customer network, and it terminates as an endpoint on the Internet.</span></span>

<span data-ttu-id="9be3c-114">この記事には、次のセクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-114">The article contains the following sections:</span></span>

- <span data-ttu-id="9be3c-115">**バックグラウンド**-office 365 フローが走査する可能性のあるネットワーク、トラフィックの種類、顧客ネットワークから Office 365 サービスエンドポイントへの接続のガイダンス、サードパーティ製のコンポーネントとの相互運用性などの背景情報を提供します。メディアフローを選択するために Teams で使用される原則。</span><span class="sxs-lookup"><span data-stu-id="9be3c-115">**Background** - Provides background information, such as networks that Office 365 flows may traverse, type of traffic, connectivity guidance from the customer network to Office 365 service endpoints, interoperability with third-party components, and principles that are used by Teams to select media flows.</span></span>

- <span data-ttu-id="9be3c-116">**さまざまなトポロジのコールフロー** -さまざまなトポロジでのコールフローの使い方を示しています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-116">**Call flows in various topologies** - Illustrates the use of call flows in various topologies.</span></span> <span data-ttu-id="9be3c-117">各トポロジについて、サポートされているすべてのフローを列挙し、これらのフローがさまざまなユースケースでどのように使用されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-117">For each topology, the section enumerates all supported flows and illustrates how these flows are used via several use cases.</span></span> <span data-ttu-id="9be3c-118">各ユースケースについて、フロー図を使ってフローの順序および選択を記述します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-118">For each use case, it describes the sequence and selection of flows via a flow diagram.</span></span> 

- <span data-ttu-id="9be3c-119">**エクスプレスルートの最適化を使用しているチーム**-簡易ルートを使用して最適化を展開する場合の、これらのフローの使い方について説明します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-119">**Teams with Express Route optimization** - Describes how these flows are used when Express Route is deployed for optimization, illustrated via a simple topology.</span></span>

## <a name="background"></a><span data-ttu-id="9be3c-120">背景</span><span class="sxs-lookup"><span data-stu-id="9be3c-120">Background</span></span>
### <a name="network-segments"></a><span data-ttu-id="9be3c-121">ネットワークセグメント</span><span class="sxs-lookup"><span data-stu-id="9be3c-121">Network segments</span></span>
<span data-ttu-id="9be3c-122">[**顧客ネットワーク**]: これは、管理および管理するネットワークセグメントです。</span><span class="sxs-lookup"><span data-stu-id="9be3c-122">**Customer network**: This is the network segment that you control and manage.</span></span> <span data-ttu-id="9be3c-123">これには、有線またはワイヤレス、office 建物間、オンプレミスのデータセンターへの接続、インターネットプロバイダー、Express Route、またはその他のプライベートピアリングへの接続など、顧客オフィス内のすべての顧客接続が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-123">This includes all customer connections within customer offices, whether wired or wireless, between office buildings, to on-premises datacenters, and your connections to Internet providers, Express Route, or any other private peering.</span></span> 

<span data-ttu-id="9be3c-124">通常、顧客ネットワークには、ファイアウォールやプロキシサーバーを備えたネットワーク境界がいくつかあります。これにより、組織のセキュリティポリシーが適用されます。また、設定して構成した特定のネットワークトラフィックのみを許可します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-124">Typically, a customer network has several network perimeters with firewalls and/or proxy servers, which enforce your organization's security policies, and that only allow certain network traffic that you have set up and configured.</span></span> <span data-ttu-id="9be3c-125">このネットワークを管理しているため、ネットワークのパフォーマンスを直接制御できます。また、ネットワーク上のサイトと365ネットワークの両方でパフォーマンスを検証するために、ネットワークの評価を実行することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9be3c-125">Because you manage this network, you have direct control over the performance of the network, and it is highly recommended that you complete network assessments to validate performance both within sites in your network and from your network to the Office 365 network.</span></span> 

<span data-ttu-id="9be3c-126">[ **Internet (インターネット**): これは、顧客ネットワークの外部から Office 365 に接続しているユーザーが使用する、全体的なネットワークの一部であるネットワークセグメントです。</span><span class="sxs-lookup"><span data-stu-id="9be3c-126">**Internet**: This is the network segment that is part of your overall network that will be used by users who are connecting to Office 365 from outside of the customer network.</span></span> <span data-ttu-id="9be3c-127">また、顧客ネットワークから Office 365 への一部のトラフィックでも使用されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-127">It is also used by some traffic from the customer network to Office 365.</span></span> 

<span data-ttu-id="9be3c-128">**アクセス済み/ゲストプライベートネットワーク**: これは、顧客ネットワークの外部のネットワークセグメントであり、公共のインターネットでは使用できません。ユーザーやゲストがアクセスする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9be3c-128">**Visited/Guest private network**: This is the network segment outside your customer network, but not in the public Internet, that your users and/or their guests may visit.</span></span> <span data-ttu-id="9be3c-129">たとえば、[ホームプライベートネットワーク] または [エンタープライズプライベートネットワーク] では、Teams は展開されません。これにより、チームサービスとやり取りするユーザーやユーザーが存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9be3c-129">For example, home private network or an Enterprise private network, that does not deploy Teams, where your users and/or their customers that interact with Teams services may reside.</span></span>

><span data-ttu-id="9be3c-130">**注**: Office 365 への接続は、これらのネットワークにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-130">**Note**: Connectivity to Office 365 is also applicable to these networks.</span></span>

<span data-ttu-id="9be3c-131">**Office 365**: これは、office 365 サービスをサポートするネットワークセグメントです。</span><span class="sxs-lookup"><span data-stu-id="9be3c-131">**Office 365**: This is the network segment that supports Office 365 services.</span></span> <span data-ttu-id="9be3c-132">これは、世界各地のお客様のネットワークに近接したエッジを使用して世界中に配布されています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-132">It is distributed worldwide with edges in proximity to the customer network in most locations.</span></span> <span data-ttu-id="9be3c-133">このドキュメントで説明されている関数には、トランスポートリレー、会議サーバー、メディアプロセッサが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-133">Functions mentioned in this document include Transport Relay, conferencing server, and Media Processor.</span></span> 

<span data-ttu-id="9be3c-134">[**簡易ルート] (オプション)**: これは、Office 365 ネットワークに対する専用のプライベートな接続を提供する、全体的なネットワークの一部であるネットワークセグメントです。</span><span class="sxs-lookup"><span data-stu-id="9be3c-134">**Express Route (optional)**: This is the network segment that is part of your overall network that will give you a dedicated, private connection to the Office 365 network.</span></span>

### <a name="types-of-traffic"></a><span data-ttu-id="9be3c-135">トラフィックのタイプ</span><span class="sxs-lookup"><span data-stu-id="9be3c-135">Types of traffic</span></span>

<span data-ttu-id="9be3c-136">**リアルタイムメディア**: RTP (リアルタイムトランスポートプロトコル) 内にカプセル化されたデータで、オーディオ、ビデオ、画面共有のワークロードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="9be3c-136">**Real-time media**: Data encapsulated within RTP (Real-time Transport Protocol) that supports audio, video and screen sharing workloads.</span></span> <span data-ttu-id="9be3c-137">通常、メディアトラフィックは非常に待機時間が高いため、このトラフィックは可能な限り多くのパスを使用し、トランスポート層プロトコルとして UDP または TCP を使うことをお勧めします。これは、品質の観点から対話的なリアルタイムメディアを作成するための最適なトランスポートです。.</span><span class="sxs-lookup"><span data-stu-id="9be3c-137">In general, media traffic is highly latency sensitive, so you would want this traffic to take the most direct path possible, and to use UDP versus TCP as the transport layer protocol, which is the best transport for interactive real time media from a quality perspective.</span></span> <span data-ttu-id="9be3c-138">(注: 最後の手段として、メディアには TCP/IP を使用できます。また、HTTP プロトコル内でトンネリングすることもできますが、品質への影響が不適切なため、お勧めしません。)RTP フローは SRTP を介してセキュリティ保護され、ペイロードのみが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-138">(Note: As a last resort, media can use TCP/IP and also be tunneled within the HTTP protocol, but it is not recommended due to bad quality implications.) RTP flow is secured via SRTP, in which only the payload is encrypted.</span></span>

<span data-ttu-id="9be3c-139">**シグナリング**: クライアントとサーバーの間の通信リンク、またはアクティビティ (通話の開始時など) を制御するために使用される他のクライアント。</span><span class="sxs-lookup"><span data-stu-id="9be3c-139">**Signaling**: The communication link between the client and server, or other clients that are used to control activities (for example, when a call is initiated), and deliver instant messages.</span></span> <span data-ttu-id="9be3c-140">ほとんどのシグナルトラフィックでは、HTTPS ベースの REST インターフェイスが使用されますが、シナリオによっては (たとえば、Office 365 とセッション境界コントローラー間の接続)、SIP プロトコルを使います。</span><span class="sxs-lookup"><span data-stu-id="9be3c-140">Most signaling traffic uses the HTTPS-based REST interfaces, though in some scenarios (for example, connection between Office 365 and a Session Border Controller) it uses SIP protocol.</span></span> <span data-ttu-id="9be3c-141">このトラフィックは待ち時間に非常に敏感であることを理解しておく必要がありますが、エンドポイント間の待機時間が数秒を超えると、サービスが停止したり、タイムアウトしたりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9be3c-141">It's important to understand that this traffic is much less sensitive to latency but may cause service outages or call timeouts if latency between the endpoints exceeds several seconds.</span></span> 

### <a name="connectivity-to-office-365"></a><span data-ttu-id="9be3c-142">Office 365 への接続</span><span class="sxs-lookup"><span data-stu-id="9be3c-142">Connectivity to Office 365</span></span>

<span data-ttu-id="9be3c-143">チーム[にはインターネットへの接続](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10)が必要。</span><span class="sxs-lookup"><span data-stu-id="9be3c-143">Teams requires [connectivity to the Internet](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10).</span></span> <span data-ttu-id="9be3c-144">Teams のエンドポイント Url と IP アドレス範囲は、 [Office 365 url と ip アドレス範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)に記載されています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-144">Teams endpoint URLs and IP address ranges are listed in [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> <span data-ttu-id="9be3c-145">(注: TCP ポート80および443への接続を開き、UDP ポート3478から3481への接続が必要です。)さらに、Teams は Skype for Business Online に依存しているため、インターネットにも接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9be3c-145">(Note: Open connectivity to TCP ports 80 and 443, and to UDP ports 3478 through 3481 is required.) Furthermore, Teams has a dependency on Skype for Business Online, which must also be connected to the Internet.</span></span>

<span data-ttu-id="9be3c-146">Teams メディアフロー接続は、標準の IETF ICE (対話型接続の確立) 手順によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-146">Teams media flows connectivity is implemented via standard IETF ICE (Interactive Connectivity Establishment) procedures.</span></span>

### <a name="interoperability-restrictions"></a><span data-ttu-id="9be3c-147">相互運用性の制限</span><span class="sxs-lookup"><span data-stu-id="9be3c-147">Interoperability restrictions</span></span>
<span data-ttu-id="9be3c-148">**サードパーティメディアリレー**: teams メディアフロー (つまり、teams のエンドポイントの1つ) は、teams または Skype for business のネイティブメディアリレーのみをスキャンする場合があります。</span><span class="sxs-lookup"><span data-stu-id="9be3c-148">**Third party media relays**: A Teams media flow (that is, one of the media endpoints is Teams) may traverse only Teams or Skype for Business native media relays.</span></span> <span data-ttu-id="9be3c-149">サードパーティメディアリレーとの相互運用性はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9be3c-149">Interoperability with a third party media relay is not supported.</span></span> <span data-ttu-id="9be3c-150">(注: PSTN でのサードパーティの SBC は、RTP/RTCP ストリームを終了して、SRTP 経由でセキュアであり、次のホップにはリレーしません。)</span><span class="sxs-lookup"><span data-stu-id="9be3c-150">(Note: A third party SBC on the boundary with PSTN must terminate RTP/RTCP stream, secured via SRTP, and not relay it to the next hop.)</span></span>

<span data-ttu-id="9be3c-151">**サードパーティの sip プロキシサーバー**: サードパーティの SBC やゲートウェイを使用した sip ダイアログの通知は、teams または Skype for business のネイティブ SIP プロキシによって発生します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-151">**Third party SIP proxy servers**: A Teams signaling SIP dialog with a third party SBC and/or gateway may traverse Teams or Skype for Business native SIP proxies.</span></span> <span data-ttu-id="9be3c-152">サードパーティの SIP プロキシとの相互運用性はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9be3c-152">Interoperability with a third party SIP proxy is not supported.</span></span>

<span data-ttu-id="9be3c-153">**サードパーティ B2BUA (つまり、SBC)**: PSTN との間の Teams メディアフローは、サードパーティの SBC によって終了します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-153">**Third party B2BUA (that is, SBC)**: A Teams media flow from/to the PSTN is terminated by a third party SBC.</span></span> <span data-ttu-id="9be3c-154">ただし、Teams ネットワーク内のサードパーティの SBC との相互運用性 (つまり、サードパーティの SBC の1つのチームと Skype for Business エンドポイントの両方) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9be3c-154">However, interoperability with a third party SBC within the Teams network (that is, a third party SBC mediates two Teams/Skype for Business endpoints) is not supported.</span></span>

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a><span data-ttu-id="9be3c-155">Microsoft Teams で推奨されないテクノロジ</span><span class="sxs-lookup"><span data-stu-id="9be3c-155">Technologies that are not recommended with Microsoft Teams</span></span>

<span data-ttu-id="9be3c-156">**VPN ネットワーク**: メディアトラフィックには推奨されません (つまり、flow 2 ')。</span><span class="sxs-lookup"><span data-stu-id="9be3c-156">**VPN network**: It is not recommended for media traffic (that is, flow 2').</span></span> <span data-ttu-id="9be3c-157">VPN クライアントは、で指定されているようにhttps://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/、境界 vpn を使用し、メディアトラフィックをルーティングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9be3c-157">The VPN client should use split VPN and route media traffic like any external non-VPN user, as specified in https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/.</span></span>

><span data-ttu-id="9be3c-158">**注**: タイトルは Lync でも、チームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-158">**Note**: Although the title is Lync, it is applicable to Teams as well.</span></span>

<span data-ttu-id="9be3c-159">**パケット**デバイス: どのような種類のパケット snippers、パケット検査、またはパケット shaper デバイスは推奨されません。また、品質が大幅に低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9be3c-159">**Packet shapers**: Any kind of packet snippers, packet inspection, or packet shaper devices are not recommended and may degrade quality significantly.</span></span> 

### <a name="principles"></a><span data-ttu-id="9be3c-160">指針</span><span class="sxs-lookup"><span data-stu-id="9be3c-160">Principles</span></span>
<span data-ttu-id="9be3c-161">Microsoft Teams のコールフローを理解するのに役立つ4つの一般的な原則があります。</span><span class="sxs-lookup"><span data-stu-id="9be3c-161">There are four general principles that help you understand call flows for Microsoft Teams:</span></span>
 
1.  <span data-ttu-id="9be3c-162">Microsoft Teams の会議は、最初の参加者が参加したのと同じ地域で Office 365 によってホストされています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-162">A Microsoft Teams conference is hosted by Office 365 in the same region where the first participant joined.</span></span> <span data-ttu-id="9be3c-163">(注: 一部のトポロジでこの規則の例外が発生する場合は、このドキュメントで説明されていて、適切なコールフローで示されています。)</span><span class="sxs-lookup"><span data-stu-id="9be3c-163">(Note: If there will be exceptions to this rule in some topologies, then they will be described in this document, and illustrated by an appropriate call flow.)</span></span>

2.  <span data-ttu-id="9be3c-164">Office 365 の Teams メディアエンドポイントは、通話の種類に基づくメディア処理のニーズに基づいて使用されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-164">A Teams media endpoint in Office 365 is used based on media processing needs and not based on call type.</span></span> <span data-ttu-id="9be3c-165">(たとえば、ポイントツーポイントの通話では、クラウドのメディアエンドポイントを使用して、議事録や記録のためにメディアの処理を行うことができます。参加者が2人の会議では、クラウドのメディアエンドポイントを使用することはできません)。ただし、ほとんどの会議では、会議がホストされている場所に割り当てられる、ミキシングとルーティングの目的でメディアエンドポイントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-165">(For example, a point-to-point call may use a media endpoint in the cloud to process media for transcription and/or recording, while a conference with two participants may not use any media endpoint in the cloud.) However, most conferences will use a media endpoint for mixing and routing purposes, allocated where the conference is hosted.</span></span> <span data-ttu-id="9be3c-166">顧客のネットワークファイアウォールの制限により、クライアントからメディアエンドポイントに送信されたメディアトラフィックが直接ルーティングされる場合や、必要に応じて、Office 365 でトランスポートリレーを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="9be3c-166">The media traffic sent from a client to the media endpoint may be routed directly or use a Transport Relay in Office 365 if required due to customer network firewall restrictions.</span></span> 

3.  <span data-ttu-id="9be3c-167">ピアツーピア通話のメディアトラフィックは、電話がクラウドでメディアエンドポイントを必要としないことを前提として、利用可能な最も直接的なルートを受け取ります (上記の #2 を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9be3c-167">Media traffic for peer-to-peer calls take the most direct route that is available, assuming that the call doesn't mandate a media endpoint in the cloud (see #2 above).</span></span> <span data-ttu-id="9be3c-168">優先ルートはリモートピア (クライアント) に直接送信されますが、そのルートが利用できない場合は、1つ以上のトランスポートリレーがトラフィックを中継します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-168">The preferred route is direct to the remote peer (client), but if that route isn't available, then one or more Transport Relays will relay traffic.</span></span> <span data-ttu-id="9be3c-169">メディアトラフィックは、メディアの品質に影響を与えるため、パケットコントローラー、VPN サーバーなどの横にあるサーバーではないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9be3c-169">It is recommended that media traffic shall not transverse servers such as packet shapers, VPN servers, and so on, since this will impact the media quality.</span></span>

4.  <span data-ttu-id="9be3c-170">シグナリングトラフィックは、常に最も近いサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-170">Signaling traffic always goes to the closest server to the user.</span></span> 

<span data-ttu-id="9be3c-171">選択されているメディアパスの詳細については、をhttps://www.youtube.com/watch?v=1tmHMIlAQdo参照してください。</span><span class="sxs-lookup"><span data-stu-id="9be3c-171">To learn more about the details on the media path that is chosen, see https://www.youtube.com/watch?v=1tmHMIlAQdo.</span></span>

## <a name="call-flows-in-various-topologies"></a><span data-ttu-id="9be3c-172">さまざまなトポロジでのコールフロー</span><span class="sxs-lookup"><span data-stu-id="9be3c-172">Call flows in various topologies</span></span>
### <a name="teams-topology"></a><span data-ttu-id="9be3c-173">Teams のトポロジ</span><span class="sxs-lookup"><span data-stu-id="9be3c-173">Teams topology</span></span>
<span data-ttu-id="9be3c-174">このトポロジは、Skype for Business Server や電話システムの直接ルーティングなど、オンプレミスの展開がなくてもクラウドから Teams サービスを利用する顧客によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-174">This topology is used by customers that leverage Teams services from the cloud without any on-premises deployment, such as Skype for Business Server or Phone System Direct Routing.</span></span> <span data-ttu-id="9be3c-175">さらに、Office 365 へのインターフェイスは、Azure Express Route を使わずにインターネット経由で行われます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-175">In addition, the interface to Office 365 is done via the Internet without Azure Express Route.</span></span> 

<span data-ttu-id="9be3c-176">[![Microsoft Teams Online の通話フロー図01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-176">[![Microsoft Teams Online Call Flows Figure 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span></span>

<span data-ttu-id="9be3c-177">*図 1-Teams のトポロジ*</span><span class="sxs-lookup"><span data-stu-id="9be3c-177">*Figure 1 - Teams topology*</span></span>

<span data-ttu-id="9be3c-178">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9be3c-178">Note that:</span></span>

- <span data-ttu-id="9be3c-179">上の図の矢印の方向は、企業境界での接続に影響を与える通信の開始方向を反映しています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-179">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="9be3c-180">メディア用に UDP の場合は、最初のパケットが逆方向に流れる場合がありますが、これらのパケットは、他の方向のパケットが流れるまでブロックされることがあります。</span><span class="sxs-lookup"><span data-stu-id="9be3c-180">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>
- <span data-ttu-id="9be3c-181">Teams は Skype for Business Online と並行して展開されるため、クライアントは "Teams/SFB ユーザー" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-181">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user".</span></span>

<span data-ttu-id="9be3c-182">詳細については、次の記事の後のオプションのトポロジを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9be3c-182">You can find more information on the following optional topologies later in the article:</span></span>

- <span data-ttu-id="9be3c-183">Skype for Business のオンプレミスの展開については、「 **Teams ハイブリッドトポロジ**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9be3c-183">Skype for Business on-premises deployment is described in **Teams  hybrid topology**.</span></span>
- <span data-ttu-id="9be3c-184">電話システムの直接ルーティング (PSTN 接続用) については、「**ダイレクトルーティングトポロジを使用した Teams**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9be3c-184">Phone System Direct Routing (for PSTN connectivity) is described in **Teams with Direct Routing topology**.</span></span>
- <span data-ttu-id="9be3c-185">エクスプレスルートについては、「 **Express route の最適化」を**参照してください。</span><span class="sxs-lookup"><span data-stu-id="9be3c-185">Express Route is described in  **Teams with Express Route optimization**.</span></span>

<span data-ttu-id="9be3c-186">**フローの説明**:</span><span class="sxs-lookup"><span data-stu-id="9be3c-186">**Flow descriptions**:</span></span>
- <span data-ttu-id="9be3c-187">**フロー 2** –ユーザーのチームエクスペリエンスの一部として、顧客ネットワーク上のユーザーによって開始されたフローを表します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-187">**Flow 2** – Represents a flow initiated by a user on the customer network to the Internet as a part of the user's Teams experience.</span></span> <span data-ttu-id="9be3c-188">これらのフローの例としては、DNS とピアツーピアメディアがあります。</span><span class="sxs-lookup"><span data-stu-id="9be3c-188">Examples of these flows are DNS and peer-to-peer media.</span></span>
- <span data-ttu-id="9be3c-189">**フロー 2 '** –リモートのモバイルチームユーザーによって開始されたフロー (顧客ネットワークへの VPN を含む) を表します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-189">**Flow 2'** – Represents a flow initiated by a remote mobile Teams user, with VPN to the customer network.</span></span> 
- <span data-ttu-id="9be3c-190">**フロー 3** –リモートのモバイルチームユーザーによって開始されたフロー (Office 365 またはチームのエンドポイント) を表します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-190">**Flow 3** – Represents a flow initiated by a remote mobile Teams user to Office 365/Teams endpoints.</span></span> 
- <span data-ttu-id="9be3c-191">**フロー 4** –顧客ネットワーク上のユーザーによって開始されたフロー (Office 365 またはチームのエンドポイント) を表します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-191">**Flow 4** – Represents a flow initiated by a user on the customer network to Office 365/Teams endpoints.</span></span>
- <span data-ttu-id="9be3c-192">**フロー 5** – teams ユーザーと別のチームまたは顧客ネットワーク内の Skype for business ユーザーとの間のピアツーピアメディアフローを表します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-192">**Flow 5** – Represents a peer-to-peer media flow between a Teams user and another Teams or Skype for Business user within the customer network.</span></span>
- <span data-ttu-id="9be3c-193">**フロー 6** –リモートのモバイルチームユーザーと別のリモートモバイルチーム、またはインターネット上の Skype for business ユーザーとの間のピアツーピアメディアフローを表します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-193">**Flow 6** – Represents a peer-to-peer media flow between a remote mobile Teams user and another remote mobile Teams or Skype for Business user over the Internet.</span></span>

#### <a name="use-case-one-to-one"></a><span data-ttu-id="9be3c-194">ユースケース: 1 対1</span><span class="sxs-lookup"><span data-stu-id="9be3c-194">Use case: One-to-one</span></span>
<span data-ttu-id="9be3c-195">1対1の通話では、発信者が IP アドレス/ポート (中継によって表示されるクライアントのパブリック IP アドレスを含む) で構成される一連の候補を取得する共通モデルを使います。</span><span class="sxs-lookup"><span data-stu-id="9be3c-195">One-to-one calls use a common model in which the caller will obtain a set of candidates consisting of IP addresses/ports--including local, relay, and reflexive (public IP address of client as seen by the relay) candidates.</span></span> <span data-ttu-id="9be3c-196">発信者は、これらの候補を、通話先に送信します。また、同様の候補を取得し、呼び出し元に送信します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-196">The caller sends these candidates to the called party; the called party also obtains a similar set of candidates and sends them to the caller.</span></span> <span data-ttu-id="9be3c-197">STUN connectivity のチェックメッセージは、どの発信者/通話相手側メディアパスが機能し、最適な作業パスが選択されているかを確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-197">STUN connectivity check messages are used to find which caller/called party media paths work, and the best working path is selected.</span></span> <span data-ttu-id="9be3c-198">メディア (つまり、SRTP 経由で保護されている RTP/RTCP パケット) は、選択した候補ペアを使って送信されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-198">Media (that is, RTP/RTCP packets secured via SRTP) are then sent using the selected candidate pair.</span></span> <span data-ttu-id="9be3c-199">トランスポートリレーは、Office 365 の一部として展開されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-199">The Transport relay is deployed as part of Office 365.</span></span>

<span data-ttu-id="9be3c-200">ローカル IP アドレス/ポート候補または再帰的候補が接続されている場合は、メディアのためにクライアント (または NAT 経由) 間の直接パスが選択されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-200">If the local IP address/port candidates or the reflexive candidates have connectivity, then the direct path between the clients (or via a NAT) will be selected for media.</span></span> <span data-ttu-id="9be3c-201">クライアントが顧客ネットワーク上にある場合は、ダイレクトパスを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9be3c-201">If the clients are both on the customer network, then the direct path should be selected.</span></span> <span data-ttu-id="9be3c-202">これには、お客様のネットワーク内で直接の UDP 接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="9be3c-202">This requires direct UDP connectivity within the customer network.</span></span> <span data-ttu-id="9be3c-203">クライアントが両方とも nomadic クラウドユーザーである場合は、NAT/ファイアウォールによっては、メディアに直接接続が使用されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9be3c-203">If the clients are both nomadic cloud users, then depending on the NAT/firewall, media may use direct connectivity.</span></span>

<span data-ttu-id="9be3c-204">1つのクライアントが顧客ネットワーク上にあり、一方が外部 (たとえば、モバイルクラウドユーザー) のクライアントである場合は、ローカルまたは再帰の候補の間の直接接続が機能していることはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="9be3c-204">If one client is internal on the customer network and one client is external (for example, a mobile cloud user), then it is unlikely that direct connectivity between the local or reflexive candidates is working.</span></span> <span data-ttu-id="9be3c-205">この場合は、いずれかのクライアントからトランスポートリレーの候補の1つを使用することをお勧めします (たとえば、内部クライアントは、Office 365 のトランスポートリレーからリレー候補を取得している必要があります)。外部クライアントは、トランスポートリレー)。</span><span class="sxs-lookup"><span data-stu-id="9be3c-205">In this case, an option is to use one of the Transport Relay candidates from either client (for example, the internal client obtained a relay candidate from the Transport relay in Office 365; the external client needs to be able to send STUN/RTP/RTCP packets to the transport relay).</span></span> <span data-ttu-id="9be3c-206">別の方法として、内部クライアントが、モバイルクラウドクライアントによって取得された relay 候補に送信されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-206">Another option is the internal client sends to the relay candidate obtained by the mobile cloud client.</span></span> <span data-ttu-id="9be3c-207">メディアの UDP 接続は強くお勧めしますが、TCP はサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-207">Note that, although UDP connectivity for media is highly recommended, TCP is supported.</span></span>

<span data-ttu-id="9be3c-208">**高レベルの手順**:</span><span class="sxs-lookup"><span data-stu-id="9be3c-208">**High-level steps**:</span></span>
1. <span data-ttu-id="9be3c-209">Teams ユーザー A は flow2 経由で URL ドメイン名 (DNS) を解決します</span><span class="sxs-lookup"><span data-stu-id="9be3c-209">Teams User A resolves URL domain name (DNS) via flow2</span></span>
2. <span data-ttu-id="9be3c-210">Teams ユーザー A は、flow 4 経由で Teams トランスポートリレーにメディアリレーポートを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-210">Teams User A allocates a media Relay port on Teams Transport Relay via flow 4</span></span>
3. <span data-ttu-id="9be3c-211">Teams ユーザー A は、フロー4から Office 365 への "招待" を ICE 候補と共に送信します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-211">Teams User A sends "invite" with ICE candidates via flow 4 to Office 365</span></span>
4. <span data-ttu-id="9be3c-212">Office 365 は、フロー4を通じてチームユーザー B に通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-212">Office 365 sends notification to Teams User B via flow 4</span></span>
5. <span data-ttu-id="9be3c-213">Teams ユーザー B は、flow 4 経由で Teams トランスポートリレーにメディアリレーポートを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-213">Teams User B allocates a media Relay port on Teams Transport Relay via flow 4</span></span>
6. <span data-ttu-id="9be3c-214">チームユーザー B は、フロー4を通じて ICE 候補を使って "answer" を送信します。フロー4では、チームユーザー A に転送されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-214">Teams User B sends "answer" with ICE candidates via flow 4, which is forwarded back to Teams User A via Flow 4</span></span>
7. <span data-ttu-id="9be3c-215">Teams ユーザー A と Teams ユーザー B が ICE 接続テストを呼び出し、最適なメディアパスが選択されています (さまざまなユースケースについては、以下の図を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9be3c-215">Teams User A and Teams User B invoke ICE connectivity tests and the best available media path is selected (see diagrams below for various use cases)</span></span>
8. <span data-ttu-id="9be3c-216">チームユーザーは、フロー4を通じて Office 365 にテレメトリを送信します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-216">Teams Users send telemetry to Office 365 via flow 4</span></span>

<span data-ttu-id="9be3c-217">**顧客ネットワーク内:**</span><span class="sxs-lookup"><span data-stu-id="9be3c-217">**Within customer network:**</span></span>

<span data-ttu-id="9be3c-218">[![Microsoft Teams Online の通話フロー図02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-218">[![Microsoft Teams Online Call Flows Figure 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span></span>

<span data-ttu-id="9be3c-219">*図 2-顧客ネットワーク内*</span><span class="sxs-lookup"><span data-stu-id="9be3c-219">*Figure 2 - Within customer network*</span></span>
 
<span data-ttu-id="9be3c-220">手順7では、ピアツーピアメディアフロー5が選択されています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-220">In step 7, peer-to-peer media flow 5 is selected.</span></span>
 
<span data-ttu-id="9be3c-221">メディアは双方向です。</span><span class="sxs-lookup"><span data-stu-id="9be3c-221">Media is bidirectional.</span></span> <span data-ttu-id="9be3c-222">フロー5の方向は、このドキュメント内のすべてのフローと一貫性のある接続の観点から、1つのサイドが通信を開始することを示します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-222">The direction of flow 5 indicates that one side initiates the communication from a connectivity perspective, consistent with all the flows in this document.</span></span> <span data-ttu-id="9be3c-223">この場合、どちらのエンドポイントも顧客のネットワーク内にあるため、どの方向を使用するかは関係ありません。</span><span class="sxs-lookup"><span data-stu-id="9be3c-223">In this case, it doesn't matter which direction is used because both endpoints are within the customer network.</span></span>

<span data-ttu-id="9be3c-224">**外部ユーザーに対する顧客ネットワーク (メディアトランスポートリレーによって中継されるメディア):**</span><span class="sxs-lookup"><span data-stu-id="9be3c-224">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="9be3c-225">[![Microsoft Teams Online の通話フロー図03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-225">[![Microsoft Teams Online Call Flows Figure 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span></span>

<span data-ttu-id="9be3c-226">*図 3-外部ユーザーへの顧客ネットワーク (Teams トランスポートリレーによるメディアの中継)*</span><span class="sxs-lookup"><span data-stu-id="9be3c-226">*Figure 3 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>
 
<span data-ttu-id="9be3c-227">手順7では、[顧客ネットワーク] から [Office 365] のフロー3、[リモートモバイルチームユーザーから Office 365 へのフロー 3] が選択されています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-227">In step 7, flow 4, from customer network to Office 365, and flow 3, from remote mobile Teams user to Office 365, are selected.</span></span> <span data-ttu-id="9be3c-228">これらのフローは、Office 365 内の Teams トランスポートリレーによって中継されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-228">These flows are relayed by Teams Transport Relay within Office 365.</span></span>

<span data-ttu-id="9be3c-229">[メディア] は、双方向で接続の観点から通信を開始する側を示します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-229">Media is bidirectional, where direction indicates which side initiates the communication from a connectivity perspective.</span></span> <span data-ttu-id="9be3c-230">この場合、これらのフローは、さまざまなトランスポートプロトコルとアドレスを使って、シグナリングとメディアに使用されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-230">In this case, these flows are used for signaling and media, via different transport protocols and addresses.</span></span>

<span data-ttu-id="9be3c-231">**外部ユーザー (ダイレクトメディア) に対する顧客ネットワーク:**</span><span class="sxs-lookup"><span data-stu-id="9be3c-231">**Customer network to external user (direct media):**</span></span>

<span data-ttu-id="9be3c-232">[![Microsoft Teams Online の通話フロー図04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-232">[![Microsoft Teams Online Call Flows Figure 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span></span>

<span data-ttu-id="9be3c-233">*図 4-外部ユーザー (ダイレクトメディア) に対する顧客ネットワーク*</span><span class="sxs-lookup"><span data-stu-id="9be3c-233">*Figure 4 - Customer network to external user (direct media)*</span></span>
 
<span data-ttu-id="9be3c-234">手順7では、[顧客ネットワークからインターネット (クライアントのピア) へのフロー 2] が選択されています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-234">In step 7, flow 2, from customer network to Internet (client's peer), is selected.</span></span>
- <span data-ttu-id="9be3c-235">リモートモバイルユーザー (Office 365 経由で中継されない) のダイレクトメディアはオプションです。</span><span class="sxs-lookup"><span data-stu-id="9be3c-235">Direct media with remote mobile user (that is, not relayed through Office 365) is optional.</span></span> <span data-ttu-id="9be3c-236">つまり、お客様は、このパスをブロックして、Office 365 でトランスポートリレー経由でメディアパスを強制することができます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-236">In other words, customer may block this path to enforce a media path through Transport Relay in Office 365.</span></span>

- <span data-ttu-id="9be3c-237">メディアは双方向です。</span><span class="sxs-lookup"><span data-stu-id="9be3c-237">Media is bidirectional.</span></span> <span data-ttu-id="9be3c-238">フロー2からリモートモバイルユーザーまでの方向は、一方のサイドが接続の観点から通信を開始することを示します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-238">The direction of flow 2 to remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span> 

<span data-ttu-id="9be3c-239">**内部ユーザーに対する VPN ユーザー (Teams トランスポートリレーによって中継されるメディア)**</span><span class="sxs-lookup"><span data-stu-id="9be3c-239">**VPN user to internal user (media relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="9be3c-240">[![Microsoft Teams Online の通話フロー図05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-240">[![Microsoft Teams Online Call Flows Figure 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span></span>

<span data-ttu-id="9be3c-241">*図 5-内部ユーザーに対する VPN ユーザー (Teams トランスポートリレーによって中継されるメディア)*</span><span class="sxs-lookup"><span data-stu-id="9be3c-241">*Figure 5 - VPN user to internal user (media relayed by Teams Transport Relay)*</span></span>
 
<span data-ttu-id="9be3c-242">VPN と顧客ネットワークとの間のシグナリングはフロー2で行われています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-242">Signaling between the VPN to the customer network is via flow 2'.</span></span> <span data-ttu-id="9be3c-243">顧客ネットワークと Office 365 間のシグナリングはフロー4経由で行われます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-243">Signaling between the customer network and Office 365 is via flow 4.</span></span> <span data-ttu-id="9be3c-244">ただし、メディアは VPN をバイパスし、Office 365 の Teams メディアリレーを通じて、フロー3と4を介してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-244">However, media bypasses the VPN and is routed via flows 3 and 4 through Teams media relay in Office 365.</span></span>

<span data-ttu-id="9be3c-245">**内部ユーザー (ダイレクトメディア) に対する VPN ユーザー**</span><span class="sxs-lookup"><span data-stu-id="9be3c-245">**VPN user to internal user (direct media)**</span></span>

<span data-ttu-id="9be3c-246">[![Microsoft Teams Online の通話フロー図06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-246">[![Microsoft Teams Online Call Flows Figure 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span></span>

<span data-ttu-id="9be3c-247">*図 6-VPN ユーザーと内部ユーザー (ダイレクトメディア)*</span><span class="sxs-lookup"><span data-stu-id="9be3c-247">*Figure 6 - VPN user to internal user (direct media)*</span></span>

<span data-ttu-id="9be3c-248">VPN と顧客ネットワークとの間のシグナリングはフロー2で行われています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-248">Signaling between the VPN to the customer network is via flow 2'.</span></span> <span data-ttu-id="9be3c-249">顧客ネットワークと Office 365 間のシグナリングはフロー4経由で行われます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-249">Signaling between the customer network and Office 365 is via flow 4.</span></span> <span data-ttu-id="9be3c-250">ただし、メディアは VPN をバイパスし、ユーザーのネットワークからインターネットへのフロー2経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-250">However, media bypasses the VPN and is routed via flow 2 from the customer network to the Internet.</span></span>

<span data-ttu-id="9be3c-251">メディアは双方向です。</span><span class="sxs-lookup"><span data-stu-id="9be3c-251">Media is bidirectional.</span></span> <span data-ttu-id="9be3c-252">リモートモバイルユーザーのフロー2の方向は、一方のサイドが接続の観点から通信を開始することを示します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-252">The direction of flow 2 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

<span data-ttu-id="9be3c-253">**外部ユーザー (ダイレクトメディア) に対する VPN ユーザー**</span><span class="sxs-lookup"><span data-stu-id="9be3c-253">**VPN user to external user (direct media)**</span></span>

<span data-ttu-id="9be3c-254">[![Microsoft Teams の通話フロー図07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-254">[![Microsoft Teams call flows Figure 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span></span>

<span data-ttu-id="9be3c-255">*図 7-VPN ユーザーから外部ユーザーへの接続 (ダイレクトメディア)*</span><span class="sxs-lookup"><span data-stu-id="9be3c-255">*Figure 7 - VPN user to external user (direct media)*</span></span>

<span data-ttu-id="9be3c-256">VPN ユーザーと顧客ネットワークとの間のシグナリングは、フロー2から、フロー4から Office 365 までの間で行われます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-256">Signaling between the VPN user to the customer network is via flow 2' and via flow 4 to Office 365.</span></span> <span data-ttu-id="9be3c-257">ただし、メディアは VPN をバイパスし、フロー6経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-257">However, media bypasses VPN and is routed via flow 6.</span></span>

<span data-ttu-id="9be3c-258">メディアは双方向です。</span><span class="sxs-lookup"><span data-stu-id="9be3c-258">Media is bidirectional.</span></span> <span data-ttu-id="9be3c-259">リモートモバイルユーザーへのフロー6の方向は、一方のサイドが接続の観点から通信を開始することを示します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-259">The direction of flow 6 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a><span data-ttu-id="9be3c-260">使用例: Office 365 トランク経由でのチームと PSTN</span><span class="sxs-lookup"><span data-stu-id="9be3c-260">Use Case: Teams to PSTN through Office 365 Trunk</span></span>
<span data-ttu-id="9be3c-261">Office 365 には、公衆交換電話網 (PSTN) での通話の発信と受信を可能にする電話システムがあります。</span><span class="sxs-lookup"><span data-stu-id="9be3c-261">Office 365 has a Phone System that allows placing and receiving calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="9be3c-262">PSTN トランクが電話システムの通話プランによって接続されている場合、このユースケースには特別な接続要件はありません。</span><span class="sxs-lookup"><span data-stu-id="9be3c-262">If the PSTN trunk is connected via the Phone System Calling Plan, then there are no special connectivity requirements for this use case.</span></span> <span data-ttu-id="9be3c-263">(独自のオンプレミス PSTN トランクを Office 365 に接続する場合は、電話システムのダイレクトルーティングを使うことができます)。</span><span class="sxs-lookup"><span data-stu-id="9be3c-263">(If you want to connect your own on-premises PSTN trunk to Office 365, you can use Phone System Direct Routing.)</span></span>

<span data-ttu-id="9be3c-264">[![Microsoft Teams Online の通話フロー図08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-264">[![Microsoft Teams Online Call Flows Figure 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span></span>

<span data-ttu-id="9be3c-265">*図 8-Office 365 トランク経由のチーム間の PSTN*</span><span class="sxs-lookup"><span data-stu-id="9be3c-265">*Figure 8 - Teams to PSTN through Office 365 Trunk*</span></span>

#### <a name="use-case-teams-meeting"></a><span data-ttu-id="9be3c-266">使用例: Teams 会議</span><span class="sxs-lookup"><span data-stu-id="9be3c-266">Use Case: Teams Meeting</span></span>

<span data-ttu-id="9be3c-267">音声/ビデオ/画面共有 (VBSS) 会議サーバーは、Office 365 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-267">The audio/video/screen sharing (VBSS) conferencing server is part of Office 365.</span></span> <span data-ttu-id="9be3c-268">これには、顧客ネットワークから到達可能である必要があり、Nomadic Cloud クライアントから到達可能である必要があるパブリック IP アドレスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-268">It has a public IP address that must be reachable from the customer network and must be reachable from a Nomadic Cloud client.</span></span> <span data-ttu-id="9be3c-269">クライアント/エンドポイントごとに、会議サーバーに接続できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9be3c-269">Each client/endpoint needs to be able to connect to the conferencing server.</span></span>

<span data-ttu-id="9be3c-270">内部クライアントでは、1対1の通話の場合と同じ方法で、ローカル、再帰、およびリレーの候補が取得されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-270">Internal clients will obtain local, reflexive, and relay candidates in the same manner as described for one-to-one calls.</span></span> <span data-ttu-id="9be3c-271">クライアントは、招待状にこれらの候補を会議サーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-271">The clients will send these candidates to the conferencing server in an invite.</span></span> <span data-ttu-id="9be3c-272">会議サーバーは、公開された IP アドレスを持っているため、relay を使用しません。そのため、ローカル IP アドレス候補で応答します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-272">The conferencing server does not use a relay since it has a publicly reachable IP address, so it responds with its local IP address candidate.</span></span> <span data-ttu-id="9be3c-273">クライアントと会議サーバーは、1対1の通話の場合と同じ方法で接続性を確認します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-273">The client and conferencing server will check connectivity in the same manner described for one-to-one calls.</span></span> 

<span data-ttu-id="9be3c-274">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9be3c-274">Note that:</span></span>

- <span data-ttu-id="9be3c-275">Teams クライアントは Skype for Business 会議に参加できず、Skype for Business クライアントは Teams 会議に参加できません。</span><span class="sxs-lookup"><span data-stu-id="9be3c-275">Teams clients cannot join Skype for Business meetings, and Skype for Business clients cannot join Teams meetings.</span></span>

- <span data-ttu-id="9be3c-276">PSTN ユーザーは、会議の開催者の PSTN 通話や会議のプロビジョニングに応じて、"ダイヤルイン" または "ダイヤルアウト" を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-276">A PSTN user optionally "Dials IN" or "Dialed OUT", depending on the meeting's organizer PSTN Calling and/or conferencing provisioning.</span></span> 

- <span data-ttu-id="9be3c-277">ゲストユーザーまたはお客様のユーザーがゲストプライベートネットワークから参加することができます。これは、厳密な規則を使って、FW/NAT で保護されています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-277">A guest user or a customer user may join from a guest private network, which is protected via FW/NAT with strict rules.</span></span>

<span data-ttu-id="9be3c-278">[![Microsoft Teams Online の通話フロー図09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-278">[![Microsoft Teams Online Call Flows Figure 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span></span>

<span data-ttu-id="9be3c-279">*図 9-Teams 会議*</span><span class="sxs-lookup"><span data-stu-id="9be3c-279">*Figure 9 - Teams Meeting*</span></span>

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a><span data-ttu-id="9be3c-280">使用例: オンプレミスの Skype for Business とのフェデレーション</span><span class="sxs-lookup"><span data-stu-id="9be3c-280">Use Case: Federation with Skype for Business on premises</span></span>

<span data-ttu-id="9be3c-281">**Office 365 で Teams トランスポートリレーによって中継されるメディア**</span><span class="sxs-lookup"><span data-stu-id="9be3c-281">**Media relayed by Teams Transport Relay in Office 365**</span></span>

<span data-ttu-id="9be3c-282">[![Microsoft Teams Online の通話フロー図10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-282">[![Microsoft Teams Online Call Flows Figure 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span></span>

<span data-ttu-id="9be3c-283">*図 10-Office 365 で Teams トランスポートリレーによって中継されるメディア*</span><span class="sxs-lookup"><span data-stu-id="9be3c-283">*Figure 10 - Media relayed by Teams Transport Relay in Office 365*</span></span>

<span data-ttu-id="9be3c-284">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9be3c-284">Note that:</span></span>

- <span data-ttu-id="9be3c-285">フェデレーションとは、2つのテナント間の通信を定義することです。</span><span class="sxs-lookup"><span data-stu-id="9be3c-285">Federation is, by definition, a communication between two tenants.</span></span> <span data-ttu-id="9be3c-286">この場合、federates を使用するテナント A は、オンプレミスの Skype for Business を使用するテナント B と共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-286">In this case, tenant A, which uses Teams, federates with tenant B, which uses Skype for Business on premises.</span></span> <span data-ttu-id="9be3c-287">テナント B でも Office 365 を使用している場合、Skype for Business クライアントでは、フロー3を使って Office 365 に接続していました。</span><span class="sxs-lookup"><span data-stu-id="9be3c-287">If tenant B is also using Office 365, then the Skype for Business client would have used flow 3 to connect with Office 365.</span></span>

- <span data-ttu-id="9be3c-288">フェデレーションされた Skype for Business クライアントからオンプレミスの Skype for business Server へのシグナルおよびメディアは、このドキュメントの範囲外です。</span><span class="sxs-lookup"><span data-stu-id="9be3c-288">Signaling and media from the federated Skype for Business client to on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="9be3c-289">ただし、わかりやすくするために、ここで示しています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-289">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="9be3c-290">チームと Skype for Business の間のシグナリングは、Office 365 のゲートウェイによってブリッジされます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-290">Signaling between Teams and Skype for Business is bridged by a gateway in Office 365.</span></span>

- <span data-ttu-id="9be3c-291">このケースのメディアは、Office 365 の Teams トランスポートリレーによって、フロー4経由で顧客ネットワークおよびリモートの Skype for Business クライアントに中継されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-291">Media in this case is relayed by Teams Transport Relay in Office 365 to the customer network and remote Skype for Business client via flow 4.</span></span>

<span data-ttu-id="9be3c-292">**フェデレーションテナントでの Skype for Business メディアリレーによるメディアの中継**</span><span class="sxs-lookup"><span data-stu-id="9be3c-292">**Media relayed by Skype for Business Media Relay in federated tenant**</span></span>

<span data-ttu-id="9be3c-293">[![Microsoft Teams Online の通話フロー図11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-293">[![Microsoft Teams Online Call Flows Figure 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span></span>

<span data-ttu-id="9be3c-294">*図 11-フェデレーションされたテナントでの Skype for Business メディアリレーによるメディアの中継*</span><span class="sxs-lookup"><span data-stu-id="9be3c-294">*Figure 11 - Media relayed by Skype for Business Media Relay in federated tenant*</span></span>

<span data-ttu-id="9be3c-295">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9be3c-295">Note that:</span></span>

- <span data-ttu-id="9be3c-296">フェデレーションされた Skype for Business クライアントから社内の Skype for business Server へのシグナリングとメディアは、このドキュメントの範囲外です。</span><span class="sxs-lookup"><span data-stu-id="9be3c-296">Signaling and media from the federated Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="9be3c-297">ただし、わかりやすくするために、ここで示しています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-297">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="9be3c-298">チームと Skype for Business の間のシグナリングは、Office 365 のゲートウェイによってブリッジされます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-298">Signaling between Teams and Skype for Business is bridged by a Gateway in Office 365.</span></span>

- <span data-ttu-id="9be3c-299">このケースのメディアは、flow 2 経由で Skype for Business のオンプレミスメディアリレーを使って顧客ネットワークに中継されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-299">Media in this case is relayed by Skype for Business on-premises Media Relay to the customer network via flow 2.</span></span> <span data-ttu-id="9be3c-300">(Teams ユーザーからフェデレーションされた顧客ネットワークでのリモートメディアリレーへのトラフィックは、逆方向のトラフィックが流れるまでに、最初にメディアリレーによってブロックされることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="9be3c-300">(Note that traffic from Teams user to the remote Media Relay in the federated customer network will be initially blocked by the Media Relay until traffic in the reverse direction starts to flow.</span></span> <span data-ttu-id="9be3c-301">ただし、双方向フローは両方の方向に接続を開きます。)</span><span class="sxs-lookup"><span data-stu-id="9be3c-301">However, the bidirectional flow will open connectivity in both directions.)</span></span>

<span data-ttu-id="9be3c-302">**Direct (ピアツーピア)**</span><span class="sxs-lookup"><span data-stu-id="9be3c-302">**Direct (peer-to-peer)**</span></span>

<span data-ttu-id="9be3c-303">[![Microsoft Teams Online の通話フロー図12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-303">[![Microsoft Teams Online Call Flows Figure 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span></span>

<span data-ttu-id="9be3c-304">*図 12-直接 (ピアツーピア)*</span><span class="sxs-lookup"><span data-stu-id="9be3c-304">*Figure 12 - Direct (peer-to-peer)*</span></span>

### <a name="teams-hybrid-topology"></a><span data-ttu-id="9be3c-305">Teams ハイブリッドトポロジ</span><span class="sxs-lookup"><span data-stu-id="9be3c-305">Teams hybrid topology</span></span>
<span data-ttu-id="9be3c-306">このトポロジには、Skype for Business のオンプレミス展開を含む Teams が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-306">This topology includes Teams with a Skype for Business on-premises deployment.</span></span>

<span data-ttu-id="9be3c-307">[![Microsoft Teams Online の通話フロー図13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-307">[![Microsoft Teams Online Call Flows Figure 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span></span>

<span data-ttu-id="9be3c-308">*図 13-Teams ハイブリッドトポロジ*</span><span class="sxs-lookup"><span data-stu-id="9be3c-308">*Figure 13 - Teams hybrid topology*</span></span>
 
- <span data-ttu-id="9be3c-309">上の図の矢印の方向は、企業境界での接続に影響を与える通信の開始方向を反映しています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-309">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="9be3c-310">メディア用に UDP の場合は、最初のパケットが逆方向に流れる場合がありますが、これらのパケットは、他の方向のパケットが流れるまでブロックされることがあります。</span><span class="sxs-lookup"><span data-stu-id="9be3c-310">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="9be3c-311">Teams は Skype for Business Online と並行して展開されるため、クライアントは "Teams/SFB ユーザー" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-311">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user".</span></span>

<span data-ttu-id="9be3c-312">追加のフロー (チームのトポロジの上にあります):</span><span class="sxs-lookup"><span data-stu-id="9be3c-312">Additional flows (on top of Teams topology):</span></span>
- <span data-ttu-id="9be3c-313">**フロー 5a** –顧客ネットワーク内の Teams ユーザーと、顧客ネットワーク edge での Skype for business のオンプレミスメディアリレーとの間のピアツーピアメディアフローを表します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-313">**Flow 5A** – Represents a peer-to-peer media flow between a Teams user within the customer network and a Skype for Business on-premises media relay at the customer network edge.</span></span>

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a><span data-ttu-id="9be3c-314">ユースケース: チームと Skype for Business の一対一</span><span class="sxs-lookup"><span data-stu-id="9be3c-314">Use Case: Teams to Skype for Business one-to-one</span></span>
<span data-ttu-id="9be3c-315">**顧客ネットワーク内のハイブリッド**</span><span class="sxs-lookup"><span data-stu-id="9be3c-315">**Hybrid within the customer network**</span></span>

<span data-ttu-id="9be3c-316">[![Microsoft Teams のオンライン通話フロー図14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-316">[![Microsoft Teams Online Call Flows Figure 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span></span>

<span data-ttu-id="9be3c-317">*図 14-顧客ネットワーク内のハイブリッド*</span><span class="sxs-lookup"><span data-stu-id="9be3c-317">*Figure 14 - Hybrid within customer network*</span></span>
 
<span data-ttu-id="9be3c-318">チームと Skype for Business の間のシグナリングは、Office 365 のゲートウェイによってブリッジされます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-318">Signaling between Teams and Skype for Business is bridged by a gateway in Office 365.</span></span> <span data-ttu-id="9be3c-319">ただし、メディアは、フロー5によって顧客ネットワーク内で直接ピアツーピアにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-319">However, media is routed directly peer-to-peer within the customer network via flow 5.</span></span>

<span data-ttu-id="9be3c-320">**外部の Skype for Business ユーザーとのハイブリッド顧客ネットワーク– Office 365 によって中継される**</span><span class="sxs-lookup"><span data-stu-id="9be3c-320">**Hybrid customer network with external Skype for Business user – relayed by Office 365**</span></span>

<span data-ttu-id="9be3c-321">[![Microsoft Teams Online の通話フロー図15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-321">[![Microsoft Teams Online Call Flows Figure 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span></span>

<span data-ttu-id="9be3c-322">*図 15-外部の Skype for Business ユーザーとのハイブリッド顧客ネットワーク (Office 365 による中継)*</span><span class="sxs-lookup"><span data-stu-id="9be3c-322">*Figure 15 - Hybrid customer network with external Skype for Business user - relayed by Office 365*</span></span>

<span data-ttu-id="9be3c-323">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9be3c-323">Note that:</span></span>

- <span data-ttu-id="9be3c-324">Skype for Business クライアントからオンプレミスの Skype for Business Server へのシグナリングとメディアは、このドキュメントの範囲外です。</span><span class="sxs-lookup"><span data-stu-id="9be3c-324">Signaling and media from the Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="9be3c-325">ただし、わかりやすくするために、ここで示しています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-325">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="9be3c-326">チームと Skype for Business の間のシグナリングは、Office 365 のゲートウェイによってブリッジされます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-326">Signaling between Teams and Skype for Business is bridged by a gateway in Office 365.</span></span>

- <span data-ttu-id="9be3c-327">メディアは、Office 365 の Teams トランスポートリレーを通じて、フロー4経由で顧客ネットワークに中継されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-327">Media is relayed through Teams Transport Relay in Office 365 to the customer network through flow 4.</span></span>

<span data-ttu-id="9be3c-328">**外部の Skype for Business ユーザーを使用したハイブリッド顧客ネットワーク-オンプレミスエッジによる中継**</span><span class="sxs-lookup"><span data-stu-id="9be3c-328">**Hybrid customer network with external Skype for Business user – relayed by on-premises Edge**</span></span>

<span data-ttu-id="9be3c-329">[![Microsoft Teams Online の通話フロー図16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-329">[![Microsoft Teams Online Call Flows Figure 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span></span>

<span data-ttu-id="9be3c-330">*図 16-外部の Skype for Business ユーザーを使用したハイブリッド顧客ネットワーク-オンプレミスエッジによる中継*</span><span class="sxs-lookup"><span data-stu-id="9be3c-330">*Figure 16 - Hybrid customer network with external Skype for Business user - relayed by on-premises Edge*</span></span>
 
<span data-ttu-id="9be3c-331">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9be3c-331">Note that:</span></span>

- <span data-ttu-id="9be3c-332">Skype for Business クライアントからオンプレミスの Skype for business Server へのシグナリングとメディアは、このドキュメントの範囲外です。</span><span class="sxs-lookup"><span data-stu-id="9be3c-332">Signaling and media from Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="9be3c-333">ただし、わかりやすくするために、ここで示しています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-333">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="9be3c-334">シグナリングは、Office 365 のゲートウェイでブリッジされます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-334">Signaling is bridged by a gateway in Office 365.</span></span>

- <span data-ttu-id="9be3c-335">メディアは、Skype for Business オンプレミスエッジ内の skype for Business メディアリレーによって、media flow 5A を介して顧客ネットワーク内の Teams ユーザーに中継されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-335">Media is relayed by Skype for Business Media Relay within Skype for Business on-premises Edge to Teams user within the customer network via media flow 5A.</span></span>

### <a name="teams-with-phone-system-direct-routing-topology"></a><span data-ttu-id="9be3c-336">電話システムのダイレクトルーティングトポロジを使用しているチーム</span><span class="sxs-lookup"><span data-stu-id="9be3c-336">Teams with Phone System Direct Routing topology</span></span>
<span data-ttu-id="9be3c-337">このトポロジには、電話システムのダイレクトルーティングを行うチームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-337">This topology includes Teams with Phone System Direct Routing.</span></span> 

<span data-ttu-id="9be3c-338">ダイレクトルーティングでは、サポートされているオンプレミスのユーザー所有のセッションボーダーコントローラー (SBC) ハードウェアデバイスを Office 365 にペアリングし、テレフォニートランクを接続することで、サードパーティの公衆交換電話網 (PSTN) サービスプロバイダーを使用することができます。そのデバイス。</span><span class="sxs-lookup"><span data-stu-id="9be3c-338">Direct Routing enables you to use a third-party Public Switched Telephone Network (PSTN) service provider by pairing a supported on-premises customer-owned Session Border Controller (SBC) hardware device to Office 365, and then connecting the telephony trunk to that device.</span></span> 

<span data-ttu-id="9be3c-339">このシナリオをサポートするには、お客様は Microsoft 認定パートナーの1つから直接ルーティングするための認定された SBC を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9be3c-339">To support this scenario, the customer must deploy a certified SBC for Direct Routing from one of Microsoft's certified partners.</span></span> <span data-ttu-id="9be3c-340">SBC は、ベンダーによって推奨されるように構成する必要があります。また、直接 UDP トラフィック用に Office 365 からルーティングすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-340">The SBC must be configured as recommended by the vendor, and be routable from Office 365 for direct UDP traffic.</span></span> <span data-ttu-id="9be3c-341">メディアは、Teams から直接、または Skype for Business クライアントから SBC (Teams のゲートウェイを経由しない) に、または Teams のゲートウェイを通過する場合があります。</span><span class="sxs-lookup"><span data-stu-id="9be3c-341">The media may flow directly from Teams and/or the Skype for Business client to the SBC (bypassing the Teams gateway) or traverse through the Teams gateway.</span></span> <span data-ttu-id="9be3c-342">樹幹が Teams ゲートウェイをバイパスするように構成されている場合、SBC を使用した接続は、SBC をサポートする ICE をベースにしており、Teams/Skype for Business のメディアエンドポイントは ICE をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-342">The connectivity with the SBC, when the trunk is configured to bypass the Teams gateway, is based on ICE, where SBC supports ICE-Lite, while the Teams/Skype for Business media endpoint supports ICE Full.</span></span> 

<span data-ttu-id="9be3c-343">[![Microsoft Teams Online の通話フロー図17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-343">[![Microsoft Teams Online Call Flows Figure 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span></span>

<span data-ttu-id="9be3c-344">\* 図 17-電話システムのダイレクトルーティングトポロジを使用したチーム</span><span class="sxs-lookup"><span data-stu-id="9be3c-344">\*Figure 17 - Teams with Phone System Direct Routing topology</span></span>

<span data-ttu-id="9be3c-345">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9be3c-345">Note that:</span></span>

- <span data-ttu-id="9be3c-346">上の図の矢印の方向は、企業境界での接続に影響を与える通信の開始方向を反映しています。</span><span class="sxs-lookup"><span data-stu-id="9be3c-346">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="9be3c-347">メディア用に UDP の場合は、最初のパケットが逆方向に流れる場合がありますが、これらのパケットは、他の方向のパケットが流れるまでブロックされることがあります。</span><span class="sxs-lookup"><span data-stu-id="9be3c-347">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="9be3c-348">Teams は Skype for Business Online と並行して展開されるため、クライアントは "Teams/SFB ユーザー" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-348">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user".</span></span>

<span data-ttu-id="9be3c-349">追加のフロー (Teams online トポロジの一番上):</span><span class="sxs-lookup"><span data-stu-id="9be3c-349">Additional flows (on top of Teams online topology):</span></span>
- <span data-ttu-id="9be3c-350">**Flow 4 '** -Office 365 から顧客ネットワークへのフローを表します。これを使用して、お客様は、クラウドの Teams メディアサーバーと SBC オンプレミスの間の接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-350">**Flow 4'** - Represents a flow from Office 365 to the customer network, used to establish a connection between the Teams media server in the cloud with the SBC on premises.</span></span>
- <span data-ttu-id="9be3c-351">**Flow 5b** –お客様のネットワーク内の Teams ユーザー間のメディアフローを表します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-351">**Flow 5B** – Represents a media flow between the Teams user within the customer network with the Direct Routing SBC in bypass mode.</span></span>
- <span data-ttu-id="9be3c-352">**フロー 5c** – PSTN 転送 call バイパスモードで、ダイレクトルーティングの sbc と別のダイレクトルーティングの sbc 間のメディアフローを表します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-352">**Flow 5C** – Represents a media flow between the Direct Routing SBC to another Direct Routing SBC in a PSTN hairpin call bypass mode.</span></span>

<span data-ttu-id="9be3c-353">**直接ルーティングを使用する内部ユーザー (Office 365 で Teams トランスポートリレーによって中継されるメディア)**</span><span class="sxs-lookup"><span data-stu-id="9be3c-353">**Internal user with Direct Routing (media relayed by Teams Transport Relay in Office 365)**</span></span>

<span data-ttu-id="9be3c-354">[![Microsoft Teams Online の通話フロー図18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-354">[![Microsoft Teams Online Call Flows Figure 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span></span>

<span data-ttu-id="9be3c-355">*図 18-直接ルーティングを使用する内部ユーザー (Office 365 で Teams トランスポートリレーによって中継されたメディア)*</span><span class="sxs-lookup"><span data-stu-id="9be3c-355">*Figure 18 - Internal user with Direct Routing (media relayed by Teams Transport Relay in Office 365)*</span></span>

<span data-ttu-id="9be3c-356">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9be3c-356">Note that:</span></span>
 
- <span data-ttu-id="9be3c-357">SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="9be3c-357">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="9be3c-358">SBC から Office 365 へのシグナリングおよびメディアの場合は、flow 4 または flow 4 を使います。</span><span class="sxs-lookup"><span data-stu-id="9be3c-358">Signaling and media from the SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="9be3c-359">顧客ネットワーク内のクライアントから Office 365 へのシグナリングとメディアの送信は、flow 4 を使います。</span><span class="sxs-lookup"><span data-stu-id="9be3c-359">Signaling and media from the client within the customer network to Office 365 use flow 4.</span></span>


<span data-ttu-id="9be3c-360">**直接ルーティングを使用するリモートユーザー (メディアは、Office 365 でメディアサーバー (MP) 経由でルーティングされます)**</span><span class="sxs-lookup"><span data-stu-id="9be3c-360">**Remote user with Direct Routing (media is routed through a media server (MP) in Office 365)**</span></span>

<span data-ttu-id="9be3c-361">[![Microsoft Teams Online の通話フロー図19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-361">[![Microsoft Teams Online Call Flows Figure 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span></span>

<span data-ttu-id="9be3c-362">*図 19-直接ルーティングを使用しているリモートユーザー (メディアは、Office 365 でメディアサーバー (MP) 経由でルーティングされます)*</span><span class="sxs-lookup"><span data-stu-id="9be3c-362">*Figure 19 - Remote user with Direct Routing (media is routed through a media server (MP) in Office 365)*</span></span>
 
<span data-ttu-id="9be3c-363">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9be3c-363">Note that:</span></span>

- <span data-ttu-id="9be3c-364">SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="9be3c-364">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="9be3c-365">SBC から Office 365 へのシグナリングおよびメディアの場合は、flow 4 または flow 4 を使います。</span><span class="sxs-lookup"><span data-stu-id="9be3c-365">Signaling and media from the SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="9be3c-366">インターネット上のクライアントから Office 365 へのシグナリングとメディアの流れ3を使用します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-366">Signaling and media from the client on the Internet to Office 365 use flow 3.</span></span>

<span data-ttu-id="9be3c-367">**内部ユーザー直接ルーティング (メディアバイパス)**</span><span class="sxs-lookup"><span data-stu-id="9be3c-367">**Internal user Direct Routing (media bypass)**</span></span>

<span data-ttu-id="9be3c-368">[![Microsoft Teams Online の通話フロー図20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-368">[![Microsoft Teams Online Call Flows Figure 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span></span>

<span data-ttu-id="9be3c-369">*図 20-内部ユーザー直接ルーティング (メディアバイパス)*</span><span class="sxs-lookup"><span data-stu-id="9be3c-369">*Figure 20 - Internal user Direct Routing (media bypass)*</span></span>
 
<span data-ttu-id="9be3c-370">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9be3c-370">Note that:</span></span>

- <span data-ttu-id="9be3c-371">SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="9be3c-371">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="9be3c-372">SBC から Office 365 およびその逆のシグナリングでは、flow 4 またはフロー4のどちらか一方または両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-372">Signaling from SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="9be3c-373">顧客ネットワーク内のクライアントから Office 365 へのシグナリングは、flow 4 を使います。</span><span class="sxs-lookup"><span data-stu-id="9be3c-373">Signaling from client within the customer network to Office 365 use flow 4.</span></span>

- <span data-ttu-id="9be3c-374">顧客ネットワーク内のクライアントから、顧客ネットワーク内の SBC までのメディア。フロー5B を使用します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-374">Media from client within the customer network to SBC within the customer network use flow 5B.</span></span>

<span data-ttu-id="9be3c-375">**直接ルーティングを使用するリモートユーザー (Office 365 の Teams トランスポートリレーによって中継されたメディアのバイパス)**</span><span class="sxs-lookup"><span data-stu-id="9be3c-375">**Remote user with Direct Routing (media bypass relayed by Teams Transport Relay in Office 365)**</span></span>

<span data-ttu-id="9be3c-376">[![Microsoft Teams Online の通話フロー図21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-376">[![Microsoft Teams Online Call Flows Figure 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span></span>

<span data-ttu-id="9be3c-377">*図 21-直接ルーティングを使用するリモートユーザー (Office 365 の Teams トランスポートリレーによって中継されるメディア)*</span><span class="sxs-lookup"><span data-stu-id="9be3c-377">*Figure 21 - Remote user with Direct Routing (media bypass relayed by Teams Transport Relay in Office 365)*</span></span>

<span data-ttu-id="9be3c-378">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9be3c-378">Note that:</span></span>

- <span data-ttu-id="9be3c-379">SBC には、Office 365 およびインターネットからルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="9be3c-379">The SBC must have a public IP address that is routable from Office 365 and Internet.</span></span>

- <span data-ttu-id="9be3c-380">SBC から Office 365、またはその逆のシグナリングでは、flow 4 またはフロー4のいずれかまたは両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-380">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="9be3c-381">インターネット上のクライアントから Office 365 への通知では、flow 3 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-381">Signaling from the client on the Internet to Office 365 uses flow 3.</span></span>

- <span data-ttu-id="9be3c-382">インターネット上のクライアントからお客様のネットワーク内の SBC へのメディアは、フロー3と4を使い、Office 365 の Teams トランスポートリレーによって中継されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-382">Media from the client on the Internet to the SBC within the customer network uses flows 3 and 4, relayed by Teams Transport Relay in Office 365.</span></span> 

<span data-ttu-id="9be3c-383">**リモートユーザーの直接ルーティング (メディアバイパスダイレクト)**</span><span class="sxs-lookup"><span data-stu-id="9be3c-383">**Remote user Direct Routing (media bypass direct)**</span></span>

<span data-ttu-id="9be3c-384">[![Microsoft Teams Online の通話フロー図22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-384">[![Microsoft Teams Online Call Flows Figure 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span></span>

<span data-ttu-id="9be3c-385">*図 22-リモートユーザーの直接ルーティング (メディアバイパスダイレクト)*</span><span class="sxs-lookup"><span data-stu-id="9be3c-385">*Figure 22 - Remote user Direct Routing (media bypass direct)*</span></span>
 
<span data-ttu-id="9be3c-386">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9be3c-386">Note that:</span></span>

- <span data-ttu-id="9be3c-387">SBC には、Office 365 およびインターネットからルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="9be3c-387">The SBC must have a public IP address that is routable from Office 365 and the Internet.</span></span>

- <span data-ttu-id="9be3c-388">SBC から Office 365、またはその逆のシグナリングでは、flow 4 またはフロー4のいずれかまたは両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-388">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="9be3c-389">インターネット上のクライアントから Office 365 への通知では、flow 3 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-389">Signaling from the client on the Internet to Office 365 uses flow 3.</span></span>

- <span data-ttu-id="9be3c-390">インターネット上のクライアントから顧客ネットワーク内の SBC までのメディアは、フロー2を使用します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-390">Media from the client on the Internet to the SBC within the customer network uses flow 2.</span></span>

<span data-ttu-id="9be3c-391">**直接ルーティング (メディアバイパス) – PSTN 転送通話 (通話転送/転送のため)**</span><span class="sxs-lookup"><span data-stu-id="9be3c-391">**Direct Routing (media bypass) – PSTN hairpin call (due to call forward/transfer)**</span></span>

<span data-ttu-id="9be3c-392">[![Microsoft Teams Online の通話フロー図23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-392">[![Microsoft Teams Online Call Flows Figure 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span></span>

<span data-ttu-id="9be3c-393">*図 23-直接ルーティング (メディアバイパス)-PSTN 転送通話 (通話転送/転送のため)*</span><span class="sxs-lookup"><span data-stu-id="9be3c-393">*Figure 23 - Direct Routing (media bypass) - PSTN hairpin call (due to call forward/transfer)*</span></span>
 
<span data-ttu-id="9be3c-394">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9be3c-394">Note that:</span></span>

- <span data-ttu-id="9be3c-395">SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="9be3c-395">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="9be3c-396">SBC から Office 365、またはその逆のシグナリングでは、flow 4 またはフロー4のいずれかまたは両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-396">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="9be3c-397">クライアントは、通話が PSTN から PSTN に hairpinned された後に、シグナリングおよびメディアループを終了します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-397">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="9be3c-398">顧客ネットワーク内の SBC インスタンス A から、顧客ネットワーク内の SBC インスタンス B へのメディア (場所 A と B は同じインスタンスである可能性があります) は、フロー5C を使用します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-398">Media from SBC instance A within the customer network to SBC instance B within the customer network (where, A and B can be the same instance) uses flow 5C.</span></span>

<span data-ttu-id="9be3c-399">**直接ルーティング (Office 365 経由のメディア) –2つのテナント間での PSTN 転送通話**</span><span class="sxs-lookup"><span data-stu-id="9be3c-399">**Direct Routing (media through Office 365) – PSTN hairpin call across two tenants**</span></span>

<span data-ttu-id="9be3c-400">[![Microsoft Teams Online の通話フロー図24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-400">[![Microsoft Teams Online Call Flows Figure 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span></span>

<span data-ttu-id="9be3c-401">*図 24-ダイレクトルーティング (Office 365 経由のメディア) –2つのテナント間での PSTN 転送通話*</span><span class="sxs-lookup"><span data-stu-id="9be3c-401">*Figure 24 - Direct Routing (media through Office 365) – PSTN hairpin call across two tenants*</span></span>
 
<span data-ttu-id="9be3c-402">次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9be3c-402">Note that:</span></span>

- <span data-ttu-id="9be3c-403">SBC には、Office 365 からルーティング可能なパブリック IP アドレスが必要です。</span><span class="sxs-lookup"><span data-stu-id="9be3c-403">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="9be3c-404">SBC から Office 365、またはその逆のシグナリングでは、flow 4 またはフロー4のいずれかまたは両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-404">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="9be3c-405">クライアントは、通話が PSTN から PSTN に hairpinned された後に、シグナリングおよびメディアループを終了します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-405">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="9be3c-406">顧客ネットワーク X から SBC インスタンス B 内の SBC インスタンスからのメディアは、Office 365 メディアサーバーを通じて中継され、バイパスモードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="9be3c-406">Media from SBC instance A within the customer network X to SBC instance B must be relayed through the Office 365 Media Server and can't use bypass mode.</span></span>

## <a name="teams-with-express-route-optimization"></a><span data-ttu-id="9be3c-407">エクスプレスルートの最適化を使用しているチーム</span><span class="sxs-lookup"><span data-stu-id="9be3c-407">Teams with Express Route optimization</span></span>

<span data-ttu-id="9be3c-408">[![Microsoft Teams Online の通話フロー図25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-408">[![Microsoft Teams Online Call Flows Figure 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span></span>

<span data-ttu-id="9be3c-409">*図 25-簡易ルートの最適化を使用したチーム*</span><span class="sxs-lookup"><span data-stu-id="9be3c-409">*Figure 25 - Teams with Express Route optimization*</span></span>
 
<span data-ttu-id="9be3c-410">エクスプレスルートが両端揃えで展開されている場合、チームフローはフロー4からフロー1に、フロー4からフロー1に再ルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-410">In the case that Express Route is justified and deployed, then Teams flows could be re-routed from flow 4 to flow 1 and from flow 4' to flow 1'.</span></span> <span data-ttu-id="9be3c-411">ただし、Teams アプリケーションは、フロー4と4を介してインターネット経由で、他の Office 365 のフローに対する依存関係を持っています。そのため、これらのフローはブロックしないでください。</span><span class="sxs-lookup"><span data-stu-id="9be3c-411">However, Teams Application has a hard dependency on other Office 365 flows over the internet via flows 4 and 4'; hence these flows must not be blocked.</span></span> 

<span data-ttu-id="9be3c-412">Skype for Business ハイブリッドエッジトラフィックは、インターネットにルーティングされるため、外部ユーザーと通信したり、他のテナントとフェデレーションを行ったりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9be3c-412">Note that Skype for Business hybrid Edge traffic is routed to the Internet and not to Express Route to communicate with external users and federate with other tenants.</span></span> 

<span data-ttu-id="9be3c-413">非対称のフローを防ぐために、再ルーティングは両方の方向で行われる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9be3c-413">To prevent asymmetrical flows, re-routing must be in both directions.</span></span> <span data-ttu-id="9be3c-414">つまり、顧客ネットワーク内のアドレスは、インターネットまたはエクスプレスルート (最適化に基づく) を介してルーティングされますが、両方を経由することはできません。</span><span class="sxs-lookup"><span data-stu-id="9be3c-414">In other words, an address within the customer network is routable either through Internet or Express Route, based on optimization, but not through both.</span></span>

<span data-ttu-id="9be3c-415">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-415">For example:</span></span>

<span data-ttu-id="9be3c-416">**外部ユーザーに対する顧客ネットワーク (メディアトランスポートリレーによって中継されるメディア):**</span><span class="sxs-lookup"><span data-stu-id="9be3c-416">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="9be3c-417">[![Microsoft Teams Online の通話フロー図26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span><span class="sxs-lookup"><span data-stu-id="9be3c-417">[![Microsoft Teams Online Call Flows Figure 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span></span>

<span data-ttu-id="9be3c-418">*図 26-外部ユーザーへの顧客ネットワーク (Teams トランスポートリレーによるメディアの中継)*</span><span class="sxs-lookup"><span data-stu-id="9be3c-418">*Figure 26 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>
 
<span data-ttu-id="9be3c-419">**高レベルの手順:**</span><span class="sxs-lookup"><span data-stu-id="9be3c-419">**High Level Steps:**</span></span>
1. <span data-ttu-id="9be3c-420">顧客ネットワーク内の Teams ユーザーが flow2 経由で URL ドメイン名 (DNS) を解決する</span><span class="sxs-lookup"><span data-stu-id="9be3c-420">Teams User within customer network resolves URL domain name (DNS) via flow2</span></span>
2. <span data-ttu-id="9be3c-421">顧客ネットワーク内の teams ユーザーは、フロー1経由で Teams トランスポートリレーにメディアリレーポートを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-421">Teams User within customer network allocates a media Relay port on Teams Transport Relay via flow 1</span></span>
3. <span data-ttu-id="9be3c-422">顧客ネットワーク内の Teams ユーザーは、フロー1から Office 365 への "招待" を、ICE 候補と共に送信します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-422">Teams User within customer network sends "invite" with ICE candidates via flow 1 to Office 365</span></span>
4. <span data-ttu-id="9be3c-423">OFFICE 365 は、フロー3経由で外部チームユーザーに通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-423">OFFICE 365 sends notification to external Teams user via flow 3</span></span>
5. <span data-ttu-id="9be3c-424">Teams の外部ユーザーは、フロー3経由で Teams トランスポートリレーにメディアリレーポートを割り当てます</span><span class="sxs-lookup"><span data-stu-id="9be3c-424">Teams external user allocates a media Relay port on Teams Transport Relay via flow 3</span></span>
6. <span data-ttu-id="9be3c-425">Teams の外部ユーザーは、フロー3経由で ICE 候補を使って "answer" を送信します。フロー1を通じて Teams ユーザー A に転送されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-425">Teams external user sends "answer" with ICE candidates via flow 3, which is forwarded back to Teams user A via Flow 1</span></span>
7. <span data-ttu-id="9be3c-426">Teams ユーザー A と Teams ユーザー B は、ICE 接続テストを呼び出し、フロー1と3を選択します。これは、Office 365 の Teams トランスポートリレーによって中継されます。</span><span class="sxs-lookup"><span data-stu-id="9be3c-426">Teams User A and Teams User B invoke ICE connectivity tests and selects flows 1 and 3, which are relayed by Teams Transport Relay in Office 365</span></span>
8. <span data-ttu-id="9be3c-427">Teams ユーザーは、フロー1と3を使って Office 365 にテレメトリを送信します。</span><span class="sxs-lookup"><span data-stu-id="9be3c-427">Teams Users send telemetry to Office 365 via flows 1 and 3</span></span>

><span data-ttu-id="9be3c-428">**注**: フロー4では、他のマイクロサービスで Teams アプリケーションの依存関係がサポートされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9be3c-428">**Note**: Flow 4 must be enabled to support dependencies of Teams application on other micro-services that mandates flow 4.</span></span>
