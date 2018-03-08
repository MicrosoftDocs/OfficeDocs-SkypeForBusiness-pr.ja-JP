---
title: "Microsoft チーム用の組織のネットワークを準備します。"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "準備し、Microsoft チーム ネットワークを管理する方法について説明します。情報には、ネットワークの要件には、帯域幅要件についてには、その他の考慮事項が含まれます。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: a89d4f201a0ea8f9392146e23629e6dd671bb7c3
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="e3528-104">Microsoft チーム用の組織のネットワークを準備します。</span><span class="sxs-lookup"><span data-stu-id="e3528-104">Prepare your organization's network for Microsoft Teams</span></span>
=================================================

<span data-ttu-id="e3528-105">Microsoft チームは、トラフィックの 3 つのフォームを結合します。</span><span class="sxs-lookup"><span data-stu-id="e3528-105">Microsoft Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="e3528-106">Microsoft チーム クライアント (シグナリング、プレゼンス、チャット、ファイルのアップロードとダウンロード、OneNote の同期) と Office 365 オンライン環境の間のデータ トラフィック。</span><span class="sxs-lookup"><span data-stu-id="e3528-106">Data traffic between the Office 365 online environment and the Microsoft Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="e3528-107">ピア ツー ピア (オーディオ、ビデオ、デスクトップの共有) のリアルタイムの通信は。</span><span class="sxs-lookup"><span data-stu-id="e3528-107">Peer to peer real time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="e3528-108">会議のリアルタイムの通信トラフィック (オーディオ、ビデオ、デスクトップの共有)。</span><span class="sxs-lookup"><span data-stu-id="e3528-108">Conferencing real time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="e3528-p102">これは、2 つのレベルのネットワークに影響を与える: ピア ツー ピアの直接 Microsoft チームのクライアントのトラフィックし、はトラフィックが Microsoft チーム クライアントと Office 365 環境間のシナリオに対応します。最適なトラフィックのことを確認するも間でフロー (たとえば、wan サイト) 間で内部ネットワーク セグメントの両方にトラフィックを許可ネットワーク サイトと Office 365 します。正しいポートを開いて、実際に特定のポートをブロックまたはされないは、機能性が低下エクスペリエンスになるされます。</span><span class="sxs-lookup"><span data-stu-id="e3528-p102">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer to peer and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios. To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example between sites over the WAN) as well as between the network sites and Office 365. Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="e3528-112">IOS および Android モバイル デバイスでは、Windows Phone ではなく、現時点では、会議がサポートされて (Windows Phone が準備中のサポート)。</span><span class="sxs-lookup"><span data-stu-id="e3528-112">Currently, meetings are supported on iOS and Android mobile devices, but not on Windows Phone (support for Windows Phone is coming soon).</span></span>

<span data-ttu-id="e3528-113">Microsoft チーム内でのリアルタイムのメディアの最適なエクスペリエンスを移動するには、Office 365 のネットワークの要件を満たす必要が (詳細については、次のソースを参照してください:[メディアの品質と skype for ネットワーク接続のパフォーマンスオンラインでビジネス](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917?ui=en-US&rs=en-US&ad=US))</span><span class="sxs-lookup"><span data-stu-id="e3528-113">To get an optimal experience with real time media within Microsoft Teams, it is required to meet the Networking Requirements for Office 365 (please see the following source for more details: [Media Quality and Network Connectivity Performance for Skype for Business Online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917?ui=en-US&rs=en-US&ad=US) )</span></span>

<span data-ttu-id="e3528-114">2 つのネットワーク セグメント (Microsoft Edge と Microsoft Edge に顧客の端にクライアント) を定義するには、次の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3528-114">The two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge) must met the following requirements:</span></span>


|<span data-ttu-id="e3528-115">値</span><span class="sxs-lookup"><span data-stu-id="e3528-115">Value</span></span>  |<span data-ttu-id="e3528-116">Microsoft Edge クライアント</span><span class="sxs-lookup"><span data-stu-id="e3528-116">Client to Microsoft Edge</span></span>  |<span data-ttu-id="e3528-117">Microsoft Edge 顧客エッジ</span><span class="sxs-lookup"><span data-stu-id="e3528-117">Customer Edge to Microsoft Edge</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="e3528-118">**待機時間 (1 つの方法)**</span><span class="sxs-lookup"><span data-stu-id="e3528-118">**Latency (one way)**</span></span>     |<span data-ttu-id="e3528-119">< 往復</span><span class="sxs-lookup"><span data-stu-id="e3528-119">< 50ms</span></span>          |<span data-ttu-id="e3528-120">< 30ms</span><span class="sxs-lookup"><span data-stu-id="e3528-120">< 30ms</span></span>          |
|<span data-ttu-id="e3528-121">**待機時間 (RTT またはラウンドト リップ時間)**</span><span class="sxs-lookup"><span data-stu-id="e3528-121">**Latency (RTT or Round-trip Time)**</span></span> |<span data-ttu-id="e3528-122">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="e3528-122">< 100ms</span></span>         |<span data-ttu-id="e3528-123">< 60 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="e3528-123">< 60ms</span></span>         |
|<span data-ttu-id="e3528-124">**バースト パケット損失**</span><span class="sxs-lookup"><span data-stu-id="e3528-124">**Burst packet loss**</span></span>    |<span data-ttu-id="e3528-125">< 200 ミリ秒間隔、10%</span><span class="sxs-lookup"><span data-stu-id="e3528-125"><10% during any 200ms interval</span></span>         |<span data-ttu-id="e3528-126">< 任意 200 ms 期間中に 1%</span><span class="sxs-lookup"><span data-stu-id="e3528-126"><1% during any 200 ms interval</span></span>         |
|<span data-ttu-id="e3528-127">**パケット損失**</span><span class="sxs-lookup"><span data-stu-id="e3528-127">**Packet loss**</span></span>     |<span data-ttu-id="e3528-128">< 任意の 15 秒の中に 1% 間隔</span><span class="sxs-lookup"><span data-stu-id="e3528-128"><1% during any 15s interval</span></span>          |<span data-ttu-id="e3528-129">< 任意の 15 秒の中に 0.1% 間隔</span><span class="sxs-lookup"><span data-stu-id="e3528-129"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="e3528-130">**パケット間到着ジッター**</span><span class="sxs-lookup"><span data-stu-id="e3528-130">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="e3528-131">< 30ms 中、15 秒間隔</span><span class="sxs-lookup"><span data-stu-id="e3528-131"><30ms during any 15s interval</span></span>         |<span data-ttu-id="e3528-132">< 任意の 15 秒の中に使う間隔</span><span class="sxs-lookup"><span data-stu-id="e3528-132"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="e3528-133">**パケットの並べ替え**</span><span class="sxs-lookup"><span data-stu-id="e3528-133">**Packet reorder**</span></span>    |<span data-ttu-id="e3528-134">< 0.05% 順序のパケット</span><span class="sxs-lookup"><span data-stu-id="e3528-134"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="e3528-135">< 0.01% 順序のパケット</span><span class="sxs-lookup"><span data-stu-id="e3528-135"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="e3528-p103">ネットワークの評価ツールを使用する両方のネットワーク セグメントをテストする (ソース: [https://www.microsoft.com/en-us/download/details.aspx?id=53885](https://go.microsoft.com/fwlink/?linkid=855799))。このツールは、両方、クライアント コンピューターで直接展開できます、PC/ラップトップ コンピューターがネットワークに接続されているにもエッジします。ツールには、制限付きのドキュメントが含まれていますが、ツールの使用に関するの詳細なドキュメントを参照してください:[ネットワークの準備ができて評価](https://go.microsoft.com/fwlink/?linkid=855800)します。このネットワークの準備ができて評価を実行すると、Microsoft チームなどのメディアのリアルタイムのアプリケーションを実行するネットワークの準備を検証することができます。</span><span class="sxs-lookup"><span data-stu-id="e3528-p103">To test both network segments a Network Assessment Tool can be used (source: [https://www.microsoft.com/en-us/download/details.aspx?id=53885](https://go.microsoft.com/fwlink/?linkid=855799)). This tool can be deployed on both the client PC directly, as well as a PC/laptop connected to the Customer Network Edge. The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800). By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>



> [!NOTE]
> <span data-ttu-id="e3528-140">これは、同じネットワーク準備ができて評価 Skype for Business を正しく配置しているお客様向けの実行をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e3528-140">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>

<a name="bandwidth-requirements"></a><span data-ttu-id="e3528-141">帯域幅の要件</span><span class="sxs-lookup"><span data-stu-id="e3528-141">Bandwidth requirements</span></span>
----------

<span data-ttu-id="e3528-p104">Microsoft チームの帯域幅計算が複雑なし、このため、計算シートを作成します。電卓をアクセスするには、参照先: <http://aka.ms/bwcalc/>します。</span><span class="sxs-lookup"><span data-stu-id="e3528-p104">Bandwidth calculations for Microsoft Teams are complex and to help with this, a calculator has been created. To access the calculator, go here: <http://aka.ms/bwcalc/>.</span></span>

<span data-ttu-id="e3528-144">ただし、お客様が[帯域幅計算機](https://aka.ms/bwcalc)を使用して、自分のニーズを追跡することをお勧めしますが、補足情報については、名前を付けての下にあるが検索されますが、コンテンツを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3528-144">The content you will find below can be used as supplemental background information, however it is recommended that customers use the [Bandwidth Calculator](https://aka.ms/bwcalc) to track their needs.</span></span>



> [!IMPORTANT]
><span data-ttu-id="e3528-p105">必要な帯域幅が利用できない場合は、Microsoft チーム内のメディア スタック量が低い利用可能な帯域幅、通話と会議の品質に影響を与えずに対応するために、音声/ビデオ セッションの品質が低下します。Microsoft チーム クライアントは、ビデオの品質、音声の品質を優先順位付けを試みます。そのために必要な帯域幅使用可能な非常に重要なはできます。</span><span class="sxs-lookup"><span data-stu-id="e3528-p105">If the required bandwidth is not available, the media stack inside Microsoft Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Microsoft Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.</span></span>


|<span data-ttu-id="e3528-148">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="e3528-148">Activity</span></span>  |<span data-ttu-id="e3528-149">帯域幅をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e3528-149">Download Bandwidth</span></span>  |<span data-ttu-id="e3528-150">帯域幅をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="e3528-150">Upload Bandwidth</span></span>  |<span data-ttu-id="e3528-151">トラフィックの流れ</span><span class="sxs-lookup"><span data-stu-id="e3528-151">Traffic Flow</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="e3528-152">**ピア ツー ピア音声通話**</span><span class="sxs-lookup"><span data-stu-id="e3528-152">**Peer to peer Audio Call**</span></span>     |<span data-ttu-id="e3528-153">0.1 mb</span><span class="sxs-lookup"><span data-stu-id="e3528-153">0.1 Mb</span></span>         |<span data-ttu-id="e3528-154">0.1 mb</span><span class="sxs-lookup"><span data-stu-id="e3528-154">0.1Mb</span></span>         |<span data-ttu-id="e3528-155">クライアント <></span><span class="sxs-lookup"><span data-stu-id="e3528-155">Client <> Client</span></span>         |
|<span data-ttu-id="e3528-156">**ピア ツー ピア映像通話 (フル スクリーン表示)**</span><span class="sxs-lookup"><span data-stu-id="e3528-156">**Peer to peer Video Call (full screen)**</span></span>     |<span data-ttu-id="e3528-157">4 mb</span><span class="sxs-lookup"><span data-stu-id="e3528-157">4 Mb</span></span>         |<span data-ttu-id="e3528-158">4 mb</span><span class="sxs-lookup"><span data-stu-id="e3528-158">4Mb</span></span>         |<span data-ttu-id="e3528-159">クライアント <></span><span class="sxs-lookup"><span data-stu-id="e3528-159">Client <> Client</span></span>          |
|<span data-ttu-id="e3528-160">**ピア ツー ピア デスクトップの共有 (1920 \* 1080 解像度)**</span><span class="sxs-lookup"><span data-stu-id="e3528-160">**Peer to peer Desktop Sharing (1920\*1080 resolution)**</span></span>     |<span data-ttu-id="e3528-161">4 mb</span><span class="sxs-lookup"><span data-stu-id="e3528-161">4 Mb</span></span>         |<span data-ttu-id="e3528-162">4 mb</span><span class="sxs-lookup"><span data-stu-id="e3528-162">4 Mb</span></span>         |<span data-ttu-id="e3528-163">クライアント <></span><span class="sxs-lookup"><span data-stu-id="e3528-163">Client <> Client</span></span>          |
|<span data-ttu-id="e3528-164">**2 つの参加者の会議**</span><span class="sxs-lookup"><span data-stu-id="e3528-164">**2 Participant Meeting**</span></span>     |<span data-ttu-id="e3528-165">4 mb</span><span class="sxs-lookup"><span data-stu-id="e3528-165">4 Mb</span></span>         |<span data-ttu-id="e3528-166">4 mb</span><span class="sxs-lookup"><span data-stu-id="e3528-166">4 Mb</span></span>         |<span data-ttu-id="e3528-167">クライアント <> Office 365</span><span class="sxs-lookup"><span data-stu-id="e3528-167">Client <> Office 365</span></span>         |
|<span data-ttu-id="e3528-168">**参加者の 3 つの会議**</span><span class="sxs-lookup"><span data-stu-id="e3528-168">**3 participant meeting**</span></span>     |<span data-ttu-id="e3528-169">8 mb</span><span class="sxs-lookup"><span data-stu-id="e3528-169">8 Mb</span></span>         |<span data-ttu-id="e3528-170">6.5 mb</span><span class="sxs-lookup"><span data-stu-id="e3528-170">6.5 Mb</span></span>         |<span data-ttu-id="e3528-171">クライアント <> Office 365</span><span class="sxs-lookup"><span data-stu-id="e3528-171">Client <> Office 365</span></span>           |
|<span data-ttu-id="e3528-172">**参加者の 4 つの会議**</span><span class="sxs-lookup"><span data-stu-id="e3528-172">**4 participant meeting**</span></span>     |<span data-ttu-id="e3528-173">5.5 mb</span><span class="sxs-lookup"><span data-stu-id="e3528-173">5.5 Mb</span></span>         |<span data-ttu-id="e3528-174">4 mb</span><span class="sxs-lookup"><span data-stu-id="e3528-174">4 Mb</span></span>         |<span data-ttu-id="e3528-175">クライアント <> Office 365</span><span class="sxs-lookup"><span data-stu-id="e3528-175">Client <> Office 365</span></span>           |
|<span data-ttu-id="e3528-176">**会議参加者 + 5**</span><span class="sxs-lookup"><span data-stu-id="e3528-176">**5 participant+ meeting**</span></span>     |<span data-ttu-id="e3528-177">6 mb</span><span class="sxs-lookup"><span data-stu-id="e3528-177">6 Mb</span></span>         |<span data-ttu-id="e3528-178">1.5 mb</span><span class="sxs-lookup"><span data-stu-id="e3528-178">1.5 Mb</span></span>         |<span data-ttu-id="e3528-179">クライアント <> Office 365</span><span class="sxs-lookup"><span data-stu-id="e3528-179">Client <> Office 365</span></span>           |


<a name="additional-network-considerations"></a><span data-ttu-id="e3528-180">その他のネットワークの考慮事項</span><span class="sxs-lookup"><span data-stu-id="e3528-180">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="e3528-181">**外部の名前解決**</span><span class="sxs-lookup"><span data-stu-id="e3528-181">**External Name Resolution**</span></span>

<span data-ttu-id="e3528-182">Microsoft チーム クライアントを実行しているすべてのクライアント コンピューターで Office 365 で提供されるサービスを検出する外部の DNS クエリを解決できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e3528-182">Ensure that all the client computers running Microsoft Teams client can resolve external DNS queries to discover the services provided by Office 365.</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="e3528-183">**NAT プールのサイズ**</span><span class="sxs-lookup"><span data-stu-id="e3528-183">**NAT Pool Size**</span></span>

<span data-ttu-id="e3528-184">複数のユーザーとデバイスは、ネットワークのアドレス変換 (NAT) またはポート アドレス翻訳 (藤巻) を使用して Office 365 にアクセスするときに、デバイスの後ろに非表示に公開ルーティング可能な IP アドレスを超えていないこと、サポートされている番号を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3528-184">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP addresses do not exceed the supported number.</span></span>

<span data-ttu-id="e3528-p106">このリスクを軽減するには、適切なパブリック IP アドレスがポート消費を防ぐために NAT プールに割り当てられていることを確認します。ポート消費によって、内部ユーザーとデバイスの問題 Office 365 サービスに接続しているときに発生します。詳細については、 [Office 365 の使用をサポートして NAT](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9)ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3528-p106">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion. Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services. For more information, please refer to [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9) guide.</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="e3528-188">**侵入の検出と防止ガイダンス**</span><span class="sxs-lookup"><span data-stu-id="e3528-188">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="e3528-189">環境に、侵入検出や送信接続のセキュリティの追加レイヤーの展開防止システム (ID/IP)] がある場合は、すべてのトラフィックと Office 365 の Url へのリンク先の whitelisted であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e3528-189">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="e3528-190">ネットワークの正常性の決定</span><span class="sxs-lookup"><span data-stu-id="e3528-190">Network health determination</span></span>
-----------------

<span data-ttu-id="e3528-191">計画: ネットワーク内で、マイクロソフトのチームの実装にすることを確認する必要がありますが必要な帯域幅、必要なすべての IP アドレスへのアクセスと正しいポートを開くと、リアルタイム メディアのパフォーマンスの要件を満たしています。</span><span class="sxs-lookup"><span data-stu-id="e3528-191">When planning on the implementation of Microsoft Teams within your network, you must ensure to have the required bandwidth, access to all required IP addresses, the correct ports opened, and are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="e3528-192">これらの条件を満たしていないがわかっている場合、エンドユーザーは表示されません操作が最適な Microsoft チームから悪い品質が原因で通話と会議中に。</span><span class="sxs-lookup"><span data-stu-id="e3528-192">If you know you will not meet these criteria, your end users will not get an optimal experience from Microsoft Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="e3528-193">いないこれらの条件を満たす必要があります、続行する前に、抽出条件を満たしていることを確認するプロジェクトを一時停止を検討する時間です。</span><span class="sxs-lookup"><span data-stu-id="e3528-193">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![判断するポイントをタップします。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="e3528-195">判断するポイント</span><span class="sxs-lookup"><span data-stu-id="e3528-195">Decision Point</span></span>         |<span data-ttu-id="e3528-196">リアルタイムのメディアをサポートするため、ネットワークの機能を評価したですか。</span><span class="sxs-lookup"><span data-stu-id="e3528-196">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="e3528-197">ネットワークが適切に評価されていないか、リアルタイム メディアができないことがわかっている場合は無効にするビデオと画面の共有ネットワークへの影響と低下チームのエクスペリエンスを削減する機能ですか。</span><span class="sxs-lookup"><span data-stu-id="e3528-197">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![次の手順をタップします。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="e3528-199">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e3528-199">Next Steps</span></span>         |<span data-ttu-id="e3528-200">ネットワークの品質不明な: ネットワークがリアルタイム メディアの準備を判断 skypeoperationsframework.com でネットワーク対応評価指示に従います。</span><span class="sxs-lookup"><span data-stu-id="e3528-200">Network Quality Unknown: Follow the Network Readiness Assessment guidance at skypeoperationsframework.com to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="e3528-201">ネットワークの品質が低下: では、高品質リアルタイム メディアの適切な環境を提供するネットワークの修復手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e3528-201">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="e3528-202">ネットワークの満足: は、すべての IP アドレスやポートが適切にアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e3528-202">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

