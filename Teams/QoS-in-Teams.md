---
title: Microsoft Teams でサービス品質を実装する
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Microsoft Teams でサービス品質 (QoS) を実装するために組織のネットワークを準備する方法を説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.qos
- ms.teamsadmincenter.meetingsettings.network.qosmarkers
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c07e3e71d391123d34ae64ebf5806c090c29a29d
ms.sourcegitcommit: e29e38bf00536400e5826fc55bc86dfd6ed761f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "50558206"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a><span data-ttu-id="c65e4-103">Microsoft Teams でサービス品質 (QoS) を実装する</span><span class="sxs-lookup"><span data-stu-id="c65e4-103">Implement Quality of Service (QoS) in Microsoft Teams</span></span>

<span data-ttu-id="c65e4-104">Microsoft Teams でサービス品質 (QoS) を使用すると、ネットワークの遅延の影響を受けやすいリアルタイムのネットワーク トラフィック (音声ストリームやビデオストリームなど) が、影響を受けにくいトラフィック (新しいアプリのダウンロードなど。ダウンロードに数秒長くかかることは大きな問題ではありません) の前に "横入り" できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-104">Quality of Service (QoS) in Microsoft Teams allows real-time network traffic that's sensitive to network delays (for example, voice or video streams) to "cut in line" in front of traffic that's less sensitive (like downloading a new app, where an extra second to download isn't a large deal).</span></span> <span data-ttu-id="c65e4-105">QoS は、Windows グループ ポリシー オブジェクトとポートベースのアクセス制御リストを使用して、リアルタイム ストリーム内のすべてのパケットを識別してマークします。</span><span class="sxs-lookup"><span data-stu-id="c65e4-105">QoS uses Windows Group Policy Objects and Port-based Access Control Lists to identify and mark all packets in real-time streams.</span></span> <span data-ttu-id="c65e4-106">これは、ネットワークが音声、ビデオ、および画面共有ストリームにネットワーク帯域幅の専用の部分を提供するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-106">This helps your network to give voice, video, and screen share streams a dedicated portion of network bandwidth.</span></span>

<span data-ttu-id="c65e4-107">この記事で説明する問題のいずれかが発生している大規模なグループ ユーザーをサポートする場合は、QoS を実装する必要がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-107">If you support a large group of users who are experiencing any of the problems described in this article, then you probably need to implement QoS.</span></span> <span data-ttu-id="c65e4-108">ユーザー数が少ない小規模企業では、QoS を必要としない場合がありますが、それらの企業においても役立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-108">A small business with few users might not need QoS, but even there it should be helpful.</span></span>

<span data-ttu-id="c65e4-109">何らかの形で QoS を使用しないと、音声とビデオで以下のような品質上の問題が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-109">Without some form of QoS, you might see the following quality issues in voice and video:</span></span>

- <span data-ttu-id="c65e4-110">ジッター – メディア パケットが異なるレートで到着すると、通話で語や音節が欠落する可能性があります</span><span class="sxs-lookup"><span data-stu-id="c65e4-110">Jitter – media packets arriving at different rates, which can result in missing words or syllables in calls</span></span>
- <span data-ttu-id="c65e4-111">パケット損失 – パケットが脱落すると、音声品質が低下したり、音声の理解が困難になったりすることがあります</span><span class="sxs-lookup"><span data-stu-id="c65e4-111">Packet loss – packets dropped, which can also result in lower voice quality and hard to understand speech</span></span>
- <span data-ttu-id="c65e4-112">ラウンド トリップ時間 (RTT) の遅延 – メディア パケットが宛先に到達するのに長い時間がかかります。それにより、会話する二者間で顕著な遅延が生じ、両者が同時に話す現象を引き起こします</span><span class="sxs-lookup"><span data-stu-id="c65e4-112">Delayed round-trip time (RTT) – media packets taking a long time to reach their destinations, which result in noticeable delays between two parties in a conversation and causes people to talk over each other</span></span>

<span data-ttu-id="c65e4-113">これらの問題に対処する最も簡単な方法は、内部とインターネットへの出力の両方でデータ接続のサイズを増やすことです。</span><span class="sxs-lookup"><span data-stu-id="c65e4-113">The least complex way to address these issues is to increase the size of the data connections, both internally and out to the internet.</span></span> <span data-ttu-id="c65e4-114">その方法は多大なコストがかかることが多いため、QoS では、帯域幅を追加する代わりに、所有しているリソースをより効果的に管理する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="c65e4-114">Since that is often cost-prohibitive, QoS provides a way to more effectively manage the resources you have instead of adding bandwidth.</span></span> <span data-ttu-id="c65e4-115">品質の問題に対処するには、最初に QoS を使用してから、必要な場合にのみ帯域幅を追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c65e4-115">To address quality issues, we recommend that you first use QoS, then add bandwidth only where necessary.</span></span>

<span data-ttu-id="c65e4-116">QoS を有効にするには、組織全体に一貫性のある QoS 設定を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-116">For QoS to be effective, you must apply consistent QoS settings throughout your organization.</span></span> <span data-ttu-id="c65e4-117">QoS の優先順位をサポートできないパスの部分では、通話、ビデオ、および画面共有の品質が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-117">Any part of the path that fails to support your QoS priorities can degrade the quality of calls, video, and screen sharing.</span></span> <span data-ttu-id="c65e4-118">これには、すべてのユーザーの PC、デバイス、ネットワーク スイッチ、インターネットへのルーター、および Teams サービスに対する設定の適用が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-118">This includes applying settings to all user PCs or devices, network switches, routers to the internet, and the Teams service.</span></span>

<span data-ttu-id="c65e4-119">_図 1. 組織のネットワークと Microsoft 365 または Office 365 サービス間の関係_</span><span class="sxs-lookup"><span data-stu-id="c65e4-119">_Figure 1. The relationship between an organization's networks and Microsoft 365 or Office 365 services_</span></span>

<span data-ttu-id="c65e4-120">![ネットワークとサービスの関係を示す図](media/Qos-in-Teams-Image1.png "組織のネットワークと Microsoft 365 および Office 365 サービスの間の関係: オンプレミスのネットワークとデバイスは、相互接続ネットワークに接続します。相互接続ネットワークは、Microsoft 365 および Office 365 のクラウド ボイスと電話会議のサービスに接続します。")</span><span class="sxs-lookup"><span data-stu-id="c65e4-120">![Illustration of the relationship between networks and services](media/Qos-in-Teams-Image1.png "The relationship between an organization's networks and Microsoft 365 or Office 365 services: on-premises network and devices connect with an interconnect network, which in turn connects with Microsoft 365 or Office 365 Cloud Voice and Audio Conferencing services.")</span></span>

## <a name="qos-implementation-checklist"></a><span data-ttu-id="c65e4-121">QoS の実装のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="c65e4-121">QoS implementation checklist</span></span>

<span data-ttu-id="c65e4-122">上位レベルでは、QoS を実装するために以下のことを行います。</span><span class="sxs-lookup"><span data-stu-id="c65e4-122">At a high level, do the following to implement QoS:</span></span>

1. <span data-ttu-id="c65e4-123">[ネットワークの準備ができていることを確認します](#make-sure-your-network-is-ready)。</span><span class="sxs-lookup"><span data-stu-id="c65e4-123">[Make sure your network is ready](#make-sure-your-network-is-ready).</span></span>

1. <span data-ttu-id="c65e4-124">[QoS 実装方法を選択します](#select-a-qos-implementation-method)。</span><span class="sxs-lookup"><span data-stu-id="c65e4-124">[Select a QoS implementation method](#select-a-qos-implementation-method).</span></span>

1. <span data-ttu-id="c65e4-125">[メディアの種類ごとに初期ポート範囲を選択します](#choose-initial-port-ranges-for-each-media-type)。</span><span class="sxs-lookup"><span data-stu-id="c65e4-125">[Choose initial port ranges for each media type](#choose-initial-port-ranges-for-each-media-type).</span></span>

1. <span data-ttu-id="c65e4-126">以下のように QoS 設定を実装する:</span><span class="sxs-lookup"><span data-stu-id="c65e4-126">Implement QoS settings:</span></span>
   1. <span data-ttu-id="c65e4-127">グループ ポリシー オブジェクト (GPO) を使用してクライアント デバイスのポート範囲とマーキングを設定するクライアント [の場合](QoS-in-Teams-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="c65e4-127">On clients using a Group Policy Object (GPO) to [set client device port ranges and markings](QoS-in-Teams-clients.md).</span></span>
   2. <span data-ttu-id="c65e4-128">ルーター (製造元の資料を参照) または他のネットワーク デバイスで実装します。</span><span class="sxs-lookup"><span data-stu-id="c65e4-128">On routers (see the manufacturer documentation) or other network devices.</span></span> <span data-ttu-id="c65e4-129">これには、ポートベースのアクセス制御リスト (ACL) を含めるか、単に QoS キューと DSCP マーキングを定義するか、またはこれらすべてを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-129">This might include port-based Access Control Lists (ACLs) or simply defining the QoS queues and DSCP markings, or all of these.</span></span>

      > [!IMPORTANT]
      > <span data-ttu-id="c65e4-130">これらの QoS ポリシーは、クライアントの送信元ポートと、送信元と宛先の IP アドレスを "any"として実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c65e4-130">We recommend implementing these QoS policies using the client source ports and a source and destination IP address of “any.”</span></span> <span data-ttu-id="c65e4-131">これにより、内部ネットワーク上の受信と送信の両方のメディア トラフィックがキャッチされます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-131">This will catch both incoming and outgoing media traffic on the internal network.</span></span>  

   3. <span data-ttu-id="c65e4-132">[Teams 会議のメディア トラフィックを処理する方法を設定します](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。</span><span class="sxs-lookup"><span data-stu-id="c65e4-132">[Set how you want to handle media traffic for Teams meetings](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).</span></span>

5. <span data-ttu-id="c65e4-133">ネットワーク上の Teams トラフィックを分析して [QoS 実装を検証](#validate-your-qos-implementation)します。</span><span class="sxs-lookup"><span data-stu-id="c65e4-133">[Validate your QoS implementation](#validate-your-qos-implementation) by analyzing Teams traffic on the network.</span></span>

<span data-ttu-id="c65e4-134">QoS の実装を準備する際には、次のガイドラインに留意してください。</span><span class="sxs-lookup"><span data-stu-id="c65e4-134">As you prepare to implement QoS, keep the following guidelines in mind:</span></span>

- <span data-ttu-id="c65e4-135">Microsoft 365 への最短パスが最適です。</span><span class="sxs-lookup"><span data-stu-id="c65e4-135">The shortest path to Microsoft 365 is best.</span></span>
- <span data-ttu-id="c65e4-136">ポートを閉じると、品質の低下のみを引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-136">Closing ports will only lead to quality degradation.</span></span>
- <span data-ttu-id="c65e4-137">プロキシなど、その間の問題は推奨されません。</span><span class="sxs-lookup"><span data-stu-id="c65e4-137">Any obstacles in between, such as proxies, aren't recommended.</span></span>
- <span data-ttu-id="c65e4-138">ポップ数を制限します:</span><span class="sxs-lookup"><span data-stu-id="c65e4-138">Limit the number of hops:</span></span>
  - <span data-ttu-id="c65e4-139">クライアントからネットワーク エッジ - 3 から 5 ホップ</span><span class="sxs-lookup"><span data-stu-id="c65e4-139">Client to network edge – 3 to 5 hops</span></span>
  - <span data-ttu-id="c65e4-140">ISP から Microsoft ネットワーク エッジ - 3 ホップ</span><span class="sxs-lookup"><span data-stu-id="c65e4-140">ISP to Microsoft network edge – 3 hops</span></span>
  - <span data-ttu-id="c65e4-141">Microsoft ネットワーク エッジから最終目的地 - 無関係</span><span class="sxs-lookup"><span data-stu-id="c65e4-141">Microsoft network edge to final destination – irrelevant</span></span>

<span data-ttu-id="c65e4-142">ファイアウォールのポートの構成については、「[Office 365 の URL と IP 範囲](office-365-urls-ip-address-ranges.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c65e4-142">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

## <a name="make-sure-your-network-is-ready"></a><span data-ttu-id="c65e4-143">ネットワークの準備ができていることを確認する</span><span class="sxs-lookup"><span data-stu-id="c65e4-143">Make sure your network is ready</span></span>

<span data-ttu-id="c65e4-144">QoS の実装を検討している場合、帯域幅の要件と他の[ネットワーク要件](prepare-network.md)が既に特定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-144">If you're considering a QoS implementation, you should already have determined your bandwidth requirements and other [network requirements](prepare-network.md).</span></span>
  
<span data-ttu-id="c65e4-145">ネットワーク全体のトラフィックの輻輳は、メディアの品質に大きく影響します。</span><span class="sxs-lookup"><span data-stu-id="c65e4-145">Traffic congestion across a network will greatly impact media quality.</span></span> <span data-ttu-id="c65e4-146">帯域幅が不足すると、パフォーマンスが低下し、ユーザー エクスペリエンスの品質低下につながります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-146">A lack of bandwidth leads to performance degradation and a poor user experience.</span></span> <span data-ttu-id="c65e4-147">Teams を導入し、使用量が増えたときに、レポート、[ユーザーごとの通話分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)、[通話品質ダッシュボード (CQD)](turning-on-and-using-call-quality-dashboard.md)を使用して問題を特定し、QoS と追加の選択的な帯域幅を使用して調整を行います。</span><span class="sxs-lookup"><span data-stu-id="c65e4-147">As Teams adoption and usage grows, use reporting, [per-user call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md), and [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to identify problems and then make adjustments using QoS and selective bandwidth additions.</span></span>

### <a name="vpn-considerations"></a><span data-ttu-id="c65e4-148">VPN に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="c65e4-148">VPN considerations</span></span>

<span data-ttu-id="c65e4-149">QoS が期待どおりに機能するのは、発信者間のすべてのリンクで実装されている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="c65e4-149">QoS only works as expected when implemented on all links between callers.</span></span> <span data-ttu-id="c65e4-150">内部ネットワークで QoS を使用しているときにユーザーがリモートの場所からサインインする場合、管理された内部ネットワーク内でのみ優先順位付けをすることができます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-150">If you use QoS on an internal network and a user signs in from a remote location, you can only prioritize within your internal, managed network.</span></span> <span data-ttu-id="c65e4-151">リモートの場所でも仮想プライベート ネットワーク (VPN) を実装することによって管理された接続を受信できますが、VPN では本質的にパケットにオーバーヘッドが追加されるので、リアルタイムのトラフィックに遅延が生じます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-151">Although remote locations can receive a managed connection by implementing a virtual private network (VPN),  a VPN inherently adds packet overhead and creates delays in real-time traffic.</span></span> <span data-ttu-id="c65e4-152">VPN を使用したリアルタイム通信トラフィックの実行は避けることをお勧めしています。</span><span class="sxs-lookup"><span data-stu-id="c65e4-152">We  recommend that you avoid running real-time communications traffic over a VPN.</span></span>

<span data-ttu-id="c65e4-153">大陸間で管理されたリンクを使用するグローバル組織では、そのようなリンクの帯域幅は LAN と比較して制限されるため QoS を強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="c65e4-153">In a global organization with managed links that span continents, we strongly recommend QoS because bandwidth for those links is limited in comparison to the LAN.</span></span>

## <a name="introduction-to-qos-queues"></a><span data-ttu-id="c65e4-154">QoS キューの概要</span><span class="sxs-lookup"><span data-stu-id="c65e4-154">Introduction to QoS queues</span></span>

<span data-ttu-id="c65e4-155">QoS を提供するには、ネットワーク デバイスでトラフィックを分類する手段が必要であり、他のネットワーク トラフィックから音声やビデオを区別できなければなりません。</span><span class="sxs-lookup"><span data-stu-id="c65e4-155">To provide QoS, network devices must have a way to classify traffic and must be able to distinguish voice or video from other network traffic.</span></span>

<span data-ttu-id="c65e4-156">ネットワーク トラフィックがルーターに入ったら、トラフィックはキューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-156">When network traffic enters a router, the traffic is placed into a queue.</span></span> <span data-ttu-id="c65e4-157">QoS ポリシーが構成されていない場合、1 つのキューのみが存在し、すべてのデータは同じ優先順位を持ち、先入先出法で処理されます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-157">If a QoS policy isn't configured, there is only one queue, and all data is treated as first-in, first-out with the same priority.</span></span> <span data-ttu-id="c65e4-158">これは、遅延に極めて敏感な音声トラフィックが、数ミリ秒の遅延があっても問題とならないトラフィックにはさまれる可能性があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c65e4-158">That means voice traffic (which is very sensitive to delays) might get stuck behind traffic where a delay of a few extra milliseconds wouldn't be a problem.</span></span>

<span data-ttu-id="c65e4-159">QoS を実装するときは、Cisco のプライオリティ キューイングや [Class-Based Weighted Fair Queueing (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) などの輻輳管理機能のいずれかと、[重み付けランダム早期検出 (WRED)](https://en.wikipedia.org/wiki/Weighted_random_early_detection):などの輻輳回避機能を使用して、複数のキューを定義します。</span><span class="sxs-lookup"><span data-stu-id="c65e4-159">When you implement QoS, you define multiple queues using one of several congestion management features, such as Cisco’s priority queuing and [Class-Based Weighted Fair Queueing (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) and congestion avoidance features, such as [weighted random early detection (WRED)](https://en.wikipedia.org/wiki/Weighted_random_early_detection).</span></span>

<span data-ttu-id="c65e4-160">_図 2. QoS キューの例_</span><span class="sxs-lookup"><span data-stu-id="c65e4-160">_Figure 2. Examples of QoS queues_</span></span>

<span data-ttu-id="c65e4-161">![QoS キューと帯域幅分割の図](media/Qos-in-Teams-Image2.png "使用可能な合計帯域幅は、複数のキュー (オーディオ、ビデオ、その他のトラフィック) で分割されます。それらには、それぞれ異なる優先順位が割り当てられています。")</span><span class="sxs-lookup"><span data-stu-id="c65e4-161">![Illustration of QoS queues and bandwidth division](media/Qos-in-Teams-Image2.png "Total available bandwidth is divided among multiple queues—audio, video, and other traffic—that have been assigned different priorities.")</span></span>

<span data-ttu-id="c65e4-162">わかりやすく例えると、QoS ではデータ ネットワークに仮想の "相乗り車線" を作成して、一部の種類のデータでは遅延がまったく生じない、またはほとんど生じないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-162">A simple analogy is that QoS creates virtual "carpool lanes" in your data network so some types of data never or rarely encounter a delay.</span></span> <span data-ttu-id="c65e4-163">そのような車線を作成すると、組織ユーザーに提供するビジネス水準のエクスペリエンスを維持しながら、それらの車線の相対的なサイズを調整して、保有している接続帯域幅をより有効に管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-163">Once you create those lanes, you can adjust their relative size and much more effectively manage the connection bandwidth you have, while still delivering business-grade experiences for your organization's users.</span></span>

## <a name="select-a-qos-implementation-method"></a><span data-ttu-id="c65e4-164">QoS 実装方法を選択する</span><span class="sxs-lookup"><span data-stu-id="c65e4-164">Select a QoS implementation method</span></span>

<span data-ttu-id="c65e4-165">ネットワーク ルーターでアクセス制御リスト (ACL) を使用して、ポートベースのタグ付けによって QoS を実装できます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-165">You could implement QoS via port-based tagging, using Access Control Lists (ACLs) on your network's routers.</span></span> <span data-ttu-id="c65e4-166">ポートベースのタグ付けは、Windows、Mac、Linux が混在する環境で機能し、最も簡単に実装できることから、最も信頼性が高い方法といえます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-166">Port-based tagging is the most reliable method because it works in mixed Windows, Mac, and Linux environments and is the easiest to implement.</span></span> <span data-ttu-id="c65e4-167">モバイル クライアントでは、DSCP 値を使用してトラフィックをマークするメカニズムが提供されないため、この方法が必要になります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-167">Mobile clients don't provide a mechanism to mark traffic by using DSCP values, so they'll require this method.</span></span>  

<span data-ttu-id="c65e4-168">ポートベースのタグ付けを使用すると、ネットワーク ルーターが受信パケットを検査します。パケットが特定のポートまたはポート範囲を使用して到着すると、そのパケットは特定の種類のメディアとして識別されて該当する種類のキューに置かれます。その際、事前に定義された [DSCP](https://tools.ietf.org/html/rfc2474) マークが IP パケットのヘッダーに追加されます。これにより、他のデバイスはそのトラフィックの種類を認識して、キュー内で優先順位を付けられるようになります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-168">Using port-based tagging, your network's router examines an incoming packet, and if the packet arrived using a certain port or range of ports, it identifies it as a certain media type and puts it in the queue for that type, adding a predetermined [DSCP](https://tools.ietf.org/html/rfc2474) mark to the IP Packet header so other devices can recognize its traffic type and give it priority in their queue.</span></span>

<span data-ttu-id="c65e4-169">ポートベースのタグ付けは異なるプラットフォーム間で機能しますが、クライアント マシンに到達するまでの経路全体ではなく、WAN エッジにおいてのみトラフィックがマークされるため、管理のオーバーヘッドが生じます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-169">Although port-based tagging works across platforms, it only marks traffic at the WAN edge (not all the way to the client machine) and creates management overhead.</span></span> <span data-ttu-id="c65e4-170">この方法の実装手順については、ルーターの製造元から提供されたドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c65e4-170">Refer to the documentation provided by the router manufacturer for instructions on implementing this method.</span></span>

### <a name="insert-dscp-markers"></a><span data-ttu-id="c65e4-171">DSCP マーカーを挿入する</span><span class="sxs-lookup"><span data-stu-id="c65e4-171">Insert DSCP markers</span></span>

<span data-ttu-id="c65e4-172">グループ ポリシー オブジェクト (GPO) を使用して QoS をクライアント デバイスに直接実装し、特定の種類のトラフィック (音声など) であることを示す DSCP マーカーを IP パケットのヘッダーに挿入することもできます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-172">You could also implement QoS by using a Group Policy Object (GPO) to direct client devices to insert a DSCP marker in IP packet headers identifying it as particular type of traffic (for example, voice).</span></span> <span data-ttu-id="c65e4-173">ルーターとその他のネットワーク デバイスでは、これらのマーキングを認識し、トラフィックを優先度の高い個別のキューに配置するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-173">Routers and other network devices can be configured to recognize this and put the traffic in a separate, higher-priority queue.</span></span>

<span data-ttu-id="c65e4-174">このシナリオ全体は有効ですが、ドメインに参加している Windows クライアントでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="c65e4-174">Although this scenario is entirely valid, it will only work for domain-joined Windows clients.</span></span> <span data-ttu-id="c65e4-175">ドメインに参加している Windows クライアントではないデバイスでは、DSCP タグ付けが有効になりません。</span><span class="sxs-lookup"><span data-stu-id="c65e4-175">Any device that isn't a domain-joined Windows client won't be enabled for DSCP tagging.</span></span> <span data-ttu-id="c65e4-176">macOS を実行しているクライアントなど、他のクライアントにはハードコードされたタグが含まれます。常にトラフィックにタグが付けされます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-176">Other clients, such as those running macOS, have hard-coded tags and will always tag traffic.</span></span>

<span data-ttu-id="c65e4-177">利点としては、GPO を介して DSCP マーキングを制御することで、ドメインに参加しているすべてのコンピューターが同じ設定を受信し、管理者だけがそれを管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-177">On the plus side, controlling the DSCP marking via GPO ensures that all domain-joined computers receive the same settings and that only an administrator can manage them.</span></span> <span data-ttu-id="c65e4-178">GPO を使用できるクライアントは、元のデバイスでタグ付けされ、構成されたネットワーク デバイスでは DSCP コードによってリアルタイム ストリームを認識して、適切な優先順位を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-178">Clients that can use GPO will be tagged on the originating device, and then configured network devices can recognize the real-time stream by the DSCP code and give it an appropriate priority.</span></span>

### <a name="best-practice"></a><span data-ttu-id="c65e4-179">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="c65e4-179">Best practice</span></span>

<span data-ttu-id="c65e4-180">可能であれば、エンドポイントでの DSCP マーキングと、ルーターでのポートベースの ACL を組み合わせて使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c65e4-180">We recommend a combination of DSCP markings at the endpoint and port-based ACLs on routers, if possible.</span></span> <span data-ttu-id="c65e4-181">グループ ポリシー オブジェクトを使用して大部分のクライアントに対応し、同時にポートベースの DSCP タグ付けを使用すると、モバイル、Mac、その他のクライアントも (少なくとも部分的には) QoS の対象にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-181">Using a GPO to catch the majority of clients, and also using port-based DSCP tagging will ensure that mobile, Mac, and other clients will still get QoS treatment (at least partially).</span></span>

<span data-ttu-id="c65e4-182">DSCP マーキングは、郵便仕分けで押されるスタンプに例えることができます。スタンプによって、配達の緊急性と、迅速な配達を行うためにそれを分類する最善の方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-182">DSCP markings can be likened to postage stamps that indicate to postal workers how urgent the delivery is and how best to sort it for speedy delivery.</span></span> <span data-ttu-id="c65e4-183">リアルタイム メディア ストリームに優先順位を付けるようにネットワークを構成すると、パケットの損失とパケットの遅延が大幅に減少します。</span><span class="sxs-lookup"><span data-stu-id="c65e4-183">Once you've configured your network to give priority to real-time media streams, lost packets and late packets should diminish greatly.</span></span>

<span data-ttu-id="c65e4-184">ネットワーク内のすべてのデバイスで同じ分類、マーキング、優先順位が使用されるようにすると、各トラフィックの種類で使用されるキューに割り当てられたポート範囲のサイズを変更することで、遅延、パケットの損失、ジッターを低減または排除することができます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-184">Once all devices in the network are using the same classifications, markings, and priorities, it's possible to reduce or eliminate delays, dropped packets, and jitter by changing the size of the port ranges assigned to the queues used for each traffic type.</span></span> <span data-ttu-id="c65e4-185">Teams の観点からすると、最も重要な構成の手順は、パケットの分類とマーキングです。</span><span class="sxs-lookup"><span data-stu-id="c65e4-185">From the Teams perspective, the most important configuration step is the classification and marking of packets.</span></span> <span data-ttu-id="c65e4-186">ただし、エンドツーエンドの QoS を成功させるには、アプリケーションの構成を基盤となるネットワークの構成に慎重に合わせる必要もあります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-186">However, for end-to-end QoS to be successful, you also need to carefully align the application's configuration with the underlying network configuration.</span></span> <span data-ttu-id="c65e4-187">QoS が完全に実装された後は、組織のニーズと実際の使用状況に基づいて、各トラフィックの種類に割り当てられたポート範囲を調整することが、継続的な管理上の課題となります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-187">Once QoS is fully implemented, ongoing management is a question of adjusting the port ranges assigned to each traffic type based on your organization's needs and actual usage.</span></span>

## <a name="choose-initial-port-ranges-for-each-media-type"></a><span data-ttu-id="c65e4-188">各メディア タイプ用の初期ポート範囲を選択する</span><span class="sxs-lookup"><span data-stu-id="c65e4-188">Choose initial port ranges for each media type</span></span>

<span data-ttu-id="c65e4-189">DSCP 値は、パケットまたはストリームに与える優先順位と、DSCP マークがクライアントによって割り当てられているか、または ACL 設定に基づいてネットワーク自体によって割り当てられているかを、対応するように構成されたネットワークに示します。</span><span class="sxs-lookup"><span data-stu-id="c65e4-189">The DSCP value tells a correspondingly configured network what priority to give a packet or stream, whether the DSCP mark is assigned by clients or the network itself based on ACL settings.</span></span> <span data-ttu-id="c65e4-190">各メディアのワークロードには、固有の DSCP 値 (他のサービスでは DSCP マーキングの共有が許可されることがありますが、Teams では許可されません) と、各メディアの種類で使用される定義済みの個別のポート範囲が与えられます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-190">Each media workload gets its own unique DSCP value (other services might allow workloads to share a DSCP marking, Teams doesn't) and a defined and separate port range used for each media type.</span></span> <span data-ttu-id="c65e4-191">他の環境には既存の QoS 戦略がある場合があります。それは、ネットワーク ワークロードの優先順位を決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-191">Other environments might have an existing QoS strategy in place, which will help you determine the priority of network workloads.</span></span>

<span data-ttu-id="c65e4-192">各種のリアルタイム ストリーミング ワークロードのポート範囲の相対サイズによって、対象ワークロードが独占的に使用できる合計帯域幅のうちの比率が決まります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-192">The relative size of the port ranges for different real-time streaming workloads sets the proportion of the total available bandwidth dedicated to that workload.</span></span> <span data-ttu-id="c65e4-193">前述の郵便仕分けの例えに戻ると、"Air Mail" のスタンプが押された手紙は最寄りの空港まで 1 時間以内に到着する可能性がありますが、"大口郵便" とマークされた小包は何台ものトラックで陸送されるまでに 1 日待機する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-193">To return to our earlier postal analogy: a letter with an "Air Mail" stamp might get taken within an hour to the nearest airport, while a small package marked "Bulk Mail" mark can wait for a day before traveling over land on a series of trucks.</span></span>

<span data-ttu-id="c65e4-194">_推奨される初期ポート範囲_</span><span class="sxs-lookup"><span data-stu-id="c65e4-194">_Recommended initial port ranges_</span></span>

|<span data-ttu-id="c65e4-195">メディア トラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="c65e4-195">Media traffic type</span></span>| <span data-ttu-id="c65e4-196">クライアントの送信元ポート範囲</span><span class="sxs-lookup"><span data-stu-id="c65e4-196">Client source port range</span></span> |<span data-ttu-id="c65e4-197">プロトコル</span><span class="sxs-lookup"><span data-stu-id="c65e4-197">Protocol</span></span>|<span data-ttu-id="c65e4-198">DSCP 値</span><span class="sxs-lookup"><span data-stu-id="c65e4-198">DSCP value</span></span>|<span data-ttu-id="c65e4-199">DSCP クラス</span><span class="sxs-lookup"><span data-stu-id="c65e4-199">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="c65e4-200">オーディオ</span><span class="sxs-lookup"><span data-stu-id="c65e4-200">Audio</span></span>| <span data-ttu-id="c65e4-201">50,000–50,019</span><span class="sxs-lookup"><span data-stu-id="c65e4-201">50,000–50,019</span></span>|<span data-ttu-id="c65e4-202">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="c65e4-202">TCP/UDP</span></span>|<span data-ttu-id="c65e4-203">46</span><span class="sxs-lookup"><span data-stu-id="c65e4-203">46</span></span>|<span data-ttu-id="c65e4-204">完全優先転送 (EF)</span><span class="sxs-lookup"><span data-stu-id="c65e4-204">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="c65e4-205">ビデオ</span><span class="sxs-lookup"><span data-stu-id="c65e4-205">Video</span></span>| <span data-ttu-id="c65e4-206">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="c65e4-206">50,020–50,039</span></span>|<span data-ttu-id="c65e4-207">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="c65e4-207">TCP/UDP</span></span>|<span data-ttu-id="c65e4-208">34</span><span class="sxs-lookup"><span data-stu-id="c65e4-208">34</span></span>|<span data-ttu-id="c65e4-209">相対的優先転送 (AF41)</span><span class="sxs-lookup"><span data-stu-id="c65e4-209">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="c65e4-210">アプリケーション/画面共有</span><span class="sxs-lookup"><span data-stu-id="c65e4-210">Application/Screen Sharing</span></span>| <span data-ttu-id="c65e4-211">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="c65e4-211">50,040–50,059</span></span>|<span data-ttu-id="c65e4-212">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="c65e4-212">TCP/UDP</span></span>|<span data-ttu-id="c65e4-213">18</span><span class="sxs-lookup"><span data-stu-id="c65e4-213">18</span></span>|<span data-ttu-id="c65e4-214">相対的優先転送 (AF21)</span><span class="sxs-lookup"><span data-stu-id="c65e4-214">Assured Forwarding (AF21)</span></span>|
||||||

<span data-ttu-id="c65e4-215">これらの設定を使用する場合は、以下の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c65e4-215">Be aware of the following when you use these settings:</span></span>

- <span data-ttu-id="c65e4-216">将来 ExpressRoute を実装する予定で、まだ QoS を実装していない場合は、ガイダンスに従って、DSCP値が送信者と受信者間で同じになるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c65e4-216">If you plan to implement ExpressRoute in the future and haven't yet implemented QoS, we recommend that you follow the guidance so that DSCP values are the same from sender to receiver.</span></span>

- <span data-ttu-id="c65e4-217">モバイル クライアントや Teams デバイスを含むすべてのクライアントは、これらのポート範囲を使用し、これらの送信元ポート範囲を使用して実装するすべての DSCP ポリシーの影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-217">All clients, including mobile clients and Teams devices, will use these port ranges and will be affected by any DSCP policy you implement that uses these source port ranges.</span></span> <span data-ttu-id="c65e4-218">動的ポートを引き続き使用するクライアントは、ブラウザーベースのクライアント (参加者を各自のブラウザーを使用して会議に参加させるクライアント) のみです。</span><span class="sxs-lookup"><span data-stu-id="c65e4-218">The only clients that will continue to use dynamic ports are the browser-based clients (clients that let participants join meetings by using their browsers).</span></span>

- <span data-ttu-id="c65e4-219">Mac クライアントは同じポート範囲を使用しますが、オーディオ (EF) とビデオ (AF41) のハードコードされた値も使用します。</span><span class="sxs-lookup"><span data-stu-id="c65e4-219">Although the Mac client uses the same port ranges, it also uses hard-coded values for audio (EF) and video (AF41).</span></span> <span data-ttu-id="c65e4-220">これらの値を構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="c65e4-220">These values aren't configurable.</span></span>

- <span data-ttu-id="c65e4-221">ユーザー エクスペリエンスを向上させるために、後でポート範囲を調整する必要がある場合は、ポート範囲が重なることなく、相互に隣接するようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-221">If you later need to adjust the port ranges to improve user experience, the port ranges can't overlap and should be adjacent to each other.</span></span>

## <a name="migrate-qos-to-teams"></a><span data-ttu-id="c65e4-222">QoS を Teams に移行する</span><span class="sxs-lookup"><span data-stu-id="c65e4-222">Migrate QoS to Teams</span></span>

<span data-ttu-id="c65e4-223">以前に Skype for Business Online を展開したことがあり (QoS のタグ付けやポート範囲を含む)、現在 </span><span class="sxs-lookup"><span data-stu-id="c65e4-223">If you've previously deployed Skype for Business Online, including QoS tagging and port ranges, and are now deploying.</span></span> <span data-ttu-id="c65e4-224">Teams を展開している場合は、Teams は既存の構成を優先して、Skype for Business クライアントと同じポート範囲とタグ付けを使用します。</span><span class="sxs-lookup"><span data-stu-id="c65e4-224">Teams, Teams will respect the existing configuration and will use the same port ranges and tagging as the Skype for Business client.</span></span> <span data-ttu-id="c65e4-225">ほとんどの場合、追加の構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c65e4-225">In most cases, no additional configuration will be needed.</span></span>

> [!NOTE]
> <span data-ttu-id="c65e4-226">グループ ポリシーによってアプリケーション名の QoS タグ付けを使用している場合は、アプリケーション名として Teams.exe を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-226">If you're using Application Name QoS tagging via Group Policy, you must add Teams.exe as the application name.</span></span>

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a><span data-ttu-id="c65e4-227">PowerShell を使用して Windows 上の Teams に QoS を実装する</span><span class="sxs-lookup"><span data-stu-id="c65e4-227">Implement QoS in Teams on Windows using PowerShell</span></span>

<span data-ttu-id="c65e4-228">**オーディオ用に QoS を設定する**</span><span class="sxs-lookup"><span data-stu-id="c65e4-228">**Set QoS for audio**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000 -IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

<span data-ttu-id="c65e4-229">**ビデオ用に QoS を設定する**</span><span class="sxs-lookup"><span data-stu-id="c65e4-229">**Set QoS for video**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020 -IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

<span data-ttu-id="c65e4-230">**共有用に QoS を設定する**</span><span class="sxs-lookup"><span data-stu-id="c65e4-230">**Set QoS for sharing**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040 -IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a><span data-ttu-id="c65e4-231">Teams 管理センターで送信元ポートを管理する</span><span class="sxs-lookup"><span data-stu-id="c65e4-231">Managing source ports in the Teams admin center</span></span>

<span data-ttu-id="c65e4-232">Teams では、さまざまなワークロードで使用される QoS の送信元ポートをアクティブに管理し、必要に応じて調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-232">In Teams, QoS source ports used by the different workloads should be actively managed, and adjusted as necessary.</span></span> <span data-ttu-id="c65e4-233">「[各メディアの種類用の初期ポート範囲を選択する](#choose-initial-port-ranges-for-each-media-type)」の表に記されているように、ポート範囲は調整できますが、DSCP マーキングを構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="c65e4-233">Referring to the table in [Choose initial port ranges for each media type](#choose-initial-port-ranges-for-each-media-type), the port ranges are adjustable, but the DSCP markings aren't configurable.</span></span> <span data-ttu-id="c65e4-234">これらの設定を実装した後で、特定のメディアの種類に必要なポート数が現状よりも多い (または、少ない) ことが判明する場合があります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-234">Once you have implemented these settings, you might find that more or fewer ports are needed for a given media type.</span></span> <span data-ttu-id="c65e4-235">Teams の実装後、[ユーザーごとの通話分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)と[通話品質ダッシュボード (CQD)](turning-on-and-using-call-quality-dashboard.md)を使用して、ポート範囲の調整を決定し、ニーズの変化に応じて定期的に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-235">[Per-user call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md) and [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) should be used in making a decision to adjust port ranges after Teams has been implemented, and periodically as needs change.</span></span>

> [!NOTE]
> <span data-ttu-id="c65e4-236">Skype for Business Online 用の送信元ポート範囲と DSCP マーキングに基づいて QoS を既に構成済みの場合には、同じ構成が Teams に適用され、マッピングに対するクライアントやネットワークの変更は必要ありません。ただし、Skype for Business Online で構成された内容と一致させるために、[Teams で使用する範囲を設定](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-236">If you've already configured QoS based on source port ranges and DSCP markings for Skype for Business Online, the same configuration will apply to Teams and no further client or network changes to the mapping will be required, though you may have to [set the ranges used in Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) to match what was configured for Skype for Business Online.</span></span>

<span data-ttu-id="c65e4-237">以前にオンプレミスの Skype for Business Server を展開したことがある場合は、QoS ポリシーを再調査しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-237">If you’ve previously deployed Skype for Business Server on-premises, you might need to re-examine your QoS policies.</span></span> <span data-ttu-id="c65e4-238">確認したポート範囲の設定に一致するようにポリシーを調整して、Teams に質の高いユーザー エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c65e4-238">Adjust the policies to match port range settings you've verified provide a quality user experience for Teams.</span></span>

## <a name="validate-your-qos-implementation"></a><span data-ttu-id="c65e4-239">QoS の実装を検証する</span><span class="sxs-lookup"><span data-stu-id="c65e4-239">Validate your QoS implementation</span></span>

<span data-ttu-id="c65e4-240">QoS を有効にするには、GPO によって設定された DSCP 値が、通話の両端に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65e4-240">For QoS to be effective, the DSCP value set by the GPO needs to be present at both ends of a call.</span></span> <span data-ttu-id="c65e4-241">Teams クライアントによって生成されたトラフィックを分析することで、Teams のワークロード トラフィックがネットワーク内を移動するときに、DSCP 値が変更、または削除されていないことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-241">By analyzing the traffic generated by the Teams client, you can verify that the DSCP value isn’t changed or stripped out when the Teams workload traffic moves through the network.</span></span>

<span data-ttu-id="c65e4-242">可能であれば、ネットワークの出口ポイントでトラフィックをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="c65e4-242">Preferably, you capture traffic at the network egress point.</span></span> <span data-ttu-id="c65e4-243">スイッチやルーターでポート ミラーリングを使用して、この問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="c65e4-243">You can use port mirroring on a switch or router to help with this.</span></span>

## <a name="implement-qos-for-other-devices"></a><span data-ttu-id="c65e4-244">他のデバイスに QoS を実装する</span><span class="sxs-lookup"><span data-stu-id="c65e4-244">Implement QoS for other devices</span></span>

<span data-ttu-id="c65e4-245">Intune、Surface、iOS、Android、Mac の QoS の実装については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c65e4-245">Read these topics for information about implementing QoS for Intune, Surface, iOS, Android, and Mac</span></span>

- [<span data-ttu-id="c65e4-246">Surface Hub 2S の QoS</span><span class="sxs-lookup"><span data-stu-id="c65e4-246">QoS for Surface Hub 2S</span></span>](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)

- [<span data-ttu-id="c65e4-247">Surface Hub の QoS</span><span class="sxs-lookup"><span data-stu-id="c65e4-247">QoS for Surface Hub</span></span>](https://docs.microsoft.com/surface-hub/surface-hub-qos)

- [<span data-ttu-id="c65e4-248">iOS、Android、Mac の QoS</span><span class="sxs-lookup"><span data-stu-id="c65e4-248">QoS for iOS, Android, and Mac</span></span>](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a><span data-ttu-id="c65e4-249">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c65e4-249">Related topics</span></span>

- [<span data-ttu-id="c65e4-250">ビデオ: ネットワークの計画</span><span class="sxs-lookup"><span data-stu-id="c65e4-250">Video: Network Planning</span></span>](https://aka.ms/teams-networking)

- [<span data-ttu-id="c65e4-251">Microsoft Teams 用に組織のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="c65e4-251">Prepare your organization's network for Microsoft Teams</span></span>](prepare-network.md)

- [<span data-ttu-id="c65e4-252">Teams クライアント に QoS を実装する</span><span class="sxs-lookup"><span data-stu-id="c65e4-252">Implement QoS in the Teams client</span></span>](QoS-in-Teams-clients.md)
