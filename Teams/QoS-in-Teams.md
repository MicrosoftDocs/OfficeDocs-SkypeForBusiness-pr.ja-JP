---
title: マイクロソフト チームのチームで Microsoft のサービスの品質
author: rmw2890
ms.author: MyAdvisor
manager: Serdars
ms.date: 12/17/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Microsoft Teams でのサービスの品質 (QoS) のために組織のネットワークを準備する
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: e68a11fcc519b63fe04bf6eedfbf9d87b3b80b0b
ms.sourcegitcommit: 0e671e6e6fdd25227068c7e3a3a5509b6536d2b1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2018
ms.locfileid: "27294181"
---
# <a name="quality-of-service-qos-in-microsoft-teams"></a><span data-ttu-id="8c3be-103">Microsoft Teams でのサービスの品質 (QoS)</span><span class="sxs-lookup"><span data-stu-id="8c3be-103">Quality of Service (QoS) in Microsoft Teams</span></span>

<span data-ttu-id="8c3be-104">この資料は、組織のネットワークのサービス品質 (QoS) マイクロソフトのチームのための準備に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8c3be-104">This article will help you prepare your organization's network for Quality of Service (QoS) in Microsoft Teams.</span></span>

<span data-ttu-id="8c3be-105">重要度の低いトラフィック上で機密性の高いネットワークの遅延には、ネットワーク トラフィックの優先順位を QoS を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="8c3be-105">You can use QoS to prioritize network traffic that is sensitive to network delays over traffic that is less sensitive.</span></span> <span data-ttu-id="8c3be-106">単純な例では、QoS が仮想作成、データの「カープール レーン」がされないため、一部種類データをネットワークまたは遅延が発生することはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="8c3be-106">A simple analogy is that QoS creates virtual “carpool lanes” in your data network so some types of data never or rarely encounter delays.</span></span>
<span data-ttu-id="8c3be-107">コールすることがチーム内の共有の会議などのリアルタイムの通信のトラフィックを優先順位を付けるより確実にビジネス クラスのユーザー エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-107">When you prioritize the traffic for real-time communications such as calls or shared meetings in Teams you can more reliably deliver a business-grade user experience.</span></span> <span data-ttu-id="8c3be-108">QoS のフォームの一部をなしには、音声およびビデオの次の品質の問題を参照してください可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8c3be-108">Without some form of QoS, you might see the following quality issues in voice and video:</span></span>

- <span data-ttu-id="8c3be-109">ジッター: メディア パケットの到着率が異なる。</span><span class="sxs-lookup"><span data-stu-id="8c3be-109">Jitter – media packets arriving at different rates.</span></span>
- <span data-ttu-id="8c3be-110">パケット損失 – パケットをドロップすると、語句や音節を不足しているが発生することができます。</span><span class="sxs-lookup"><span data-stu-id="8c3be-110">Packet loss – packets dropped, which can result in missing words or syllables.</span></span>
- <span data-ttu-id="8c3be-111">遅延の往復時間 (RTT) – メディア パケットが宛先に到達するのに時間がかかっています。</span><span class="sxs-lookup"><span data-stu-id="8c3be-111">Delayed round trip time (RTT) – media packets taking a long time to reach their destinations.</span></span>

<span data-ttu-id="8c3be-112">QoS では、真に効果的な一貫した QoS 設定が必要な QoS 優先順位をサポートするために失敗したパスの任意の部分には、通話の品質が低下する可能性があるため、(ユーザーのコンピューター、ネットワーク スイッチ、およびクラウドへのルーター) は、組織内のエンド ツー エンドを適用します。、ビデオ、および画面共有します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-112">For QoS to be truly effective, consistent QoS settings need to be applied from end to end in your organization (user PCs, network switches, and routers to the cloud), because any part of the path that fails to support your QoS priorities can degrade the quality of calls, video, and screen shares.</span></span>

<span data-ttu-id="8c3be-113">![組織のネットワークおよび Office 365 のサービス間の関係: オンプレミス ネットワークとデバイスは、Office 365 のクラウドの音声および電話会議サービスに接続する、相互接続ネットワークに接続します]。(media/Qos-in-Teams-Image1.png "組織のネットワークおよび Office 365 のサービス間の関係: オンプレミス ネットワークとデバイスは、Office 365 のクラウドの音声および電話会議サービスに接続する、相互接続ネットワークに接続します")。</span><span class="sxs-lookup"><span data-stu-id="8c3be-113">![The relationship between an organization's networks and Office 365 services: on-premises network and devices connect with an interconnect network, which in turn connects with Office 365 Cloud Voice and Audio Conferencing services.](media/Qos-in-Teams-Image1.png "The relationship between an organization's networks and Office 365 services: on-premises network and devices connect with an interconnect network, which in turn connects with Office 365 Cloud Voice and Audio Conferencing services.")</span></span>

<span data-ttu-id="8c3be-114">_図 1 です。組織のネットワークおよび Office 365 のサービス間の関係_</span><span class="sxs-lookup"><span data-stu-id="8c3be-114">_Figure 1. The relationship between an organization’s networks and Office 365 services_</span></span>


<span data-ttu-id="8c3be-115">ほとんどの場合は、相互接続ネットワークを管理されていないネットワークのインターネット接続となります。</span><span class="sxs-lookup"><span data-stu-id="8c3be-115">In most cases, the interconnect network will be an unmanaged network internet connection.</span></span> 

<span data-ttu-id="8c3be-116">エンド ・ ツー ・ エンドの QoS に対応する利用可能なオプションの 1 つは、 [Azure の ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/)です。</span><span class="sxs-lookup"><span data-stu-id="8c3be-116">One option available to address end-to-end QoS is [Azure ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/).</span></span> <span data-ttu-id="8c3be-117">設置型ネットワーク上で QoS を実装することもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-117">We still recommend that you implement QoS on your on-premises network.</span></span> <span data-ttu-id="8c3be-118">展開全体にわたってワークロードをリアルタイム通信の品質が向上し、チョークを軽減します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-118">This will increase the quality of real-time communication workloads throughout your deployment and alleviate chokepoints.</span></span> 


## <a name="prioritize-teams-network-traffic-for-qos"></a><span data-ttu-id="8c3be-119">QoS のチームのネットワーク トラフィックを優先順位を付ける</span><span class="sxs-lookup"><span data-stu-id="8c3be-119">Prioritize Teams network traffic for QoS</span></span> 

<span data-ttu-id="8c3be-120">チームのリアルタイム通信トラフィックを優先順位を設定する方法についてこの資料で説明、音声、ビデオ。</span><span class="sxs-lookup"><span data-stu-id="8c3be-120">This article focuses on how to prioritize Teams real-time communications traffic—namely, voice and video.</span></span> <span data-ttu-id="8c3be-121">他の種類のトラフィックは、お客様のニーズに基づいて優先順位を付けることができますもします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-121">You can also prioritize other types of traffic, based on your needs.</span></span>

<span data-ttu-id="8c3be-122">トラフィックの優先順位をいくつかの方法がありますが、差別化されたサービス コード ポイント (DSCP) のマーキングを使用して、最も一般的なは。</span><span class="sxs-lookup"><span data-stu-id="8c3be-122">There are several ways to prioritize traffic, but the most common is by using differentiated services code point (DSCP) markings.</span></span> <span data-ttu-id="8c3be-123">適用できるように「タグ付き」) ベースのポートの範囲にまたはグループ ポリシー オブジェクトを使用していますいます。</span><span class="sxs-lookup"><span data-stu-id="8c3be-123">They can be applied (“tagged”) based on port ranges or via Group Policy objects.</span></span> <span data-ttu-id="8c3be-124">この資料では、両方の操作を説明します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-124">We’ll cover both in this article.</span></span> <span data-ttu-id="8c3be-125">ドメインに参加しているものだけでなく、すべてのデバイスの動作するためにポートの範囲に基づくタグ付け機能を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-125">We recommend that you use tagging based on port ranges because it will work for all devices, not just those joined to the domain.</span></span>

<span data-ttu-id="8c3be-126">グループ ポリシー オブジェクトを使用して DSCP マーキングを制御することにより、ドメインに参加しているコンピューターが適切な設定を受信して、管理者だけがそれらを管理できることをします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-126">Controlling the DSCP marking via Group Policy objects ensures that domain-joined computers receive the correct settings and that only an administrator can manage them.</span></span>

<span data-ttu-id="8c3be-127">別の呼び出し元の接続のすべてのリンクに実装されているときに、QoS をのみ動作するかを理解する重要です。</span><span class="sxs-lookup"><span data-stu-id="8c3be-127">It’s important to understand that QoS only works when implemented on all links that connect caller to another.</span></span> <span data-ttu-id="8c3be-128">内部ネットワーク上で QoS を使用する場合は、ユーザーがリモートの場所からサインインすることができますのみ優先順位を管理、内部ネットワーク内で。</span><span class="sxs-lookup"><span data-stu-id="8c3be-128">If you use QoS on the internal network and a user signs in from a remote location, you can only prioritize within your internal, managed network.</span></span> <span data-ttu-id="8c3be-129">リモート ・ サイトでは、仮想プライベート ネットワーク (VPN) を実装することにより管理されている接続を受信できる、リアルタイム通信トラフィックを VPN 経由で実行しないようにすることお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-129">Although remote locations can receive a managed connection by implementing a virtual private network (VPN), we  recommend that you avoid running real-time communications traffic over the VPN.</span></span>

> [!NOTE]
> <span data-ttu-id="8c3be-130">分割トンネリング VPN に接続されているリモート ・ ユーザーのユーザー エクスペリエンスの品質を最大化を実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-130">We recommend that you implement split tunneling for VPN-connected remote users to maximize the quality of the user experience.</span></span> <span data-ttu-id="8c3be-131">詳細については、MyAdvisor から[分割トンネルの VPN の展開のガイダンス](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 )のドキュメントをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-131">Download the document [Deploy-Guidance-VPN Split Tunnel](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ) from MyAdvisor for more information.</span></span>

<span data-ttu-id="8c3be-132">大陸にまたがる管理のリンクを持つグローバル組織では、強くお勧め QoS それらのリンクの帯域幅は、LAN と比較すると限られているためです。</span><span class="sxs-lookup"><span data-stu-id="8c3be-132">In a global organization with managed links that span continents, we strongly recommend QoS because bandwidth for those links is limited in comparison to the LAN.</span></span>

## <a name="qos-queues"></a><span data-ttu-id="8c3be-133">QoS キュー</span><span class="sxs-lookup"><span data-stu-id="8c3be-133">QoS queues</span></span>

<span data-ttu-id="8c3be-134">QoS を提供するには、ネットワーク デバイスがトラフィックを分類する方法が必要し、音声またはビデオに他のネットワーク トラフィックを区別できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c3be-134">To provide QoS, network devices must have a way to classify traffic and must be able to distinguish voice or video from other network traffic.</span></span> 

<span data-ttu-id="8c3be-135">差別化サービス (DiffServ) は、ネットワーク デバイスの優先順位を設定するのには、IPv4 と IPv6 パケットのヘッダー内のサービス (ToS) フィールドの種類を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-135">Differentiated services (DiffServ) uses the type of services (ToS) field in the header of an IPv4/IPv6 packet to set priority for network devices.</span></span> <span data-ttu-id="8c3be-136">DiffServ フィールドの 6 つの最上位ビットは、差別化されたサービス コード ポイント、または DSCP です。</span><span class="sxs-lookup"><span data-stu-id="8c3be-136">The six most significant bits of the DiffServ field are the differentiated services code point, or DSCP.</span></span> <span data-ttu-id="8c3be-137">これを使用して、トラフィック (音声など)、特定の種類に分類してできるマークされます (101110、または音声トラフィックの 10 進数で 46)、ネットワーク デバイスは、これらのマーキングを処理するときにトラフィックが優先順位を付けるそれに応じてように (で、転送を促進します。この例で)。</span><span class="sxs-lookup"><span data-stu-id="8c3be-137">Using this, traffic can be classified as a particular type (for example, voice), and then marked (101110, or 46 in decimal for voice traffic), so that when network devices process these markings, the traffic can be prioritized accordingly (expedited forwarding, in this example).</span></span>

<span data-ttu-id="8c3be-138">ネットワーク トラフィックが、ルーターを入力すると、トラフィックは、キューに格納されます。</span><span class="sxs-lookup"><span data-stu-id="8c3be-138">When network traffic enters a router, the traffic is placed into a queue.</span></span> <span data-ttu-id="8c3be-139">QoS に、キューの 1 つだけがあるし、データが扱われるようで、先入れ先出しします。つまり、オンラインのストリーミング サービスからトラフィックの背後にある音声トラフィックの遅延に非常に機密性の高い) に残ってしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8c3be-139">If there is no QoS in place, there is only one queue, and data is treated as first-in, first-out. That means voice traffic (which is very sensitive to delays) might get stuck behind traffic from online streaming services.</span></span> <span data-ttu-id="8c3be-140">別の輻輳管理などの機能 (Cisco のキューの優先度クラスに基づく重み付け公平キュー [CBWFQ]) と輻輳の回避などの機能 (ランダムな重み付けの早期検出 [を使用して、複数のキューを定義するには QoS を実装する場合WRED])。</span><span class="sxs-lookup"><span data-stu-id="8c3be-140">When you implement QoS, you can define multiple queues by using different congestion management features (such as Cisco’s priority queuing and class-based weighted fair queue [CBWFQ]) and congestion avoidance features (such as weighted random early detection [WRED]).</span></span>

<span data-ttu-id="8c3be-141">![キューを複数に分割されている使用可能な帯域幅の合計: オーディオ、ビデオ、およびその他のトラフィック、異なる優先度が割り当てられている]。(media/Qos-in-Teams-Image2.png "キューを複数に分割されている使用可能な帯域幅の合計: オーディオ、ビデオ、およびその他のトラフィック、異なる優先度が割り当てられている")。</span><span class="sxs-lookup"><span data-stu-id="8c3be-141">![Total available bandwidth is divided among multiple queues—audio, video, and other traffic—that have been assigned different priorities.](media/Qos-in-Teams-Image2.png "Total available bandwidth is divided among multiple queues—audio, video, and other traffic—that have been assigned different priorities.")</span></span>

<span data-ttu-id="8c3be-142">_図 2 になります。QoS キューの例_</span><span class="sxs-lookup"><span data-stu-id="8c3be-142">_Figure 2. Examples of QoS queues_</span></span>

<span data-ttu-id="8c3be-143">これらの要素があると後、基になるマネージ ネットワークは今すぐ分類、マーク、およびトラフィックの優先順位を設定する方法を理解しているために、予測可能な QoS を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="8c3be-143">After these pieces are in place, it’s possible to deliver predictable QoS because the underlying managed network now understands how to classify, mark, and prioritize traffic.</span></span> <span data-ttu-id="8c3be-144">チームの観点からの最も重要な構成手順は、クラス分けと、パケットのマーキングが成功するためのエンド ・ ツー ・ エンドの QoS にもする必要しますが、基になるネットワークの構成とアプリケーションの構成を慎重に配置します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-144">From the Teams perspective, the most important configuration step is the classification and marking of packets, but for end-to-end QoS to be successful you also need to carefully align the application’s configuration with the underlying network configuration.</span></span>

## <a name="teams-qos-scenarios"></a><span data-ttu-id="8c3be-145">チームの QoS のシナリオ</span><span class="sxs-lookup"><span data-stu-id="8c3be-145">Teams QoS scenarios</span></span>

<span data-ttu-id="8c3be-146">チームの QoS を実装するためのガイダンスは、4 つのシナリオに基づいています。</span><span class="sxs-lookup"><span data-stu-id="8c3be-146">The guidance for implementing QoS for Teams is based on four scenarios:</span></span>

*  <span data-ttu-id="8c3be-147">**シナリオ 1:** チームを展開を展開して、や、ポート ベースのタグ付けを使用して QoS の実装を計画します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-147">**Scenario 1:** You’ve deployed or are deploying Teams and plan to implement QoS via port-based tagging.</span></span> <span data-ttu-id="8c3be-148">ポート ベースのタグ付けは、最も信頼性の高いメソッドは例外なくすべてのプラットフォームで実装することが簡単です。</span><span class="sxs-lookup"><span data-stu-id="8c3be-148">Port-based tagging is the most reliable method because it works universally on all platforms and is the easiest to implement.</span></span>  

*  <span data-ttu-id="8c3be-149">**シナリオ 2:** チームを展開を展開して、や、グループ ポリシー オブジェクトのタグ付けを使用して QoS の実装を計画します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-149">**Scenario 2:** You’ve deployed or are deploying Teams and plan to implement QoS via Group Policy object tagging.</span></span> <span data-ttu-id="8c3be-150">これは、シナリオ 1 と組み合わせて使用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="8c3be-150">This is sometimes used in combination with scenario 1.</span></span> <span data-ttu-id="8c3be-151">このシナリオでは完全に有効な Windows クライアントをドメインに参加しているはのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-151">Although this scenario is entirely valid, it will only work for domain-joined Windows clients.</span></span> <span data-ttu-id="8c3be-152">DSCP の Windows ドメインに参加しているクライアントではない任意のデバイスを有効にしないタグ付けします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-152">Any device that isn’t a domain-joined Windows client won’t be enabled for DSCP tagging.</span></span>

*  <span data-ttu-id="8c3be-153">**シナリオ 3:** 展開して、Skype のビジネス オンライン、QoS がタグ付けを含む、そのチームを配置するようになりました。</span><span class="sxs-lookup"><span data-stu-id="8c3be-153">**Scenario 3:** You’ve deployed Skype for Business Online, including QoS tagging, and are now deploying Teams.</span></span> <span data-ttu-id="8c3be-154">この状況に該当する場合は、Teams は既存の構成を優先して、Skype for Business クライアントのものと同じポート範囲とタグ付けを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-154">If this is you, Teams will respect the existing configuration and will use the same port ranges and tagging as the Skype for Business client.</span></span> <span data-ttu-id="8c3be-155">ほとんどの場合、追加の構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8c3be-155">In most cases, no additional configuration will be needed.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="8c3be-156">グループ ポリシーを使用してタグ付けアプリケーション名の QoS を使用する場合は、アプリケーション名として Teams.exe を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c3be-156">If you're using Application Name QoS tagging via Group Policy, you must add Teams.exe as the application name.</span></span>

*  <span data-ttu-id="8c3be-157">**シナリオ 4:** チームは、展開を展開して、や、ポート ベースのカスタムのポート範囲を使用してタグ付けを使用して QoS を実装します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-157">**Scenario 4:** You’ve deployed or are deploying Teams and want to implement QoS via port-based tagging by using a custom port range.</span></span>

## <a name="implement-qos"></a><span data-ttu-id="8c3be-158">QoS を実装します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-158">Implement QoS</span></span>

<span data-ttu-id="8c3be-159">非常に高いレベルで QoS を実装する手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="8c3be-159">At a very high level, implementing QoS requires these steps:</span></span>

1. <span data-ttu-id="8c3be-160">工順、および帯域幅の要件を決定します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-160">Determine your route and bandwidth requirements.</span></span>

2. <span data-ttu-id="8c3be-161">DSCP マーキング、およびポートの範囲を使用すると、トラフィックを分類できます。</span><span class="sxs-lookup"><span data-stu-id="8c3be-161">Use DSCP markings and port ranges to classify traffic.</span></span>

3. <span data-ttu-id="8c3be-162">グループ ポリシー オブジェクト内でポリシー ・ ベースの QoS 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-162">Configure the policy-based QoS settings within a Group Policy object.</span></span>

4. <span data-ttu-id="8c3be-163">グループ ポリシー オブジェクト内のポートの範囲を確認します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-163">Verify the port ranges in the Group Policy object.</span></span>

5. <span data-ttu-id="8c3be-164">QoS を検証するには、ネットワーク上のチームのトラフィックを分析します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-164">Validate QoS by analyzing Teams traffic on the network.</span></span>

<span data-ttu-id="8c3be-165">QoS を実装するために準備するときは、次のガイドラインに留意してください。</span><span class="sxs-lookup"><span data-stu-id="8c3be-165">As you prepare to implement QoS, keep the following guidelines in mind:</span></span>

- <span data-ttu-id="8c3be-166">Office 365 への最短パスをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-166">The shortest path to Office 365 is best.</span></span>

- <span data-ttu-id="8c3be-167">ポートを閉じるだけにつながる品質が低下します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-167">Closing ports will only lead to quality degradation.</span></span>

- <span data-ttu-id="8c3be-168">中間プロキシなど、障害物がない、お勧めできません。</span><span class="sxs-lookup"><span data-stu-id="8c3be-168">Any obstacles in-between, such as proxies, are not recommended.</span></span>

- <span data-ttu-id="8c3be-169">ホップの数を制限するには。</span><span class="sxs-lookup"><span data-stu-id="8c3be-169">Limit the number of hops:</span></span>

    - <span data-ttu-id="8c3be-170">ネットワーク エッジ: 3 ~ 5 のホップするクライアントです。</span><span class="sxs-lookup"><span data-stu-id="8c3be-170">Client to network edge – 3 to 5 hops.</span></span>
    - <span data-ttu-id="8c3be-171">ISP に Microsoft ネットワークのエッジ – 3 ホップ</span><span class="sxs-lookup"><span data-stu-id="8c3be-171">ISP to Microsoft network edge – 3 hops</span></span>
    - <span data-ttu-id="8c3be-172">最終的な宛先-無関係に Microsoft ネットワークのエッジ</span><span class="sxs-lookup"><span data-stu-id="8c3be-172">Microsoft network edge to final destination – irrelevant</span></span> 

<span data-ttu-id="8c3be-173">ファイアウォール ポートを構成する方法の詳細については、 [Office 365 の Url と IP の範囲](office-365-urls-ip-address-ranges.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c3be-173">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

## <a name="determine-bandwidth-requirements"></a><span data-ttu-id="8c3be-174">帯域幅要件を決定します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-174">Determine bandwidth requirements</span></span>

<span data-ttu-id="8c3be-175">マイクロソフト チームの QoS を構成する前に、マイクロソフトのチーム用にネットワークを準備し、帯域幅要件を決定する重要なです。</span><span class="sxs-lookup"><span data-stu-id="8c3be-175">Before you configure QoS for Microsoft Teams, it’s important to prepare your network for Microsoft Teams and determine your bandwidth requirements.</span></span> <span data-ttu-id="8c3be-176">ネットワークの QoS を提供する、リアルタイムのトラフィックの各リンクに定義された帯域幅の予約が必要です。</span><span class="sxs-lookup"><span data-stu-id="8c3be-176">Providing QoS in your network requires the reservation of a defined amount of bandwidth on each link for real-time traffic.</span></span> <span data-ttu-id="8c3be-177">(帯域幅は、いつでもリアルタイム トラフィックに必要ない場合は場合に、使用できます、他のトラフィック。)</span><span class="sxs-lookup"><span data-stu-id="8c3be-177">(If that bandwidth isn’t required for real-time traffic at any time, it can be used for other traffic.)</span></span>

<span data-ttu-id="8c3be-178">ネットワーク間でトラフィックの輻輳は、メディアの品質に著しい影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="8c3be-178">Traffic congestion across a network will greatly impact media quality.</span></span> <span data-ttu-id="8c3be-179">パフォーマンスが低下し、ユーザー エクスペリエンスの低下、潜在顧客を帯域幅の不足は、計画チームの配置の開始点としての帯域幅を検討します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-179">A lack of bandwidth leads to performance degradation and a poor user experience, so consider bandwidth planning as a starting point for Teams deployment.</span></span> <span data-ttu-id="8c3be-180">チームの導入と使用率が増大すると、レポートを使用して必要な調整を行います。</span><span class="sxs-lookup"><span data-stu-id="8c3be-180">As Teams adoption and usage grows, use reporting to make necessary adjustments.</span></span> 

<span data-ttu-id="8c3be-181">FastTrack で利用可能なネットワーク プランナーは、帯域幅の要件を決定する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="8c3be-181">The Network Planner available on FastTrack is helpful when you are determining bandwidth requirements.</span></span>

### <a name="requirements-for-a-connection-from-your-network-to-microsoft-network-edge"></a><span data-ttu-id="8c3be-182">ネットワークから Microsoft ネットワークのエッジへの接続の要件</span><span class="sxs-lookup"><span data-stu-id="8c3be-182">Requirements for a connection from your network to Microsoft network edge</span></span>

<span data-ttu-id="8c3be-183">最良のメディアの品質のしきい値を表 1 に示すように、ネットワークのパフォーマンスの目標は、Microsoft ネットワークのエッジに、組織のネットワークからの接続を必要です。</span><span class="sxs-lookup"><span data-stu-id="8c3be-183">For the best media quality, the network performance targets or thresholds shown in Table 1 are required for a connection from your organization’s network to the Microsoft network edge.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c3be-184">Office 365 サービスを会社のネットワーク上のチームのクライアント間の接続は、次のネットワーク パフォーマンスの要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c3be-184">Connectivity between a Teams client on your company network to Office 365 services must meet the following network performance requirements.</span></span>

<span data-ttu-id="8c3be-185">_表 1 です。ネットワーク パフォーマンスの測定値を Office 365 サービスのクライアント_</span><span class="sxs-lookup"><span data-stu-id="8c3be-185">_Table 1. Network performance metrics - client to Office 365 services_</span></span>

| <span data-ttu-id="8c3be-186">指標</span><span class="sxs-lookup"><span data-stu-id="8c3be-186">Metric</span></span> | <span data-ttu-id="8c3be-187">Target</span><span class="sxs-lookup"><span data-stu-id="8c3be-187">Target</span></span> |
|--------|--------|
| <span data-ttu-id="8c3be-188">遅延 (一方向)</span><span class="sxs-lookup"><span data-stu-id="8c3be-188">Latency (one way)</span></span> | <span data-ttu-id="8c3be-189">< 50 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="8c3be-189">< 50 milliseconds</span></span> |
| <span data-ttu-id="8c3be-190">待機時間 (ラウンド トリップ時間 (RTT)</span><span class="sxs-lookup"><span data-stu-id="8c3be-190">Latency (round trip time (RTT)</span></span> | <span data-ttu-id="8c3be-191">< 100 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="8c3be-191">< 100 milliseconds</span></span> |
| <span data-ttu-id="8c3be-192">バースト パケット損失</span><span class="sxs-lookup"><span data-stu-id="8c3be-192">Burst packet loss</span></span> | <span data-ttu-id="8c3be-193">200 ミリ秒の間隔中に < 10%</span><span class="sxs-lookup"><span data-stu-id="8c3be-193">< 10% during any 200 millisecond interval</span></span> |
| <span data-ttu-id="8c3be-194">パケット損失</span><span class="sxs-lookup"><span data-stu-id="8c3be-194">Packet loss</span></span> | <span data-ttu-id="8c3be-195">15 の 2 番目の間隔の中に < 1%</span><span class="sxs-lookup"><span data-stu-id="8c3be-195">< 1% during any 15 second interval</span></span> |
| <span data-ttu-id="8c3be-196">パケット間到着ジッタ</span><span class="sxs-lookup"><span data-stu-id="8c3be-196">Packet inter-arrival jitter</span></span> | <span data-ttu-id="8c3be-197">15 の 2 番目の間隔の中に < 30 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="8c3be-197">< 30 milliseconds during any 15 second interval</span></span> |
| <span data-ttu-id="8c3be-198">パケットの並べ替え</span><span class="sxs-lookup"><span data-stu-id="8c3be-198">Packet reorder</span></span> | <span data-ttu-id="8c3be-199">パケットの並べ替えを < 0.05%</span><span class="sxs-lookup"><span data-stu-id="8c3be-199">< 0.05% out of order packets</span></span> |

<span data-ttu-id="8c3be-200">遅延のメトリック ターゲットでは、会社のサイトやサイトと同じ大陸には、マイクロソフトのエッジです。</span><span class="sxs-lookup"><span data-stu-id="8c3be-200">The latency metric target assumes your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="8c3be-201">Microsoft ネットワークのエッジ接続する会社のサイトには、WiFi または他のワイヤレス技術は、最初のホップ ネットワーク アクセスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8c3be-201">Your company site to the Microsoft network edge connection includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="8c3be-202">ネットワーク パフォーマンスの目標は、適切な帯域幅と QoS 計画を想定しています。</span><span class="sxs-lookup"><span data-stu-id="8c3be-202">The network performance target assumes proper bandwidth and/or QoS planning.</span></span> <span data-ttu-id="8c3be-203">つまり、要件は、ピーク負荷の下では、ネットワーク接続とチーム リアルタイム メディアのトラフィックを直接適用されます。</span><span class="sxs-lookup"><span data-stu-id="8c3be-203">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

### <a name="requirements-for-a-connection-from-your-network-edge-to-microsoft-network-edge"></a><span data-ttu-id="8c3be-204">ネットワークのエッジをネットワークのエッジからマイクロソフトへの接続の要件</span><span class="sxs-lookup"><span data-stu-id="8c3be-204">Requirements for a connection from your network edge to Microsoft network edge</span></span>

<span data-ttu-id="8c3be-205">表 2 は、ネットワークのパフォーマンスの目標や、ネットワーク エッジおよび Microsoft ネットワーク エッジの間の接続に必要なしきい値を示します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-205">Table 2 shows the network performance targets or thresholds that are required for the connection between your network edge and the Microsoft network edge.</span></span> <span data-ttu-id="8c3be-206">これは、組織の内部ネットワークや WAN を除外あり、ガイドとして、インターネット経由または ExpressRoute のパートナー ネットワークを介して送信されるネットワーク トラフィックをテストするときです。</span><span class="sxs-lookup"><span data-stu-id="8c3be-206">This excludes your organization’s internal network or WAN, and is intended as a guide when you test network traffic that is sent over the internet or through an ExpressRoute partner network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c3be-207">Microsoft ネットワークのエッジに、会社のネットワークのエッジの間の接続は、次のネットワーク パフォーマンスの要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c3be-207">Connectivity between your company's network edge to the Microsoft network edges must meet the following network performance requirements.</span></span>

<span data-ttu-id="8c3be-208">_表 2 になります。ネットワーク パフォーマンスの測定基準エッジ ツー エッジ_</span><span class="sxs-lookup"><span data-stu-id="8c3be-208">_Table 2. Network performance metrics - edge to edge_</span></span>

| <span data-ttu-id="8c3be-209">指標</span><span class="sxs-lookup"><span data-stu-id="8c3be-209">Metric</span></span> | <span data-ttu-id="8c3be-210">Target</span><span class="sxs-lookup"><span data-stu-id="8c3be-210">Target</span></span> |
|--------|--------|
| <span data-ttu-id="8c3be-211">遅延 (一方向)</span><span class="sxs-lookup"><span data-stu-id="8c3be-211">Latency (one way)</span></span> | <span data-ttu-id="8c3be-212">< 30 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="8c3be-212">< 30 milliseconds</span></span> |
| <span data-ttu-id="8c3be-213">待機時間 (ラウンド トリップ時間 (RTT)</span><span class="sxs-lookup"><span data-stu-id="8c3be-213">Latency (round trip time (RTT)</span></span> | <span data-ttu-id="8c3be-214">< 60 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="8c3be-214">< 60 milliseconds</span></span> |
| <span data-ttu-id="8c3be-215">バースト パケット損失</span><span class="sxs-lookup"><span data-stu-id="8c3be-215">Burst packet loss</span></span> | <span data-ttu-id="8c3be-216">200 ミリ秒の間隔中に < 1%</span><span class="sxs-lookup"><span data-stu-id="8c3be-216">< 1% during any 200 millisecond interval</span></span> |
| <span data-ttu-id="8c3be-217">パケット損失</span><span class="sxs-lookup"><span data-stu-id="8c3be-217">Packet loss</span></span> | <span data-ttu-id="8c3be-218">15 の 2 番目の間隔の中に < 0.1%</span><span class="sxs-lookup"><span data-stu-id="8c3be-218">< 0.1% during any 15 second interval</span></span> |
| <span data-ttu-id="8c3be-219">パケット間到着ジッタ</span><span class="sxs-lookup"><span data-stu-id="8c3be-219">Packet inter-arrival jitter</span></span> | <span data-ttu-id="8c3be-220">15 の 2 番目の間隔の中に < 15 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="8c3be-220">< 15 milliseconds during any 15 second interval</span></span> |
| <span data-ttu-id="8c3be-221">パケットの並べ替え</span><span class="sxs-lookup"><span data-stu-id="8c3be-221">Packet reorder</span></span> | <span data-ttu-id="8c3be-222">パケットの並べ替えを < 0.01%</span><span class="sxs-lookup"><span data-stu-id="8c3be-222">< 0.01% out of order packets</span></span> |


## <a name="recommended-dscp-markings"></a><span data-ttu-id="8c3be-223">推奨 DSCP マーキング</span><span class="sxs-lookup"><span data-stu-id="8c3be-223">Recommended DSCP markings</span></span>

<span data-ttu-id="8c3be-224">QoS を構成する準備ができたらの最初のステップは、(オーディオ、ビデオなど) のトラフィック フローを分類する、重複しない一意のポート範囲に DSCP 値を割り当てることによって。</span><span class="sxs-lookup"><span data-stu-id="8c3be-224">When you're ready to configure QoS, your first step is to classify the traffic flows (such as audio and video) by assigning DSCP values to the unique, non-overlapping port ranges.</span></span> <span data-ttu-id="8c3be-225">ここで割り当てられている DSCP 値は、ネットワーク構成に基づいて、ネットワークを通過するトラフィックの優先順位を決定します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-225">The DSCP value assigned here will determine the priority of the traffic going through the network, based on network configuration.</span></span> <span data-ttu-id="8c3be-226">各作業負荷を取得独自の DSCP 値は必ずしも一意の値: ネットワーク上の同一の優先順位を与える、音声およびビデオのワークロードに対して同じ値を設定するのにはする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8c3be-226">Each workload gets its own DSCP value, though not necessarily a unique value—you might want to set the same value for voice and video workloads, giving them the same priority in the network.</span></span>  

<span data-ttu-id="8c3be-227">DSCP 値を使用するのには、ワークロードの優先順位を設定する方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8c3be-227">The DSCP value to use depends on how you want to prioritize the workload.</span></span> <span data-ttu-id="8c3be-228">などのビジネス要件がアプリケーションに与えることを決定する可能性がありますビデオと同じ優先順位を共有 (しそのため、ビデオと同じ DSCP 値を使用)。</span><span class="sxs-lookup"><span data-stu-id="8c3be-228">For example, business requirements might dictate that you give application sharing the same priority as video (and therefore mark it with the same DSCP value as video).</span></span> <span data-ttu-id="8c3be-229">他の環境は、既存の QoS 戦略を実施してネットワークのワークロードの優先順位を決定する際に役立つがあります。</span><span class="sxs-lookup"><span data-stu-id="8c3be-229">Other environments might have an existing QoS strategy in place, which will help you determine the priority of network workloads.</span></span> 

<span data-ttu-id="8c3be-230">ExpressRoute とチームのために必要な DSCP マーキングを表 3 に示します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-230">Table 3 shows the DSCP markings required for Teams with ExpressRoute.</span></span> <span data-ttu-id="8c3be-231">これらのマーキングは可能性がありますではないことを確認して、自分の環境で使用するどのようなお客様にとっての開始点として機能します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-231">These markings might serve as a good starting point for customers who are unsure what to use in their own environments.</span></span> <span data-ttu-id="8c3be-232">詳細については、「[ExpressRoute QoS の要件](https://docs.microsoft.com/azure/expressroute/expressroute-qos)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8c3be-232">To learn more, read [ExpressRoute QoS requirements](https://docs.microsoft.com/azure/expressroute/expressroute-qos).</span></span>

<span data-ttu-id="8c3be-233">_表 3。DSCP マーキング_</span><span class="sxs-lookup"><span data-stu-id="8c3be-233">_Table 3. DSCP markings_</span></span>

| <span data-ttu-id="8c3be-234">クライアント ソース ポートの範囲</span><span class="sxs-lookup"><span data-stu-id="8c3be-234">Client source port range</span></span> |<span data-ttu-id="8c3be-235">プロトコル</span><span class="sxs-lookup"><span data-stu-id="8c3be-235">Protocol</span></span>|<span data-ttu-id="8c3be-236">メディアのカテゴリ</span><span class="sxs-lookup"><span data-stu-id="8c3be-236">Media category</span></span>|<span data-ttu-id="8c3be-237">DSCP 値</span><span class="sxs-lookup"><span data-stu-id="8c3be-237">DSCP value</span></span>|<span data-ttu-id="8c3be-238">DSCP クラス</span><span class="sxs-lookup"><span data-stu-id="8c3be-238">DSCP class</span></span>|
|---------|---------|---------|---------|---------|
| <span data-ttu-id="8c3be-239">50,000 – 50,019</span><span class="sxs-lookup"><span data-stu-id="8c3be-239">50,000–50,019</span></span>|<span data-ttu-id="8c3be-240">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="8c3be-240">TCP/UDP</span></span>|<span data-ttu-id="8c3be-241">音声</span><span class="sxs-lookup"><span data-stu-id="8c3be-241">Audio</span></span>|<span data-ttu-id="8c3be-242">46</span><span class="sxs-lookup"><span data-stu-id="8c3be-242">46</span></span>|<span data-ttu-id="8c3be-243">完全優先転送 (EF)</span><span class="sxs-lookup"><span data-stu-id="8c3be-243">Expedited Forwarding (EF)</span></span>|
| <span data-ttu-id="8c3be-244">50,020 – 50,039</span><span class="sxs-lookup"><span data-stu-id="8c3be-244">50,020–50,039</span></span>|<span data-ttu-id="8c3be-245">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="8c3be-245">TCP/UDP</span></span>|<span data-ttu-id="8c3be-246">ビデオ</span><span class="sxs-lookup"><span data-stu-id="8c3be-246">Video</span></span>|<span data-ttu-id="8c3be-247">34</span><span class="sxs-lookup"><span data-stu-id="8c3be-247">34</span></span>|<span data-ttu-id="8c3be-248">相対的優先転送 (AF41)</span><span class="sxs-lookup"><span data-stu-id="8c3be-248">Assured Forwarding (AF41)</span></span>|
| <span data-ttu-id="8c3be-249">50,040-50,059</span><span class="sxs-lookup"><span data-stu-id="8c3be-249">50,040–50,059</span></span>|<span data-ttu-id="8c3be-250">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="8c3be-250">TCP/UDP</span></span>|<span data-ttu-id="8c3be-251">アプリケーション/デスクトップ共有</span><span class="sxs-lookup"><span data-stu-id="8c3be-251">Application/Desktop Sharing</span></span>|<span data-ttu-id="8c3be-252">18</span><span class="sxs-lookup"><span data-stu-id="8c3be-252">18</span></span>|<span data-ttu-id="8c3be-253">相対的優先転送 (AF21)</span><span class="sxs-lookup"><span data-stu-id="8c3be-253">Assured Forwarding (AF21)</span></span>|

<span data-ttu-id="8c3be-254">表 3 の情報を使用する場合、次の対応になります。</span><span class="sxs-lookup"><span data-stu-id="8c3be-254">Be aware of the following when you use the information in Table 3:</span></span>

-  <span data-ttu-id="8c3be-255">ExpressRoute の今後の実装を計画してまだ QoS を実装していない場合は、DSCP 値が受信機に送信元から同じになるようは、表 3 のガイダンスに従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-255">If you plan to implement ExpressRoute in the future and haven’t yet implemented QoS, we recommend that you follow the guidance in Table 3 so that DSCP values are the same from sender to receiver.</span></span> 

-  <span data-ttu-id="8c3be-256">モバイル クライアントやチームのデバイスを含む、すべてのクライアントは、これらのポート範囲を使用し、いずれ DSCP のポリシーを実装するソース ポート範囲を使用する影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="8c3be-256">All clients, including mobile clients and Teams devices, will use these port ranges and will be affected by any DSCP policy you implement that uses these source port ranges.</span></span> <span data-ttu-id="8c3be-257">引き続き動的ポートを使用する唯一のクライアントは、ブラウザー ベースのクライアント (つまり、参加者のブラウザーを使用してミーティングに参加できるようにこれらのクライアント) です。</span><span class="sxs-lookup"><span data-stu-id="8c3be-257">The only clients that will continue to use dynamic ports are the browser-based clients (that is, those clients that let participants join meetings by using their browsers).</span></span>

-  <span data-ttu-id="8c3be-258">Mac クライアントは、同じポート範囲を使用するがも、(EF) のオーディオおよびビデオ (AF41) の値をハードコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-258">Although the Mac client uses the same port ranges, it also uses hard-coded values for audio (EF) and video (AF41).</span></span> <span data-ttu-id="8c3be-259">これらの値は構成可能ではありません。</span><span class="sxs-lookup"><span data-stu-id="8c3be-259">These values are not configurable.</span></span>


## <a name="source-ports-used-by-teams"></a><span data-ttu-id="8c3be-260">Teams によって使用されるソース ポート</span><span class="sxs-lookup"><span data-stu-id="8c3be-260">Source ports used by Teams</span></span>

<span data-ttu-id="8c3be-261">Teams では、QoS は異なるワークロードで使用される送信元ポートに基づいて構成される必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c3be-261">In Teams, QoS should be configured based on the source ports used by the different workloads.</span></span> <span data-ttu-id="8c3be-262">現時点では、どちらのサーバー側とクライアント側のポートの範囲は、設定できます。</span><span class="sxs-lookup"><span data-stu-id="8c3be-262">Currently, neither server-side nor client-side port ranges are configurable.</span></span> 

<span data-ttu-id="8c3be-263">表 3 に記載されているクライアント ソース ポートの範囲は、チームに適用され、その関連付けられている QoS の DSCP マーキングを使用しています。</span><span class="sxs-lookup"><span data-stu-id="8c3be-263">The client source port ranges listed in Table 3 also apply to Teams and use their associated QoS DSCP markings.</span></span>

<span data-ttu-id="8c3be-264">これらの QoS ポリシーを実装するための推奨される方法は、「すべて」の発信元と宛先の IP アドレスにクライアントの送信元ポートを使用するには</span><span class="sxs-lookup"><span data-stu-id="8c3be-264">The recommended method of implementing these QoS policies is to use the client source ports with a source and destination IP address of “any.”</span></span> <span data-ttu-id="8c3be-265">内部ネットワークでこのメディアを受信および送信トラフィックの両方をキャッチします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-265">This will catch both incoming and outgoing media traffic on the internal network.</span></span> 

> [!NOTE]
> <span data-ttu-id="8c3be-266">ソース ポート範囲に基づいて Skype のオンライン ビジネスの QoS を既に構成した場合は、チームに同じ設定が適用され、さらに変更が必要ないです。</span><span class="sxs-lookup"><span data-stu-id="8c3be-266">If you've already configured QoS based on source port ranges for Skype for Business Online, the same configuration will apply to Teams and no further changes will be required.</span></span> <span data-ttu-id="8c3be-267">ビジネス サーバー設置型の Skype を展開した場合は、QoS ポリシーを再検査し、必要に応じて調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c3be-267">If you’ve deployed Skype for Business Server on-premises, you’ll need to re-examine your QoS policies and adjust them if necessary.</span></span>

## <a name="set-dscp-markings"></a><span data-ttu-id="8c3be-268">DSCP マーキングを設定します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-268">Set DSCP markings</span></span>

<span data-ttu-id="8c3be-269">トラフィックの分類の適切な DSCP マーキングを設定するのには複数の方法があります。</span><span class="sxs-lookup"><span data-stu-id="8c3be-269">There are multiple approaches to setting the proper DSCP markings for traffic classification:</span></span>

-  <span data-ttu-id="8c3be-270">**エンドポイントの DSCP マーキング:** だ一般的に希望のオプションでは、エンドポイント自体には、適切なマーキングが用意されています。</span><span class="sxs-lookup"><span data-stu-id="8c3be-270">**DSCP marking at the endpoint:** This is generally the preferred option, because the endpoint itself provides the proper markings.</span></span> <span data-ttu-id="8c3be-271">これを実行して、グループ ポリシー オブジェクトを使用して、現在、Windows のドメインに参加しているクライアントでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="8c3be-271">Currently this can be done by using a Group Policy object, but it can only be used on domain-joined Windows clients.</span></span> <span data-ttu-id="8c3be-272">モバイル クライアントでは、DSCP 値を使用してトラフィックをマークするためのメカニズムを提供しません。</span><span class="sxs-lookup"><span data-stu-id="8c3be-272">Mobile clients don’t provide a mechanism to mark traffic by using DSCP values.</span></span> <span data-ttu-id="8c3be-273">以外を構成することはできません&ndash;タグのトラフィック、Mac OS などのクライアントに Windows クライアントをドメインに参加しているハード コーディングされたタグがあり、前述のようにトラフィックをタグは常にします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-273">Although you can’t configure non&ndash;domain-joined Windows clients to tag traffic, clients such as Mac OS have hard-coded tags and will always tag traffic as described above.</span></span>

-  <span data-ttu-id="8c3be-274">**ポート ベースの DSCP がルーターにアクセス制御リスト (Acl) を使用してタグ付け:** これは、Windows と Mac の異機種混在環境で発生した非常に一般的なオプションです。</span><span class="sxs-lookup"><span data-stu-id="8c3be-274">**Port-based DSCP tagging by using access control lists (ACLs) on routers:** This is a very common option encountered in heterogeneous Windows and Mac environments.</span></span> <span data-ttu-id="8c3be-275">このシナリオでは、ネットワーク チームは、各モダリティに対して定義されているソース ポートの範囲に基づいて (通常は WAN 上にある) の入口/出口となるルーターでのトラフィックをマークします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-275">In this scenario, the network team marks the traffic at the ingress/egress routers (typically located on the WAN) based on the source port ranges defined for each modality.</span></span> <span data-ttu-id="8c3be-276">WAN エッジへのトラフィックにのみマークこのプラットフォーム間で動作しますが、-がクライアント コンピューターにないこと、したがって管理のオーバーヘッドが発生し、。</span><span class="sxs-lookup"><span data-stu-id="8c3be-276">Although this works across platforms, it only marks traffic at the WAN edge—not all the way to the client machine—and therefore incurs management overhead.</span></span>

-  <span data-ttu-id="8c3be-277">**エンドポイントとルーターのポート ベースの Acl に DSCP マーキングの組み合わせ:** この組み合わせは、お客様の環境で可能な場合はお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-277">**A combination of DSCP markings at the endpoint and port-based ACLs on routers:** We recommend this combination, if possible in your environment.</span></span> <span data-ttu-id="8c3be-278">グループ ポリシー オブジェクトを使用して、クライアントのほとんどをキャッチしてタグを付けるようにすること、モバイル、Mac、およびその他のクライアントがまだ QoS 処理 (少なくとも部分的に) ポート ベースの DSCP を使用しても。</span><span class="sxs-lookup"><span data-stu-id="8c3be-278">Use a Group Policy object to catch the majority of clients, and also use port-based DSCP tagging to ensure that mobile, Mac, and other clients will still get QoS treatment (at least partially).</span></span>

<span data-ttu-id="8c3be-279">チーム クライアントで定義済みのソースのポート範囲の DSCP 値を設定するのには、グループ ポリシー内のポリシー ベースの QoS を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8c3be-279">You can use policy-based QoS within Group Policy to set the DSCP value for the predefined source port range in the Teams client.</span></span> <span data-ttu-id="8c3be-280">各ワークロードのポリシーを作成するのにには、表 3 に指定されたポート範囲を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-280">Use the port ranges specified in Table 3 to create a policy for each workload.</span></span>

<span data-ttu-id="8c3be-281">ポートの範囲を特定したら、次に、グループ ポリシー オブジェクト内でポリシー ・ ベースの QoS 設定を構成するのには。</span><span class="sxs-lookup"><span data-stu-id="8c3be-281">After you’ve identified the port ranges, the next step is to configure the policy-based QoS settings within a Group Policy object.</span></span> <span data-ttu-id="8c3be-282">[ポート範囲および Skype ビジネス サーバー用のクライアントにサービスの品質ポリシー](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)を構成する手順の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8c3be-282">You can find more information about these steps in [Configuring port ranges and a Quality of Service policy for your clients on Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10).</span></span>

<span data-ttu-id="8c3be-283">QoS 10 の Windows コンピューターのオーディオのポリシー、グループ ポリシーの管理がインストールされているコンピューターに最初のログオンを作成します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-283">To create a QoS audio policy for Windows 10 computers, first log on to a computer on which Group Policy Management has been installed.</span></span> <span data-ttu-id="8c3be-284">グループ ポリシーの管理] を開きます ([開始] をクリックして、管理ツール] をポイントし、[グループ ポリシーの管理] をクリック) し、次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-284">Open Group Policy Management (click Start, point to Administrative Tools, and then click Group Policy Management), and then complete the following steps:</span></span>

1. <span data-ttu-id="8c3be-285">グループ ポリシーの管理では、新しいポリシーを作成するコンテナーを探します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-285">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="8c3be-286">たとえば、OU という名前の**クライアント**には、すべてのクライアント コンピューターが存在する場合、クライアント OU で新しいポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c3be-286">For example, if all your client computers are located in an OU named **Clients**, the new policy should be created in the Client OU.</span></span>

2. <span data-ttu-id="8c3be-287">適切なコンテナーを右クリックし、**このドメインに GPO を作成しここにリンク**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-287">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3. <span data-ttu-id="8c3be-288">**新しい GPO** ] ダイアログ ボックスで **[名前**] ボックスに新しいグループ ポリシー オブジェクトの名前を入力し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-288">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4. <span data-ttu-id="8c3be-289">新しく作成したポリシーを右クリックし、し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-289">Right-click the newly created policy, and then click **Edit**.</span></span>

5. <span data-ttu-id="8c3be-290">グループ ポリシー管理エディターで、**コンピューター**の構成**Windows の設定**を展開し、**ポリシー ベースの QoS**を右クリックし、**新規ポリシーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-290">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6. <span data-ttu-id="8c3be-291">**ポリシー ベースの QoS** ] ダイアログ ボックスで [開始] ページで、 **[名前**] ボックスで新しいポリシーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-291">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="8c3be-292">**DSCP 値を指定**を選択し、 **46**に値を設定します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-292">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="8c3be-293">オフの場合、**アウト バウンドのスロットル率を指定**のままにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-293">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7. <span data-ttu-id="8c3be-294">次のページでは、**すべてのアプリケーション**が選択されているかどうかを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-294">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="8c3be-295">この設定は、特定のアプリケーションによって作成された、46 のだけではなくパケットの DSCP のマークが付いたすべてのパケットを検索するネットワークを指示します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-295">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

8. <span data-ttu-id="8c3be-296">3 番目のページでは、**任意の発信元 IP アドレス**と**宛先の IP アドレス**の両方が選択されているし、[**次へ**] をクリックを確認します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-296">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="8c3be-297">これら 2 つの設定では、パケットが管理されることを確認してどのコンピューター (IP アドレス) がパケットを送信し、パケットをどのコンピューター (IP アドレス) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8c3be-297">These two settings ensure that packets will be managed regardless of which computer (IP address) sent the packets and which computer (IP address) will receive the packets.</span></span>

9. <span data-ttu-id="8c3be-298">[4] ページでは、**この QoS ポリシーを適用するプロトコルを選択**」ドロップ ダウン リストから**TCP および UDP**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-298">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** drop-down list.</span></span> <span data-ttu-id="8c3be-299">TCP (伝送制御プロトコル) と UDP (ユーザー データグラム プロトコル) は、最も一般的に使用される 2 つのネットワーク プロトコルです。</span><span class="sxs-lookup"><span data-stu-id="8c3be-299">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most commonly used.</span></span>

10. <span data-ttu-id="8c3be-300">**発信元ポート番号の指定**の見出しの下には、**この送信元ポートまたは範囲から**選択します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-300">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="8c3be-301">付随するテキスト ボックスで、オーディオの転送用に予約されたポートの範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-301">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="8c3be-302">50019 オーディオ トラフィック用のポートをポート 50000 を予約する場合のこの形式を使用するポートの範囲を入力するたとえば、: **50000:50019**。</span><span class="sxs-lookup"><span data-stu-id="8c3be-302">For example, if you reserved ports 50000 through ports 50019 for audio traffic, enter the port range using this format: **50000:50019**.</span></span> <span data-ttu-id="8c3be-303">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-303">Click **Finish**.</span></span>

<span data-ttu-id="8c3be-304">クライアント コンピューターにグループ ポリシーを更新するまでは、作成した新しいポリシーを有効になります。</span><span class="sxs-lookup"><span data-stu-id="8c3be-304">The new policies you’ve created won’t take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="8c3be-305">グループ ポリシーは、独自に定期的に更新されたが即時更新を強制することができます。</span><span class="sxs-lookup"><span data-stu-id="8c3be-305">Although Group Policy periodically refreshes on its own, you can force an immediate refresh.</span></span>

### <a name="force-group-policy-refresh"></a><span data-ttu-id="8c3be-306">フォースのグループ ポリシーの更新</span><span class="sxs-lookup"><span data-stu-id="8c3be-306">Force Group Policy refresh</span></span>

1. <span data-ttu-id="8c3be-307">グループ ポリシーを更新する各コンピューターでは、コマンド コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="8c3be-307">On each computer for which you want to refresh Group Policy, open a command console.</span></span> <span data-ttu-id="8c3be-308">コマンド コンソールを管理者として実行するように設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-308">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="8c3be-309">コマンド プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-309">At the command prompt, enter</span></span>
   ```
    gpudate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a><span data-ttu-id="8c3be-310">グループ ポリシー オブジェクト内の DSCP マーキングを確認します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-310">Verify DSCP markings in the Group Policy object</span></span>

<span data-ttu-id="8c3be-311">グループ ポリシー オブジェクトの値が設定されていることを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-311">To verify that the values from the Group Policy object have been set, perform the following steps.</span></span>

1. <span data-ttu-id="8c3be-312">コマンド コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="8c3be-312">Open a command console.</span></span> <span data-ttu-id="8c3be-313">コマンド コンソールを管理者として実行するように設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-313">Ensure that the command console is set to run as administrator.</span></span>

2. <span data-ttu-id="8c3be-314">コマンド プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-314">At the command prompt, enter</span></span> 
   ```
   gpresult /R >gp.txt
   ```

   <span data-ttu-id="8c3be-315">レポートを生成、gp.txt をという名前のテキスト ファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-315">This will generate a report and send it to a text file named gp.txt.</span></span> <span data-ttu-id="8c3be-316">代わりに、gp.html という名前の読みやすい html 形式のレポートで同じデータを生成するのには次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-316">Alternatively, you can enter the following command to produce the same data in a more readable HTML report named gp.html:</span></span>
   ```
   gpresult /H >gp.html
   ```

   <span data-ttu-id="8c3be-317">![Gpresult コマンドを実行しているコンソール ・ ウィンドウのスクリーン ショットです]。(media/Qos-in-Teams-Image3.png "Gpresult コマンドを実行しているコンソール ・ ウィンドウのスクリーン ショットです")。</span><span class="sxs-lookup"><span data-stu-id="8c3be-317">![Screenshot of the console window running the gpresult command.](media/Qos-in-Teams-Image3.png "Screenshot of the console window running the gpresult command.")</span></span>

3. <span data-ttu-id="8c3be-318">、生成されたファイルで**適用されたグループ ポリシー オブジェクト**の見出しを検索し、以前に作成したグループ ポリシー オブジェクトの名前に適用されたポリシーの一覧であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-318">In the generated file, look for the heading **Applied Group Policy Objects** and verify that the names of the Group Policy objects created earlier are in the list of applied policies.</span></span> 

4. <span data-ttu-id="8c3be-319">レジストリ エディターを開きとに移動します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-319">Open the Registry Editor, and go to:</span></span>

   <span data-ttu-id="8c3be-320">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\\</span><span class="sxs-lookup"><span data-stu-id="8c3be-320">HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\\</span></span>

   <span data-ttu-id="8c3be-321">表 4 に記載されているレジストリ エントリの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-321">Verify the values for the registry entries listed in Table 4.</span></span>

   <span data-ttu-id="8c3be-322">_表 4 です。QoS の Windows のレジストリ エントリの値_</span><span class="sxs-lookup"><span data-stu-id="8c3be-322">_Table 4. Values for Windows registry entries for QoS_</span></span>


   |          <span data-ttu-id="8c3be-323">名前</span><span class="sxs-lookup"><span data-stu-id="8c3be-323">Name</span></span>          |  <span data-ttu-id="8c3be-324">種類</span><span class="sxs-lookup"><span data-stu-id="8c3be-324">Type</span></span>  |    <span data-ttu-id="8c3be-325">データ</span><span class="sxs-lookup"><span data-stu-id="8c3be-325">Data</span></span>     |
   |------------------------|--------|-------------|
   |    <span data-ttu-id="8c3be-326">Application Name</span><span class="sxs-lookup"><span data-stu-id="8c3be-326">Application Name</span></span>    | <span data-ttu-id="8c3be-327">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8c3be-327">REG_SZ</span></span> |  <span data-ttu-id="8c3be-328">Teams.exe</span><span class="sxs-lookup"><span data-stu-id="8c3be-328">Teams.exe</span></span>  |
   |       <span data-ttu-id="8c3be-329">DSCP Value</span><span class="sxs-lookup"><span data-stu-id="8c3be-329">DSCP Value</span></span>       | <span data-ttu-id="8c3be-330">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8c3be-330">REG_SZ</span></span> |     <span data-ttu-id="8c3be-331">46</span><span class="sxs-lookup"><span data-stu-id="8c3be-331">46</span></span>      |
   |        <span data-ttu-id="8c3be-332">Local IP</span><span class="sxs-lookup"><span data-stu-id="8c3be-332">Local IP</span></span>        | <span data-ttu-id="8c3be-333">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8c3be-333">REG_SZ</span></span> |     \*      |
   | <span data-ttu-id="8c3be-334">Local IP Prefix Length</span><span class="sxs-lookup"><span data-stu-id="8c3be-334">Local IP Prefix Length</span></span> | <span data-ttu-id="8c3be-335">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8c3be-335">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="8c3be-336">Local Port</span><span class="sxs-lookup"><span data-stu-id="8c3be-336">Local Port</span></span>       | <span data-ttu-id="8c3be-337">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8c3be-337">REG_SZ</span></span> | <span data-ttu-id="8c3be-338">50000-50019</span><span class="sxs-lookup"><span data-stu-id="8c3be-338">50000-50019</span></span> |
   |        <span data-ttu-id="8c3be-339">プロトコル</span><span class="sxs-lookup"><span data-stu-id="8c3be-339">Protocol</span></span>        | <span data-ttu-id="8c3be-340">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8c3be-340">REG_SZ</span></span> |     \*      |
   |       <span data-ttu-id="8c3be-341">Remote IP</span><span class="sxs-lookup"><span data-stu-id="8c3be-341">Remote IP</span></span>        | <span data-ttu-id="8c3be-342">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8c3be-342">REG_SZ</span></span> |     \*      |
   |    <span data-ttu-id="8c3be-343">リモート IP プレフィックス</span><span class="sxs-lookup"><span data-stu-id="8c3be-343">Remote IP Prefix</span></span>    | <span data-ttu-id="8c3be-344">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8c3be-344">REG_SZ</span></span> |     \*      |
   |      <span data-ttu-id="8c3be-345">Remote Port</span><span class="sxs-lookup"><span data-stu-id="8c3be-345">Remote Port</span></span>       | <span data-ttu-id="8c3be-346">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8c3be-346">REG_SZ</span></span> |     \*      |
   |     <span data-ttu-id="8c3be-347">Throttle Rate</span><span class="sxs-lookup"><span data-stu-id="8c3be-347">Throttle Rate</span></span>      | <span data-ttu-id="8c3be-348">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8c3be-348">REG_SZ</span></span> |     <span data-ttu-id="8c3be-349">-1</span><span class="sxs-lookup"><span data-stu-id="8c3be-349">-1</span></span>      |


5. <span data-ttu-id="8c3be-350">アプリケーション名のエントリの値が使用しているクライアントに対して適切であることを確認し、DSCP 値とローカル ・ ポートの両方のエントリに、グループ ポリシー オブジェクトの設定が反映されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-350">Verify that the value for the Application Name entry is correct for the client you’re using, and verify that both the DSCP Value and Local Port entries reflect the settings in the Group Policy object.</span></span>

## <a name="validate-qos-by-analyzing-teams-traffic-on-the-network"></a><span data-ttu-id="8c3be-351">チーム ネットワーク上のトラフィックを分析して QoS を検証します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-351">Validate QoS by analyzing Teams traffic on the network</span></span>

<span data-ttu-id="8c3be-352">QoS を有効にする、DSCP の値によって、グループ ポリシー オブジェクト セットは、呼び出しの両端に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c3be-352">For QoS to be effective, the DSCP value set by the Group Policy object needs to be present at both ends of a call.</span></span> <span data-ttu-id="8c3be-353">DSCP 値が変更またはチームの作業負荷のトラフィックの移動を走査するときに削除されていないを確認するチームのクライアントによって生成されるトラフィックを見て、ネットワークを経由します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-353">By looking at the traffic generated by the Teams client, you can verify that the DSCP value isn’t changed or stripped out when the Teams workload traffic traverses moves through the network.</span></span>

<span data-ttu-id="8c3be-354">可能であれば、ネットワークの出口ポイントへのトラフィックをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="8c3be-354">Preferably, you capture traffic at the network egress point.</span></span> <span data-ttu-id="8c3be-355">これを支援するには、スイッチまたはルーターのポートのミラーリングを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-355">You can use port mirroring on a switch or router to help with this.</span></span>

### <a name="use-network-monitor-to-verify-dscp-values"></a><span data-ttu-id="8c3be-356">DSCP 値を確認するのにはネットワーク モニターを使用して</span><span class="sxs-lookup"><span data-stu-id="8c3be-356">Use Network Monitor to verify DSCP values</span></span>

<span data-ttu-id="8c3be-357">ネットワーク モニターは、ネットワーク トラフィックを分析するのには[マイクロソフトからダウンロード](https://www.microsoft.com/download/4865)をすることができますツールです。</span><span class="sxs-lookup"><span data-stu-id="8c3be-357">Network Monitor is a tool you can [download from Microsoft](https://www.microsoft.com/download/4865) to analyze network traffic.</span></span>

1. <span data-ttu-id="8c3be-358">PC では、ネットワーク モニターを実行して、ポートのミラーリングとパケットをキャプチャ開始のように構成されたポートに接続します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-358">On the PC running Network Monitor, connect to the port that has been configured for port mirroring and start capturing packets.</span></span> 

2. <span data-ttu-id="8c3be-359">チームのクライアントを使用して呼び出しを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-359">Make a call by using the Teams client.</span></span> <span data-ttu-id="8c3be-360">呼び出しを切断する前にメディアが確立されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-360">Make sure media has been established before hanging up the call.</span></span> 

3. <span data-ttu-id="8c3be-361">キャプチャを停止します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-361">Stop the capture.</span></span>

4. <span data-ttu-id="8c3be-362">[**ディスプレイ フィルター** ] フィールドで、呼び出しを行った PC のソース IP アドレスを使用し、検索条件として DSCP 値 (16 進コードは 0xb8 という) 46 を定義することで次の例に示すようにフィルターを絞り込みます。</span><span class="sxs-lookup"><span data-stu-id="8c3be-362">In the **Display Filter** field, use the source IP address of the PC that made the call, and refine the filter by defining DSCP value 46 (hex 0xb8) as search criteria, as shown in the following example:</span></span>

    <span data-ttu-id="8c3be-363">Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8</span><span class="sxs-lookup"><span data-stu-id="8c3be-363">Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8</span></span> 

    <span data-ttu-id="8c3be-364">![を適用するフィルターを示すネットワーク モニターで [ディスプレイ フィルター] ダイアログ ボックスのスクリーン ショットです]。(media/Qos-in-Teams-Image4.png "を適用するフィルターを示すネットワーク モニターで [ディスプレイ フィルター] ダイアログ ボックスのスクリーン ショットです")。</span><span class="sxs-lookup"><span data-stu-id="8c3be-364">![Screenshot of the Display Filter dialog box in Network Monitor, showing the filters to apply.](media/Qos-in-Teams-Image4.png "Screenshot of the Display Filter dialog box in Network Monitor, showing the filters to apply.")</span></span>

5. <span data-ttu-id="8c3be-365">フィルターを有効に**適用**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-365">Select **Apply** to activate the filter.</span></span>

6. <span data-ttu-id="8c3be-366">**フレームの概要**ウィンドウで、最初に UDP パケットを選択します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-366">In the **Frame Summary** window, select the first UDP packet.</span></span>

7. <span data-ttu-id="8c3be-367">**フレームの詳細**ウィンドウで、IPv4] ボックスの一覧のアイテムを展開し、 **DSCP**で始まる行の末尾の値に注意してください。</span><span class="sxs-lookup"><span data-stu-id="8c3be-367">In the **Frame Details** window, expand the IPv4 list item and note the value at the end of the line that begins with **DSCP**.</span></span> 

    <span data-ttu-id="8c3be-368">![DSCP 設定を強調表示、ネットワーク モニターのフレームの詳細] ダイアログ ボックスのスクリーン ショットです]。(media/Qos-in-Teams-Image5.png "DSCP 設定を強調表示、ネットワーク モニターのフレームの詳細] ダイアログ ボックスのスクリーン ショットです")。</span><span class="sxs-lookup"><span data-stu-id="8c3be-368">![Screenshot of the Frame Details dialog box in Network Monitor, highlighting DSCP settings.](media/Qos-in-Teams-Image5.png "Screenshot of the Frame Details dialog box in Network Monitor, highlighting DSCP settings.")</span></span>

<span data-ttu-id="8c3be-369">この例では、DSCP 値は 46 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="8c3be-369">In this example, the DSCP value is set to 46.</span></span> <span data-ttu-id="8c3be-370">これは、正しいために使用するソース ポートは、50019、音声のワークロードがあることを示します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-370">This is correct, because the source port used is 50019, which indicates that this is a voice workload.</span></span> 

<span data-ttu-id="8c3be-371">GPO によってマーキングされている各ワークロードについて確認を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8c3be-371">Repeat the verification for each workload that has been marked by the GPO.</span></span> 

## <a name="more-information"></a><span data-ttu-id="8c3be-372">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8c3be-372">More information</span></span>

[<span data-ttu-id="8c3be-373">Microsoft Teams 用に組織のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="8c3be-373">Prepare your organization's network for Microsoft Teams</span></span>](prepare-network.md)

[<span data-ttu-id="8c3be-374">ExpressRout QoS 要件</span><span class="sxs-lookup"><span data-stu-id="8c3be-374">ExpressRout QoS requirements</span></span>](https://docs.microsoft.com/azure/expressroute/expressroute-qos)