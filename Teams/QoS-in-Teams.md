---
title: Microsoft Teams でサービスの品質 (QoS) を実施する
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Microsoft Teams でサービスの品質 (QoS) のために組織のネットワークを準備する方法について説明します。
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
ms.openlocfilehash: 52b1d03be3e5d54260084bbf44ad6695404607c9
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766580"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a><span data-ttu-id="d07ed-103">Microsoft Teams でサービスの品質 (QoS) を実装する</span><span class="sxs-lookup"><span data-stu-id="d07ed-103">Implement Quality of Service (QoS) in Microsoft Teams</span></span>

<span data-ttu-id="d07ed-104">Microsoft Teams の QoS (Quality of Service) では、ネットワークの遅延 (音声やビデオのストリームなど) に影響を受けているリアルタイムのネットワークトラフィックが、機密性の低いトラフィック (たとえば、新しいアプリをダウンロードしても、追加のもう1つ目のダウンロードは大きなものではありません) になります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-104">Quality of Service (QoS) in Microsoft Teams allows real-time network traffic that's sensitive to network delays (for example, voice or video streams) to "cut in line" in front of traffic that's less sensitive (like downloading a new app, where an extra second to download isn't a large deal).</span></span> <span data-ttu-id="d07ed-105">QoS では、Windows のグループポリシーオブジェクトとポートベースのアクセス制御リストを使用して、リアルタイムストリーム内のすべてのパケットを特定してマークします。</span><span class="sxs-lookup"><span data-stu-id="d07ed-105">QoS uses Windows Group Policy Objects and Port-based Access Control Lists to identify and mark all packets in real-time streams.</span></span> <span data-ttu-id="d07ed-106">これにより、ネットワークがネットワーク帯域幅の専用部分を使って、音声、ビデオ、画面共有を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-106">This helps your network to give voice, video, and screen share streams a dedicated portion of network bandwidth.</span></span>

<span data-ttu-id="d07ed-107">この記事で説明されているいずれかの問題が発生している大規模なユーザーをサポートしている場合は、おそらく QoS を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-107">If you support a large group of users who are experiencing any of the problems described in this article, then you probably need to implement QoS.</span></span> <span data-ttu-id="d07ed-108">ユーザー数の少ない小規模企業は、QoS を必要としない場合もありますが、役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-108">A small business with few users might not need QoS, but even there it should be helpful.</span></span>

<span data-ttu-id="d07ed-109">QoS の形式がないと、音声とビデオで次の品質の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-109">Without some form of QoS, you might see the following quality issues in voice and video:</span></span>

- <span data-ttu-id="d07ed-110">ジッター–さまざまな料金で受信するメディアパケット。通話に単語または音節が含まれていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-110">Jitter – media packets arriving at different rates, which can result in missing words or syllables in calls</span></span>
- <span data-ttu-id="d07ed-111">パケット損失–パケットが破棄されると、音声品質が低下し、音声認識が困難になることもあります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-111">Packet loss – packets dropped, which can also result in lower voice quality and hard to understand speech</span></span>
- <span data-ttu-id="d07ed-112">遅延したラウンドトリップ時間 (RTT) –メディアパケットが相手に届くまでに時間がかかります。これにより、会話中に2つの当事者間で顕著な遅延が発生し、ユーザーが互いに連絡を取り合うようになります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-112">Delayed round-trip time (RTT) – media packets taking a long time to reach their destinations, which result in noticeable delays between two parties in a conversation and causes people to talk over each other</span></span>

<span data-ttu-id="d07ed-113">これらの問題に対処するための最も複雑な方法は、内部とインターネットの両方でデータ接続のサイズを大きくすることです。</span><span class="sxs-lookup"><span data-stu-id="d07ed-113">The least complex way to address these issues is to increase the size of the data connections, both internally and out to the internet.</span></span> <span data-ttu-id="d07ed-114">多くの場合、費用がかかる場合があるため、QoS は帯域幅を追加する代わりに、使用しているリソースをより効果的に管理する手段となります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-114">Since that is often cost-prohibitive, QoS provides a way to more effectively manage the resources you have instead of adding bandwidth.</span></span> <span data-ttu-id="d07ed-115">品質の問題を解決するには、最初に QoS を使用し、必要に応じて帯域幅のみを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d07ed-115">To address quality issues, we recommend that you first use QoS, then add bandwidth only where necessary.</span></span>

<span data-ttu-id="d07ed-116">QoS を有効にするには、組織全体で一貫した QoS 設定を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-116">For QoS to be effective, you must apply consistent QoS settings throughout your organization.</span></span> <span data-ttu-id="d07ed-117">QoS の優先順位をサポートしていないパスの部分は、通話、ビデオ、画面共有の品質を低下させる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-117">Any part of the path that fails to support your QoS priorities can degrade the quality of calls, video, and screen sharing.</span></span> <span data-ttu-id="d07ed-118">これには、すべてのユーザーの Pc またはデバイス、ネットワークスイッチ、インターネットへのルーター、および Teams サービスへの設定の適用が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-118">This includes applying settings to all user PCs or devices, network switches, routers to the internet, and the Teams service.</span></span>

<span data-ttu-id="d07ed-119">_図1組織のネットワークと Microsoft 365 または Office 365 サービスの間の関係_</span><span class="sxs-lookup"><span data-stu-id="d07ed-119">_Figure 1. The relationship between an organization's networks and Microsoft 365 or Office 365 services_</span></span>

<span data-ttu-id="d07ed-120">![ネットワークとサービス間の関係を示す図](media/Qos-in-Teams-Image1.png "組織のネットワークと Microsoft 365 または Office 365 サービスの間の関係: オンプレミスのネットワークとデバイスは、相互接続ネットワークに接続されます。これは、Microsoft 365 または Office 365 クラウドの音声と電話会議サービスに接続します。")</span><span class="sxs-lookup"><span data-stu-id="d07ed-120">![Illustration of the relationship between networks and services](media/Qos-in-Teams-Image1.png "The relationship between an organization's networks and Microsoft 365 or Office 365 services: on-premises network and devices connect with an interconnect network, which in turn connects with Microsoft 365 or Office 365 Cloud Voice and Audio Conferencing services.")</span></span>

## <a name="qos-implementation-checklist"></a><span data-ttu-id="d07ed-121">QoS の実装のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="d07ed-121">QoS implementation checklist</span></span>

<span data-ttu-id="d07ed-122">高レベルでは、次の操作を実行して QoS を実装します。</span><span class="sxs-lookup"><span data-stu-id="d07ed-122">At a high level, do the following to implement QoS:</span></span>

1. [<span data-ttu-id="d07ed-123">ネットワークの準備ができていることを確認する</span><span class="sxs-lookup"><span data-stu-id="d07ed-123">Make sure your network is ready</span></span>](#make-sure-your-network-is-ready)

1. [<span data-ttu-id="d07ed-124">QoS の実装方法を選択する</span><span class="sxs-lookup"><span data-stu-id="d07ed-124">Select a QoS implementation method</span></span>](#select-a-qos-implementation-method)

1. [<span data-ttu-id="d07ed-125">各メディアの種類の初期ポート範囲を選ぶ</span><span class="sxs-lookup"><span data-stu-id="d07ed-125">Choose initial port ranges for each media type</span></span>](#choose-initial-port-ranges-for-each-media-type)

1. <span data-ttu-id="d07ed-126">QoS 設定を実装します。</span><span class="sxs-lookup"><span data-stu-id="d07ed-126">Implement QoS settings:</span></span>
   1. <span data-ttu-id="d07ed-127">グループポリシーオブジェクト (GPO) を使用するクライアントで、[クライアントデバイスのポート範囲とマークを設定](QoS-in-Teams-clients.md)する</span><span class="sxs-lookup"><span data-stu-id="d07ed-127">On clients using a Group Policy Object (GPO) to [set client device port ranges and markings](QoS-in-Teams-clients.md)</span></span>
   2. <span data-ttu-id="d07ed-128">ルーター (製造元のマニュアルを参照)、または他のネットワークデバイスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d07ed-128">On routers (see the manufacturer documentation) or other network devices.</span></span> <span data-ttu-id="d07ed-129">これには、ポートベースのアクセス制御リスト (Acl) が含まれていることもあれば、QoS キューと DSCP マーキングのいずれかを定義することもあります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-129">This might include port-based Access Control Lists (ACLs) or simply defining the QoS queues and DSCP markings, or all of these.</span></span>

      > [!IMPORTANT]
      > <span data-ttu-id="d07ed-130">これらの QoS ポリシーは、クライアントソースポートと、発信元と送信先の IP アドレスを "any" として実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d07ed-130">We recommend implementing these QoS policies using the client source ports and a source and destination IP address of “any.”</span></span> <span data-ttu-id="d07ed-131">これにより、内部ネットワーク上の受信および送信メディアの両方のトラフィックがキャッチされます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-131">This will catch both incoming and outgoing media traffic on the internal network.</span></span>  

   3. [<span data-ttu-id="d07ed-132">Teams 会議でメディアトラフィックを処理する方法を設定する</span><span class="sxs-lookup"><span data-stu-id="d07ed-132">Set how you want to handle media traffic for Teams meetings</span></span>](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. <span data-ttu-id="d07ed-133">ネットワーク上のチームトラフィックを分析して、 [QoS の実装を検証](#validate-your-qos-implementation)します。</span><span class="sxs-lookup"><span data-stu-id="d07ed-133">[Validate your QoS implementation](#validate-your-qos-implementation) by analyzing Teams traffic on the network.</span></span>

<span data-ttu-id="d07ed-134">QoS を実装する準備ができたら、次のガイドラインを念頭に置いてください。</span><span class="sxs-lookup"><span data-stu-id="d07ed-134">As you prepare to implement QoS, keep the following guidelines in mind:</span></span>

- <span data-ttu-id="d07ed-135">Microsoft 365 への最短パス</span><span class="sxs-lookup"><span data-stu-id="d07ed-135">The shortest path to Microsoft 365 is best</span></span>
- <span data-ttu-id="d07ed-136">ポートを閉じると音質が低下する</span><span class="sxs-lookup"><span data-stu-id="d07ed-136">Closing ports will only lead to quality degradation</span></span>
- <span data-ttu-id="d07ed-137">プロキシなどの障害物はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="d07ed-137">Any obstacles in between, such as proxies, aren't recommended</span></span>
- <span data-ttu-id="d07ed-138">ホップ数を制限します。</span><span class="sxs-lookup"><span data-stu-id="d07ed-138">Limit the number of hops:</span></span>
  - <span data-ttu-id="d07ed-139">クライアントからネットワークエッジへ-3 ~ 5 ホップ</span><span class="sxs-lookup"><span data-stu-id="d07ed-139">Client to network edge – 3 to 5 hops</span></span>
  - <span data-ttu-id="d07ed-140">ISP から Microsoft ネットワークエッジ–3ホップ</span><span class="sxs-lookup"><span data-stu-id="d07ed-140">ISP to Microsoft network edge – 3 hops</span></span>
  - <span data-ttu-id="d07ed-141">Microsoft ネットワークエッジから最終的な送信先への関連性がない</span><span class="sxs-lookup"><span data-stu-id="d07ed-141">Microsoft network edge to final destination – irrelevant</span></span>

<span data-ttu-id="d07ed-142">ファイアウォールのポートを構成する方法については、「 [Office 365 の URL と IP 範囲](office-365-urls-ip-address-ranges.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d07ed-142">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

## <a name="make-sure-your-network-is-ready"></a><span data-ttu-id="d07ed-143">ネットワークの準備ができていることを確認する</span><span class="sxs-lookup"><span data-stu-id="d07ed-143">Make sure your network is ready</span></span>

<span data-ttu-id="d07ed-144">QoS の実装を検討している場合は、帯域幅要件とその他の [ネットワーク要件](prepare-network.md)を既に決定しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-144">If you're considering a QoS implementation, you should already have determined your bandwidth requirements and other [network requirements](prepare-network.md).</span></span>
  
<span data-ttu-id="d07ed-145">ネットワーク全体でのトラフィック渋滞は、メディアの品質に大きく影響します。</span><span class="sxs-lookup"><span data-stu-id="d07ed-145">Traffic congestion across a network will greatly impact media quality.</span></span> <span data-ttu-id="d07ed-146">帯域幅の不足は、パフォーマンスの低下を招き、ユーザーエクスペリエンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="d07ed-146">A lack of bandwidth leads to performance degradation and a poor user experience.</span></span> <span data-ttu-id="d07ed-147">Teams の導入と使用量が増加するにつれて、レポート作成、 [ユーザーごとの通話分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)、 [通話品質ダッシュボード (CQD)](turning-on-and-using-call-quality-dashboard.md) を使用して問題を特定し、QoS と選択的な帯域幅の追加機能を使って調整を行います。</span><span class="sxs-lookup"><span data-stu-id="d07ed-147">As Teams adoption and usage grows, use reporting, [per-user call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md), and [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to identify problems and then make adjustments using QoS and selective bandwidth additions.</span></span>

### <a name="vpn-considerations"></a><span data-ttu-id="d07ed-148">VPN に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="d07ed-148">VPN considerations</span></span>

<span data-ttu-id="d07ed-149">QoS は、呼び出し元間のすべてのリンクに実装されている場合にのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="d07ed-149">QoS only works as expected when implemented on all links between callers.</span></span> <span data-ttu-id="d07ed-150">内部ネットワークで QoS を使用していて、ユーザーが遠隔地からサインインしている場合は、内部の管理されたネットワーク内でのみ優先順位を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-150">If you use QoS on an internal network and a user signs in from a remote location, you can only prioritize within your internal, managed network.</span></span> <span data-ttu-id="d07ed-151">リモートの場所は仮想プライベートネットワーク (VPN) を実装することによって管理された接続を受け取ることができますが、VPN の本質的にはパケットのオーバーヘッドが追加され、リアルタイムトラフィックで遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="d07ed-151">Although remote locations can receive a managed connection by implementing a virtual private network (VPN),  a VPN inherently adds packet overhead and creates delays in real-time traffic.</span></span> <span data-ttu-id="d07ed-152">VPN 経由のリアルタイム通信トラフィックを実行しないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d07ed-152">We  recommend that you avoid running real-time communications traffic over a VPN.</span></span>

<span data-ttu-id="d07ed-153">世界中の管理されたリンクを含むグローバル組織では、これらのリンクの帯域幅が LAN と比較して制限されているため、QoS を強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d07ed-153">In a global organization with managed links that span continents, we strongly recommend QoS because bandwidth for those links is limited in comparison to the LAN.</span></span>

## <a name="introduction-to-qos-queues"></a><span data-ttu-id="d07ed-154">QoS キューの概要</span><span class="sxs-lookup"><span data-stu-id="d07ed-154">Introduction to QoS queues</span></span>

<span data-ttu-id="d07ed-155">QoS を提供するには、ネットワークデバイスがトラフィックを分類するための手段を持っている必要があります。また、音声やビデオを他のネットワークトラフィックと区別できなければなりません。</span><span class="sxs-lookup"><span data-stu-id="d07ed-155">To provide QoS, network devices must have a way to classify traffic and must be able to distinguish voice or video from other network traffic.</span></span>

<span data-ttu-id="d07ed-156">ネットワークトラフィックがルーターに入ったら、トラフィックはキューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-156">When network traffic enters a router, the traffic is placed into a queue.</span></span> <span data-ttu-id="d07ed-157">QoS ポリシーが構成されていない場合は、1つのキューしかありません。すべてのデータは、同じ優先度で最初のデータとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-157">If a QoS policy isn't configured, there is only one queue, and all data is treated as first-in, first-out with the same priority.</span></span> <span data-ttu-id="d07ed-158">つまり、ボイストラフィック (遅延に非常に敏感) は、わずか数秒の遅延が問題となるトラフィックが遅れている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-158">That means voice traffic (which is very sensitive to delays) might get stuck behind traffic where a delay of a few extra milliseconds wouldn't be a problem.</span></span>

<span data-ttu-id="d07ed-159">QoS を実装する場合、複数のキューを定義するには、Cisco の優先度キューや [クラスベースの加重公平なキュー (cbの](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) 場合) や輻輳回避機能 ( [wred)](https://en.wikipedia.org/wiki/Weighted_random_early_detection)などの輻輳回避機能のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="d07ed-159">When you implement QoS, you define multiple queues using one of several congestion management features, such as Cisco’s priority queuing and [Class-Based Weighted Fair Queueing (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) and congestion avoidance features, such as [weighted random early detection (WRED)](https://en.wikipedia.org/wiki/Weighted_random_early_detection).</span></span>

<span data-ttu-id="d07ed-160">_図2QoS キューの例_</span><span class="sxs-lookup"><span data-stu-id="d07ed-160">_Figure 2. Examples of QoS queues_</span></span>

<span data-ttu-id="d07ed-161">![QoS キューと帯域幅区分の図](media/Qos-in-Teams-Image2.png "利用可能な帯域幅の合計は、複数のキュー (オーディオ、ビデオ、その他のトラフィック) で分割されます。これには、さまざまな優先順位が割り当てられています。")</span><span class="sxs-lookup"><span data-stu-id="d07ed-161">![Illustration of QoS queues and bandwidth division](media/Qos-in-Teams-Image2.png "Total available bandwidth is divided among multiple queues—audio, video, and other traffic—that have been assigned different priorities.")</span></span>

<span data-ttu-id="d07ed-162">簡単な例としては、QoS によってデータネットワーク内に仮想 "相乗りレーン" が作成されるため、データの種類によっては遅延が発生しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-162">A simple analogy is that QoS creates virtual "carpool lanes" in your data network so some types of data never or rarely encounter a delay.</span></span> <span data-ttu-id="d07ed-163">これらのレーンを作成した後は、組織のユーザーに対してビジネスレベルのエクスペリエンスを提供しながら、相対的なサイズを調整して、より効率的に接続の帯域幅を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-163">Once you create those lanes, you can adjust their relative size and much more effectively manage the connection bandwidth you have, while still delivering business-grade experiences for your organization's users.</span></span>

## <a name="select-a-qos-implementation-method"></a><span data-ttu-id="d07ed-164">QoS の実装方法を選択する</span><span class="sxs-lookup"><span data-stu-id="d07ed-164">Select a QoS implementation method</span></span>

<span data-ttu-id="d07ed-165">ネットワークのルーターでアクセス制御リスト (Acl) を使用して、ポートベースのタグを使って QoS を実装することができます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-165">You could implement QoS via port-based tagging, using Access Control Lists (ACLs) on your network's routers.</span></span> <span data-ttu-id="d07ed-166">ポートベースのタグ付けは、Windows、Mac、および Linux の混合環境で動作するため、最も信頼できる方法です。</span><span class="sxs-lookup"><span data-stu-id="d07ed-166">Port-based tagging is the most reliable method because it works in mixed Windows, Mac, and Linux environments and is the easiest to implement.</span></span> <span data-ttu-id="d07ed-167">モバイルクライアントでは、DSCP 値を使ってトラフィックをマークするメカニズムは用意されていないため、このメソッドが必要になります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-167">Mobile clients don't provide a mechanism to mark traffic by using DSCP values, so they'll require this method.</span></span>  

<span data-ttu-id="d07ed-168">ポートベースのタグ付けを使用すると、ネットワークのルーターは受信パケットを調べます。また、特定のポートまたはポートの範囲を使ってパケットが着信した場合は、特定のメディアの種類として識別[DSCP](https://tools.ietf.org/html/rfc2474)し、それをその種類のキューに入れて、他のデバイスがそのトラフィックの種類を認識してキューの優先順位を上げる</span><span class="sxs-lookup"><span data-stu-id="d07ed-168">Using port-based tagging, your network's router examines an incoming packet, and if the packet arrived using a certain port or range of ports, it identifies it as a certain media type and puts it in the queue for that type, adding a predetermined [DSCP](https://tools.ietf.org/html/rfc2474) mark to the IP Packet header so other devices can recognize its traffic type and give it priority in their queue.</span></span>

<span data-ttu-id="d07ed-169">ポートベースのタグ付けはプラットフォーム間で動作しますが、WAN edge でトラフィックをマークするだけで、管理のオーバーヘッドが生じます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-169">Although port-based tagging works across platforms, it only marks traffic at the WAN edge (not all the way to the client machine) and creates management overhead.</span></span> <span data-ttu-id="d07ed-170">この方法を実装する手順については、ルーター製造元から提供されているドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d07ed-170">Refer to the documentation provided by the router manufacturer for instructions on implementing this method.</span></span>

### <a name="insert-dscp-markers"></a><span data-ttu-id="d07ed-171">DSCP マーカーを挿入する</span><span class="sxs-lookup"><span data-stu-id="d07ed-171">Insert DSCP markers</span></span>

<span data-ttu-id="d07ed-172">また、グループポリシーオブジェクト (GPO) を使ってクライアントデバイスが、特定の種類のトラフィック (ボイスなど) であることを示す DSCP マーカーを IP パケットヘッダーに挿入することで、QoS を実装することもできます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-172">You could also implement QoS by using a Group Policy Object (GPO) to direct client devices to insert a DSCP marker in IP packet headers identifying it as particular type of traffic (for example, voice).</span></span> <span data-ttu-id="d07ed-173">ルーターなどのネットワークデバイスでは、これを認識して、トラフィックを個別の優先度の高いキューに配置するように構成することができます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-173">Routers and other network devices can be configured to recognize this and put the traffic in a separate, higher-priority queue.</span></span>

<span data-ttu-id="d07ed-174">このシナリオは完全に有効ですが、ドメインに参加している Windows クライアントに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="d07ed-174">Although this scenario is entirely valid, it will only work for domain-joined Windows clients.</span></span> <span data-ttu-id="d07ed-175">ドメインに参加していないデバイスでは、DSCP タグ付けは有効になりません。</span><span class="sxs-lookup"><span data-stu-id="d07ed-175">Any device that isn't a domain-joined Windows client won't be enabled for DSCP tagging.</span></span> <span data-ttu-id="d07ed-176">Mac OS などのクライアントでは、ハードコーディングされたタグがあり、常にトラフィックがタグ付けされます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-176">Clients such as Mac OS have hard-coded tags and will always tag traffic.</span></span>

<span data-ttu-id="d07ed-177">正側では、GPO を使用して DSCP マーキングを制御することで、ドメインに参加しているすべてのコンピューターが同じ設定を受け取り、管理者だけがそれらを管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-177">On the plus side, controlling the DSCP marking via GPO ensures that all domain-joined computers receive the same settings and that only an administrator can manage them.</span></span> <span data-ttu-id="d07ed-178">GPO を使うことができるクライアントは、元のデバイスでタグ付けされ、設定されたネットワークデバイスでは、DSCP コードによってリアルタイムストリームを認識し、適切な優先順位を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-178">Clients that can use GPO will be tagged on the originating device, and then configured network devices can recognize the real-time stream by the DSCP code and give it an appropriate priority.</span></span>

### <a name="best-practice"></a><span data-ttu-id="d07ed-179">ベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="d07ed-179">Best practice</span></span>

<span data-ttu-id="d07ed-180">可能であれば、エンドポイントとポートベースの Acl での DSCP マーキングをルーターで組み合わせることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d07ed-180">We recommend a combination of DSCP markings at the endpoint and port-based ACLs on routers, if possible.</span></span> <span data-ttu-id="d07ed-181">GPO を使用してほとんどのクライアントをキャッチし、さらにポートベースの DSCP タグを使用することで、モバイル、Mac、およびその他のクライアントでも QoS 処理を行うことができます (少なくとも一部)。</span><span class="sxs-lookup"><span data-stu-id="d07ed-181">Using a GPO to catch the majority of clients, and also using port-based DSCP tagging will ensure that mobile, Mac, and other clients will still get QoS treatment (at least partially).</span></span>

<span data-ttu-id="d07ed-182">[DSCP マーキング] は、likened が配信されるまでの時間と、迅速な配信のために最適な並べ替えを行うことができるようにする郵送の頻度を示す切手にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-182">DSCP markings can be likened to postage stamps that indicate to postal workers how urgent the delivery is and how best to sort it for speedy delivery.</span></span> <span data-ttu-id="d07ed-183">リアルタイムメディアストリームに優先順位を設定するようにネットワークを構成すると、紛失したパケットや遅延したパケットが大幅に減少します。</span><span class="sxs-lookup"><span data-stu-id="d07ed-183">Once you've configured your network to give priority to real-time media streams, lost packets and late packets should diminish greatly.</span></span>

<span data-ttu-id="d07ed-184">ネットワーク内のすべてのデバイスが同じ分類、マーキング、優先順位を使用している場合は、各トラフィックの種類で使用されるキューに割り当てられているポート範囲のサイズを変更することによって、遅延、破棄されたパケット、ジッタを削減または除去することができます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-184">Once all devices in the network are using the same classifications, markings, and priorities, it's possible to reduce or eliminate delays, dropped packets, and jitter by changing the size of the port ranges assigned to the queues used for each traffic type.</span></span> <span data-ttu-id="d07ed-185">Teams の観点から見ると、最も重要な構成手順は、パケットを分類してマークすることです。</span><span class="sxs-lookup"><span data-stu-id="d07ed-185">From the Teams perspective, the most important configuration step is the classification and marking of packets.</span></span> <span data-ttu-id="d07ed-186">ただし、エンドツーエンドの QoS を成功させるには、基になるネットワーク構成にアプリケーションの構成を慎重に合わせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-186">However, for end-to-end QoS to be successful, you also need to carefully align the application's configuration with the underlying network configuration.</span></span> <span data-ttu-id="d07ed-187">QoS が完全に実装されたら、継続的な管理は、組織のニーズと実際の使用状況に基づいて、各トラフィックの種類に割り当てられたポート範囲を調整することになります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-187">Once QoS is fully implemented, ongoing management is a question of adjusting the port ranges assigned to each traffic type based on your organization's needs and actual usage.</span></span>

## <a name="choose-initial-port-ranges-for-each-media-type"></a><span data-ttu-id="d07ed-188">各メディアの種類の初期ポート範囲を選ぶ</span><span class="sxs-lookup"><span data-stu-id="d07ed-188">Choose initial port ranges for each media type</span></span>

<span data-ttu-id="d07ed-189">DSCP 値は、対応して構成されたネットワークに、パケットまたはストリームを割り当てるための優先順位を示します。 DSCP マークがクライアントとネットワーク自体のどちらで割り当てられているかは、ACL 設定に基づいて判断されます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-189">The DSCP value tells a correspondingly configured network what priority to give a packet or stream, whether the DSCP mark is assigned by clients or the network itself based on ACL settings.</span></span> <span data-ttu-id="d07ed-190">メディアの各ワークロードには、独自の固有の DSCP 値が与えられます (他のサービスによっては、ワークロードで DSCP マーキング、チームにはない)、および各メディアの種類に対して定義され、個別のポート範囲を共有できます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-190">Each media workload gets its own unique DSCP value (other services might allow workloads to share a DSCP marking, Teams doesn't) and a defined and separate port range used for each media type.</span></span> <span data-ttu-id="d07ed-191">その他の環境には既存の QoS 戦略がある場合があります。これは、ネットワークワークロードの優先順位を決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-191">Other environments might have an existing QoS strategy in place, which will help you determine the priority of network workloads.</span></span>

<span data-ttu-id="d07ed-192">さまざまなリアルタイムストリーミングワークロードのポート範囲の相対サイズによって、そのワークロード専用の使用可能な帯域幅の合計の比率が設定されます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-192">The relative size of the port ranges for different real-time streaming workloads sets the proportion of the total available bandwidth dedicated to that workload.</span></span> <span data-ttu-id="d07ed-193">以前のお客様に戻るには、"Air Mail" スタンプ付きの文字が、最も近い空港から1時間以内に実行されることがあります。また、"一括メール" マークとマークされた小さいパッケージでは、1日のうち、一連のトラックで陸を通過するまで待機することができます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-193">To return to our earlier postal analogy: a letter with an "Air Mail" stamp might get taken within an hour to the nearest airport, while a small package marked "Bulk Mail" mark can wait for a day before traveling over land on a series of trucks.</span></span>

<span data-ttu-id="d07ed-194">_推奨される初期ポート範囲_</span><span class="sxs-lookup"><span data-stu-id="d07ed-194">_Recommended initial port ranges_</span></span>

|<span data-ttu-id="d07ed-195">メディア トラフィックの種類</span><span class="sxs-lookup"><span data-stu-id="d07ed-195">Media traffic type</span></span>| <span data-ttu-id="d07ed-196">クライアントのソース ポートの範囲</span><span class="sxs-lookup"><span data-stu-id="d07ed-196">Client source port range</span></span> |<span data-ttu-id="d07ed-197">プロトコル</span><span class="sxs-lookup"><span data-stu-id="d07ed-197">Protocol</span></span>|<span data-ttu-id="d07ed-198">DSCP 値</span><span class="sxs-lookup"><span data-stu-id="d07ed-198">DSCP value</span></span>|<span data-ttu-id="d07ed-199">DSCP クラス</span><span class="sxs-lookup"><span data-stu-id="d07ed-199">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="d07ed-200">オーディオ</span><span class="sxs-lookup"><span data-stu-id="d07ed-200">Audio</span></span>| <span data-ttu-id="d07ed-201">50,000–50,019</span><span class="sxs-lookup"><span data-stu-id="d07ed-201">50,000–50,019</span></span>|<span data-ttu-id="d07ed-202">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="d07ed-202">TCP/UDP</span></span>|<span data-ttu-id="d07ed-203">46</span><span class="sxs-lookup"><span data-stu-id="d07ed-203">46</span></span>|<span data-ttu-id="d07ed-204">完全優先転送 (EF)</span><span class="sxs-lookup"><span data-stu-id="d07ed-204">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="d07ed-205">ビデオ</span><span class="sxs-lookup"><span data-stu-id="d07ed-205">Video</span></span>| <span data-ttu-id="d07ed-206">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="d07ed-206">50,020–50,039</span></span>|<span data-ttu-id="d07ed-207">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="d07ed-207">TCP/UDP</span></span>|<span data-ttu-id="d07ed-208">34</span><span class="sxs-lookup"><span data-stu-id="d07ed-208">34</span></span>|<span data-ttu-id="d07ed-209">相対的優先転送 (AF41)</span><span class="sxs-lookup"><span data-stu-id="d07ed-209">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="d07ed-210">アプリケーション/画面共有</span><span class="sxs-lookup"><span data-stu-id="d07ed-210">Application/Screen Sharing</span></span>| <span data-ttu-id="d07ed-211">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="d07ed-211">50,040–50,059</span></span>|<span data-ttu-id="d07ed-212">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="d07ed-212">TCP/UDP</span></span>|<span data-ttu-id="d07ed-213">才</span><span class="sxs-lookup"><span data-stu-id="d07ed-213">18</span></span>|<span data-ttu-id="d07ed-214">相対的優先転送 (AF21)</span><span class="sxs-lookup"><span data-stu-id="d07ed-214">Assured Forwarding (AF21)</span></span>|
||||||

<span data-ttu-id="d07ed-215">これらの設定を使用する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="d07ed-215">Be aware of the following when you use these settings:</span></span>

- <span data-ttu-id="d07ed-216">今後、ExpressRoute の実装を計画していて、QoS を実装していない場合は、このガイダンスに従うことをお勧めします。これにより、DSCP 値が送信者と受信者と同じになるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d07ed-216">If you plan to implement ExpressRoute in the future and haven't yet implemented QoS, we recommend that you follow the guidance so that DSCP values are the same from sender to receiver.</span></span>
- <span data-ttu-id="d07ed-217">モバイルクライアントやチームデバイスを含むすべてのクライアントは、これらのポート範囲を使用します。また、これらのソースポート範囲を使用する、実装するすべての DSCP ポリシーが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-217">All clients, including mobile clients and Teams devices, will use these port ranges and will be affected by any DSCP policy you implement that uses these source port ranges.</span></span> <span data-ttu-id="d07ed-218">動的なポートを引き続き使用するクライアントは、ブラウザーベースのクライアント (つまり、参加者がブラウザーを使って会議に参加できるクライアント) だけです。</span><span class="sxs-lookup"><span data-stu-id="d07ed-218">The only clients that will continue to use dynamic ports are the browser-based clients (clients that let participants join meetings by using their browsers).</span></span>
- <span data-ttu-id="d07ed-219">Mac クライアントでは、同じポート範囲を使用しますが、オーディオ (EF) とビデオ (AF41) にはハードコーディングされた値も使用されます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-219">Although the Mac client uses the same port ranges, it also uses hard-coded values for audio (EF) and video (AF41).</span></span> <span data-ttu-id="d07ed-220">これらの値は構成できません。</span><span class="sxs-lookup"><span data-stu-id="d07ed-220">These values aren't configurable.</span></span>
- <span data-ttu-id="d07ed-221">ユーザーエクスペリエンスを向上させるために、後でポート範囲を調整する必要がある場合は、ポート範囲を重ねる必要があり、互いに隣り合っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-221">If you later need to adjust the port ranges to improve user experience, the port ranges can't overlap and should be adjacent to each other.</span></span>

## <a name="migrate-qos-to-teams"></a><span data-ttu-id="d07ed-222">QoS を Teams に移行する</span><span class="sxs-lookup"><span data-stu-id="d07ed-222">Migrate QoS to Teams</span></span>

<span data-ttu-id="d07ed-223">以前に Skype for Business Online を展開したことがある場合 (QoS のタグ付けやポート範囲を含む)、展開されている場合。</span><span class="sxs-lookup"><span data-stu-id="d07ed-223">If you've previously deployed Skype for Business Online, including QoS tagging and port ranges, and are now deploying.</span></span> <span data-ttu-id="d07ed-224">Teams では、チームは既存の構成を尊重し、Skype for Business クライアントと同じポート範囲とタグ付けを使用します。</span><span class="sxs-lookup"><span data-stu-id="d07ed-224">Teams, Teams will respect the existing configuration and will use the same port ranges and tagging as the Skype for Business client.</span></span> <span data-ttu-id="d07ed-225">ほとんどの場合、追加の構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d07ed-225">In most cases, no additional configuration will be needed.</span></span>

> [!NOTE]
> <span data-ttu-id="d07ed-226">グループポリシーによってアプリケーション名の QoS タグ付けを使用している場合は、アプリケーション名として Teams.exe を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-226">If you're using Application Name QoS tagging via Group Policy, you must add Teams.exe as the application name.</span></span>

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a><span data-ttu-id="d07ed-227">PowerShell を使用して Windows 上のチームに QoS を実装する</span><span class="sxs-lookup"><span data-stu-id="d07ed-227">Implement QoS in Teams on Windows using PowerShell</span></span>

<span data-ttu-id="d07ed-228">**オーディオ用に QoS を設定する**</span><span class="sxs-lookup"><span data-stu-id="d07ed-228">**Set QoS for audio**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000
-IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

<span data-ttu-id="d07ed-229">**ビデオに QoS を設定する**</span><span class="sxs-lookup"><span data-stu-id="d07ed-229">**Set QoS for video**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020
-IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

<span data-ttu-id="d07ed-230">**共有用に QoS を設定する**</span><span class="sxs-lookup"><span data-stu-id="d07ed-230">**Set QoS for sharing**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040
-IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a><span data-ttu-id="d07ed-231">Teams 管理センターでソースポートを管理する</span><span class="sxs-lookup"><span data-stu-id="d07ed-231">Managing source ports in the Teams admin center</span></span>

<span data-ttu-id="d07ed-232">Teams では、さまざまなワークロードによって使用される QoS ソースポートを、必要に応じて動的に管理し、調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-232">In Teams, QoS source ports used by the different workloads should be actively managed, and adjusted as necessary.</span></span> <span data-ttu-id="d07ed-233">「 [各メディアの種類の初期ポート範囲を選択](#choose-initial-port-ranges-for-each-media-type)する」の表を参照すると、ポート範囲は調整できますが、DSCP マーキングは構成できません。</span><span class="sxs-lookup"><span data-stu-id="d07ed-233">Referring to the table in [Choose initial port ranges for each media type](#choose-initial-port-ranges-for-each-media-type), the port ranges are adjustable, but the DSCP markings aren't configurable.</span></span> <span data-ttu-id="d07ed-234">これらの設定を実装した後は、特定のメディアの種類に必要なポートの数が増加したり、少ない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-234">Once you have implemented these settings, you might find that more or fewer ports are needed for a given media type.</span></span> <span data-ttu-id="d07ed-235">[ユーザーごとの通話分析](use-call-analytics-to-troubleshoot-poor-call-quality.md) と [通話品質ダッシュボード (CQD)](turning-on-and-using-call-quality-dashboard.md) を使用して、Teams が実装された後、定期的に、必要に応じて、ポート範囲を調整することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d07ed-235">[Per-user call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md) and [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) should be used in making a decision to adjust port ranges after Teams has been implemented, and periodically as needs change.</span></span>

> [!NOTE]
> <span data-ttu-id="d07ed-236">Skype for Business Online のソースポート範囲と DSCP マーキングに基づいて既に QoS を構成している場合は、同じ構成が Teams に適用され、マッピングに対するクライアントやネットワークの変更は必要ありませんが、 [チームで使用する範囲を設定](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) して、Skype For business online 用に構成されたものと一致させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-236">If you've already configured QoS based on source port ranges and DSCP markings for Skype for Business Online, the same configuration will apply to Teams and no further client or network changes to the mapping will be required, though you may have to [set the ranges used in Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) to match what was configured for Skype for Business Online.</span></span>

<span data-ttu-id="d07ed-237">以前にオンプレミスの Skype for Business Server を展開したことがある場合は、QoS ポリシーを再調査しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-237">If you’ve previously deployed Skype for Business Server on-premises, you might need to re-examine your QoS policies.</span></span> <span data-ttu-id="d07ed-238">検証したポート範囲の設定に合わせてポリシーを調整して、チームの品質ユーザーエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d07ed-238">Adjust the policies to match port range settings you've verified provide a quality user experience for Teams.</span></span>

## <a name="validate-your-qos-implementation"></a><span data-ttu-id="d07ed-239">QoS の実装を検証する</span><span class="sxs-lookup"><span data-stu-id="d07ed-239">Validate your QoS implementation</span></span>

<span data-ttu-id="d07ed-240">QoS を有効にするには、GPO によって設定された DSCP 値が、通話の両端に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d07ed-240">For QoS to be effective, the DSCP value set by the GPO needs to be present at both ends of a call.</span></span> <span data-ttu-id="d07ed-241">チームクライアントによって生成されたトラフィックを分析することで、チームの作業負荷トラフィックがネットワーク内を移動したときに、DSCP 値が変更または削除されないことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-241">By analyzing the traffic generated by the Teams client, you can verify that the DSCP value isn’t changed or stripped out when the Teams workload traffic moves through the network.</span></span>

<span data-ttu-id="d07ed-242">可能であれば、ネットワークの出口ポイントでトラフィックをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="d07ed-242">Preferably, you capture traffic at the network egress point.</span></span> <span data-ttu-id="d07ed-243">スイッチまたはルータでポートミラーリングを使用して、この問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="d07ed-243">You can use port mirroring on a switch or router to help with this.</span></span>

## <a name="implement-qos-for-other-devices"></a><span data-ttu-id="d07ed-244">他のデバイスに QoS を実装する</span><span class="sxs-lookup"><span data-stu-id="d07ed-244">Implement QoS for other devices</span></span>

<span data-ttu-id="d07ed-245">Intune、Surface、iOS、Android、Mac の QoS の実装については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d07ed-245">Read these topics for information about implementing QoS for Intune, Surface, iOS, Android, and Mac</span></span>

- [<span data-ttu-id="d07ed-246">Surface Hub 2S の QoS</span><span class="sxs-lookup"><span data-stu-id="d07ed-246">QoS for Surface Hub 2S</span></span>](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)

- [<span data-ttu-id="d07ed-247">Surface Hub の QoS</span><span class="sxs-lookup"><span data-stu-id="d07ed-247">QoS for Surface Hub</span></span>](https://docs.microsoft.com/surface-hub/surface-hub-qos)

- [<span data-ttu-id="d07ed-248">IOS、Android、Mac の QoS</span><span class="sxs-lookup"><span data-stu-id="d07ed-248">QoS for iOS, Android, and Mac</span></span>](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a><span data-ttu-id="d07ed-249">関連項目</span><span class="sxs-lookup"><span data-stu-id="d07ed-249">Related topics</span></span>

- [<span data-ttu-id="d07ed-250">ビデオ : ネットワーク計画</span><span class="sxs-lookup"><span data-stu-id="d07ed-250">Video: Network Planning</span></span>](https://aka.ms/teams-networking)

- [<span data-ttu-id="d07ed-251">Microsoft Teams 用に組織のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="d07ed-251">Prepare your organization's network for Microsoft Teams</span></span>](prepare-network.md)

- [<span data-ttu-id="d07ed-252">チームクライアントでの QoS の実装</span><span class="sxs-lookup"><span data-stu-id="d07ed-252">Implement QoS in the Teams client</span></span>](QoS-in-Teams-clients.md)
