---
title: Microsoft Teams 用に組織のネットワークを準備する
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
description: ネットワーク要件、帯域幅要件、その他の考慮事項といった Microsoft Teams ネットワークの準備と管理について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c39924df868d7d9a3dae45a68b9785a4f493b35a
ms.sourcegitcommit: 889295b507c77a93b10b3a5e826f2b0c79c31f75
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2019
ms.locfileid: "30771711"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="5ab40-104">Microsoft Teams 用に組織のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="5ab40-104">Prepare your organization's network for Microsoft Teams</span></span>


<span data-ttu-id="5ab40-105">Teams は 3 つの形態のトラフィックを組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="5ab40-105">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="5ab40-106">Office 365 オンライン環境と Teams クライアント間のデータ トラフィック (信号、プレゼンス、チャット、ファイルのアップロードとダウンロード、OneNote 同期)。</span><span class="sxs-lookup"><span data-stu-id="5ab40-106">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="5ab40-107">ピアツーピアのリアルタイムのコミュニケーション トラフィック (音声、ビデオ、デスクトップ共有)。</span><span class="sxs-lookup"><span data-stu-id="5ab40-107">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="5ab40-108">会議型のリアルタイムのコミュニケーション トラフィック (音声、ビデオ、デスクトップ共有)。</span><span class="sxs-lookup"><span data-stu-id="5ab40-108">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="5ab40-p102">この組み合わせは 2 つのレベルにおけるネットワークに対して影響を及ぼします。ピアツーピアのシナリオの場合、トラフィックは Microsoft Teams クライアント間で直接にフローします。会議のシナリオの場合、トラフィックは Office 365 環境と Microsoft Teams クライアント間をフローします。最適なトラフィック フローを実現するには、内部ネットワーク セグメント間 (WAN 上でのサイト間) のフロー、さらにネットワーク サイトと Office 365 間のフローの両方を許可する必要があります。適切なポートを開かなかったり、特定のポートを自動的に遮断すると、ネットワーク エクスペリエンスの質が低下します。</span><span class="sxs-lookup"><span data-stu-id="5ab40-p102">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios. To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365. Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="5ab40-112">会議は、iOS および Android モバイル デバイスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5ab40-112">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="5ab40-113">マイクロソフトのチーム内でのリアルタイム メディアに最適なエクスペリエンスを得るには、ネットワークは、Office 365 のネットワーク要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ab40-113">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="5ab40-114">詳細については、「[Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5ab40-114">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="5ab40-115">2 つの重要なネットワーク セグメント (クライアントから Microsoft Edge、Customer Edge から Microsoft Edge) については、以下の推奨事項を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="5ab40-115">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="5ab40-116">値</span><span class="sxs-lookup"><span data-stu-id="5ab40-116">Value</span></span>  |<span data-ttu-id="5ab40-117">クライアントから Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5ab40-117">Client to Microsoft Edge</span></span>  |<span data-ttu-id="5ab40-118">Customer Edge から Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5ab40-118">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="5ab40-119">**待機時間 (1 つの方法)**\*</span><span class="sxs-lookup"><span data-stu-id="5ab40-119">**Latency (one way)** \*</span></span>  |<span data-ttu-id="5ab40-120">< 50 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="5ab40-120">< 50ms</span></span>          |<span data-ttu-id="5ab40-121">< 30 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="5ab40-121">< 30ms</span></span>         |
|<span data-ttu-id="5ab40-122">**RTT (ラウンドト リップ時間) の待機時間**\*</span><span class="sxs-lookup"><span data-stu-id="5ab40-122">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="5ab40-123">< 100 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="5ab40-123">< 100ms</span></span>   |<span data-ttu-id="5ab40-124">< 60 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="5ab40-124">< 60ms</span></span> |
|<span data-ttu-id="5ab40-125">**バースト パケット損失**</span><span class="sxs-lookup"><span data-stu-id="5ab40-125">**Burst packet loss**</span></span>    |<span data-ttu-id="5ab40-126">< 任意の 200 ミリ秒間隔で 10%</span><span class="sxs-lookup"><span data-stu-id="5ab40-126"><10% during any 200ms interval</span></span>         |<span data-ttu-id="5ab40-127">< 任意の 200 ミリ秒間隔で 1%</span><span class="sxs-lookup"><span data-stu-id="5ab40-127"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="5ab40-128">**パケット損失**</span><span class="sxs-lookup"><span data-stu-id="5ab40-128">**Packet loss**</span></span>     |<span data-ttu-id="5ab40-129">< 任意の 15 秒間隔で 1%</span><span class="sxs-lookup"><span data-stu-id="5ab40-129"><1% during any 15s interval</span></span>          |<span data-ttu-id="5ab40-130">< 任意の 15 秒間隔で 0.1%</span><span class="sxs-lookup"><span data-stu-id="5ab40-130"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="5ab40-131">**パケット到着間ジッター**</span><span class="sxs-lookup"><span data-stu-id="5ab40-131">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="5ab40-132">< 15 秒間隔で 30 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="5ab40-132"><30ms during any 15s interval</span></span>         |<span data-ttu-id="5ab40-133">< 任意の 15 秒間隔で 15 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="5ab40-133"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="5ab40-134">**パケットの並べ替え**</span><span class="sxs-lookup"><span data-stu-id="5ab40-134">**Packet reorder**</span></span>    |<span data-ttu-id="5ab40-135">< 順序が適切でないパケットが 0.05%</span><span class="sxs-lookup"><span data-stu-id="5ab40-135"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="5ab40-136">< 順序が適切でないパケットが 0.01%</span><span class="sxs-lookup"><span data-stu-id="5ab40-136"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="5ab40-137">\*遅延のメトリック ターゲットは、会社のサイトまたはサイトを想定し、同じ大陸には、マイクロソフトのエッジ。</span><span class="sxs-lookup"><span data-stu-id="5ab40-137">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="5ab40-138">Microsoft ネットワークのエッジに、企業サイトの接続には、WiFi または他のワイヤレス技術は、最初のホップ ネットワーク アクセスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5ab40-138">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="5ab40-139">ネットワーク パフォーマンスの目標は、適切な帯域幅と[QoS の計画](QoS-in-Teams.md)と仮定します。</span><span class="sxs-lookup"><span data-stu-id="5ab40-139">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="5ab40-140">つまり、要件は、ピーク負荷の下では、ネットワーク接続とチーム リアルタイム メディアのトラフィックを直接適用されます。</span><span class="sxs-lookup"><span data-stu-id="5ab40-140">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="5ab40-141">両方のネットワーク セグメントをテストするには、[ネットワーク評価ツール](https://go.microsoft.com/fwlink/?linkid=855799)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5ab40-141">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="5ab40-142">直接およびお客様のネットワークのエッジに接続されている PC では、両方のクライアント コンピューターでこのツールを展開できます。</span><span class="sxs-lookup"><span data-stu-id="5ab40-142">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="5ab40-143">ツールには、制限付きのマニュアルが含まれていますが、ツールの使用方法をより深いレベルのマニュアルを参照してください:[ネットワーク対応の評価](https://go.microsoft.com/fwlink/?linkid=855800)。</span><span class="sxs-lookup"><span data-stu-id="5ab40-143">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="5ab40-144">このネットワーク対応の評価を実行すると、マイクロソフトのチームなどのリアルタイム メディアのアプリケーションを実行するのには、ネットワークの準備を検証できます。</span><span class="sxs-lookup"><span data-stu-id="5ab40-144">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="5ab40-145">これは、ビジネス用の Skype を正常に展開しているお客様向けの実行に推奨されている同じネットワーク対応の評価です。</span><span class="sxs-lookup"><span data-stu-id="5ab40-145">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="5ab40-146">帯域幅の要件</span><span class="sxs-lookup"><span data-stu-id="5ab40-146">Bandwidth requirements</span></span>


<span data-ttu-id="5ab40-147">この資料では、マイクロソフトのチームのリアルタイム オーディオ、ビデオ、およびデスクトップのさまざまな用途の様相を共有して帯域幅を利用する方法の簡単なバージョンについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5ab40-147">This article describes a concise version of how bandwidth is utilized by Microsoft Teams real time audio, video, and desktop sharing modalities in various use cases.</span></span> <span data-ttu-id="5ab40-148">チームは常に帯域幅の使用に慎重であり、1.2Mbps での HD ビデオの品質を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="5ab40-148">Teams is always conservative on bandwidth utilization and can deliver HD video quality in under 1.2Mbps.</span></span>  <span data-ttu-id="5ab40-149">各オーディオとビデオ通話や会議での実際の帯域幅の消費量が異なる、レイアウトのビデオ、ビデオの解像度、ビデオのフレーム数/秒など、いくつかの要因に基づいています。</span><span class="sxs-lookup"><span data-stu-id="5ab40-149">The actual bandwidth consumption in each audio/video call or meeting will vary, based on several factors, such as video layout, video resolution, and video frames per second.</span></span> <span data-ttu-id="5ab40-150">多くの帯域幅が利用可能な品質と使用法が最適なエクスペリエンスを実現するのには増加します。</span><span class="sxs-lookup"><span data-stu-id="5ab40-150">When more bandwidth is available quality and usage will increase to deliver the best experience.</span></span>


|<span data-ttu-id="5ab40-151">Bandwidth(up/down)</span><span class="sxs-lookup"><span data-stu-id="5ab40-151">Bandwidth(up/down)</span></span> |<span data-ttu-id="5ab40-152">シナリオ</span><span class="sxs-lookup"><span data-stu-id="5ab40-152">Scenarios</span></span> |
|---|---|
|<span data-ttu-id="5ab40-153">30 kbps</span><span class="sxs-lookup"><span data-stu-id="5ab40-153">30 kbps</span></span> |<span data-ttu-id="5ab40-154">ピア ツー ピア音声通話</span><span class="sxs-lookup"><span data-stu-id="5ab40-154">Peer-to-peer audio calling</span></span> |
|<span data-ttu-id="5ab40-155">130 kbps</span><span class="sxs-lookup"><span data-stu-id="5ab40-155">130 kbps</span></span> |<span data-ttu-id="5ab40-156">ピア ツー ピア音声通話や画面共有</span><span class="sxs-lookup"><span data-stu-id="5ab40-156">Peer-to-peer audio calling and screen sharing</span></span> |
|<span data-ttu-id="5ab40-157">500 kbps</span><span class="sxs-lookup"><span data-stu-id="5ab40-157">500 kbps</span></span> |<span data-ttu-id="5ab40-158">ピア ツー ピアの品質のビデオの 30 fps で 360 p を呼び出す</span><span class="sxs-lookup"><span data-stu-id="5ab40-158">Peer-to-peer quality video calling 360p at 30fps</span></span> |
|<span data-ttu-id="5ab40-159">1.2 Mbps</span><span class="sxs-lookup"><span data-stu-id="5ab40-159">1.2 Mbps</span></span> |<span data-ttu-id="5ab40-160">ピア ツー ピア HD 品質のビデオ解像度の 30 fps で 720 p の HD を呼び出す</span><span class="sxs-lookup"><span data-stu-id="5ab40-160">Peer-to-peer HD quality video calling with resolution of HD 720p at 30fps</span></span> |
|<span data-ttu-id="5ab40-161">1.5 Mbps</span><span class="sxs-lookup"><span data-stu-id="5ab40-161">1.5 Mbps</span></span> |<span data-ttu-id="5ab40-162">ピア ツー ピア HD 品質のビデオ解像度の 30 fps で 1080 p の HD を呼び出す</span><span class="sxs-lookup"><span data-stu-id="5ab40-162">Peer-to-peer HD quality video calling with resolution of HD 1080p at 30fps</span></span> |
|<span data-ttu-id="5ab40-163">500 kbps/1Mbps</span><span class="sxs-lookup"><span data-stu-id="5ab40-163">500kbps/1Mbps</span></span> |<span data-ttu-id="5ab40-164">グループ ビデオ通話</span><span class="sxs-lookup"><span data-stu-id="5ab40-164">Group Video calling</span></span> |
|<span data-ttu-id="5ab40-165">1Mbps/2Mbps</span><span class="sxs-lookup"><span data-stu-id="5ab40-165">1Mbps/2Mbps</span></span> |<span data-ttu-id="5ab40-166">HD グループのビデオ (1080 p の画面でビデオを 540 p) を呼び出す</span><span class="sxs-lookup"><span data-stu-id="5ab40-166">HD Group video calling (540p videos on 1080p screen)</span></span> |

<!--
The content you will find below can be used as supplemental background information; however, it is recommended that customers use [Network Planner](https://aka.ms/bwcalc) to track their needs.

> [!IMPORTANT]
>If the required bandwidth is not available, the media stack inside Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.


|Activity  |Download Bandwidth  |Upload Bandwidth  |Traffic Flow |
|---------|---------|---------|---------|
|**Peer to peer Audio Call**     |0.1 Mb         |0.1Mb         |Client <> Client         |
|**Peer to peer Video Call (full screen)**     |4 Mb         |4Mb         |Client <> Client          |
|**Peer to peer Desktop Sharing (1920*1080 resolution)**     |4 Mb         |4 Mb         |Client <> Client          |
|**2 Participant Meeting**     |4 Mb         |4 Mb         |Client <> Office 365         |
|**3 participant meeting**     |8 Mb         |6.5 Mb         |Client <> Office 365           |
|**4 participant meeting**     |5.5 Mb         |4 Mb         |Client <> Office 365           |
|**5 participant+ meeting**     |6 Mb         |1.5 Mb         |Client <> Office 365           |
-->

<a name="additional-network-considerations"></a><span data-ttu-id="5ab40-167">追加のネットワークに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="5ab40-167">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="5ab40-168">外部の名前解決</span><span class="sxs-lookup"><span data-stu-id="5ab40-168">External Name Resolution</span></span>

<span data-ttu-id="5ab40-169">チームのクライアントを実行するすべてのクライアント コンピューターで、Office 365 が提供するサービスを検出するのには外部の DNS クエリを解決できることと、ファイアウォールがアクセスを遮断していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ab40-169">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="5ab40-170">ファイアウォール ポートを構成する方法の詳細については、 [Office 365 の Url と IP の範囲](office-365-urls-ip-address-ranges.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ab40-170">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="5ab40-171">NAT プール サイズ</span><span class="sxs-lookup"><span data-stu-id="5ab40-171">NAT Pool Size</span></span>

<span data-ttu-id="5ab40-172">複数のユーザーとデバイスは、ネットワーク アドレス変換 (NAT) またはポート アドレス変換 (PAT) を使用して Office 365 にアクセスするときは、公的にルーティング可能な各 IP アドレスの背後にある非表示のデバイスがサポートされている数を超えていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ab40-172">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="5ab40-173">このリスクを軽減するには、ポートの枯渇を防ぐために適切なパブリック IP アドレスが NAT プールに割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ab40-173">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="5ab40-174">ポートの消費と、内部のエンド ・ ユーザーとデバイスは、Office 365 サービスに接続するときの問題に直面します。</span><span class="sxs-lookup"><span data-stu-id="5ab40-174">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="5ab40-175">詳細については、 [NAT は、Office 365 のサポート](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ab40-175">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="5ab40-176">**侵入検知と防止の手引き**</span><span class="sxs-lookup"><span data-stu-id="5ab40-176">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="5ab40-177">お客様の環境が、侵入検知および防止システム (IDS/IPS) の送信接続のセキュリティの追加レイヤーとして配置されている場合、Office 365 の Url へのリンク先をすべてのトラフィックが whitelisted ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ab40-177">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="5ab40-178">ネットワーク正常性の決定</span><span class="sxs-lookup"><span data-stu-id="5ab40-178">Network health determination</span></span>
-----------------

<span data-ttu-id="5ab40-179">マイクロソフト チームのネットワーク内での実装を計画するときことを必要な帯域幅がある場合、すべて必須の IP アドレスを開くと、適切なポートへのアクセスがあり、リアルタイム メディアのパフォーマンス要件を達成します。.</span><span class="sxs-lookup"><span data-stu-id="5ab40-179">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="5ab40-180">これらの条件に適合していない場合は、エンド ・ ユーザーは表示されません最適なエクスペリエンス チームから品質が悪いため通話や会議中に。</span><span class="sxs-lookup"><span data-stu-id="5ab40-180">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="5ab40-181">いないこれらの条件を満たす必要があります、これは、時間を続行する前に、条件を満たしていることを確認するプロジェクトを一時停止を検討してください。</span><span class="sxs-lookup"><span data-stu-id="5ab40-181">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="5ab40-183">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="5ab40-183">Decision Point</span></span>         |<span data-ttu-id="5ab40-184">リアルタイム メディアをサポートするため、ネットワークの機能を評価するでしょうか。</span><span class="sxs-lookup"><span data-stu-id="5ab40-184">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="5ab40-185">ネットワークが適切に評価されていない、またはリアルタイム メディアができないことがわかって、無効にしてもビデオと画面の共有ネットワークへの影響とチーム エクスペリエンスの低下を軽減する機能ですか。</span><span class="sxs-lookup"><span data-stu-id="5ab40-185">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![次のステップ アイコン。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="5ab40-187">次のステップ</span><span class="sxs-lookup"><span data-stu-id="5ab40-187">Next Steps</span></span>         |<span data-ttu-id="5ab40-188">ネットワーク品質不明: ネットワークのリアルタイム メディアの準備ができたかを判断するのには[ネットワーク対応の評価](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="5ab40-188">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="5ab40-189">ネットワークの品質が低下します。 は、高品質リアルタイム メディアの適切な環境を提供するネットワークの改善手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5ab40-189">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="5ab40-190">ネットワーク満足: は、すべての IP アドレスとポートが正しくアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5ab40-190">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="5ab40-191">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5ab40-191">Related Topics</span></span>

[<span data-ttu-id="5ab40-192">ビデオ: ネットワークの計画</span><span class="sxs-lookup"><span data-stu-id="5ab40-192">Video: Network Planning</span></span>](https://aka.ms/teams-networking)
