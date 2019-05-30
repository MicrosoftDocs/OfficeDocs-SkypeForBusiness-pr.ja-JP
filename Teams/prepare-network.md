---
title: Microsoft Teams 用に組織のネットワークを準備する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/25/2019
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
ms.openlocfilehash: 330b62bc98d4a45d8d6902707dd2ebb9fd031913
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548279"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="9dc30-104">Microsoft Teams 用に組織のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="9dc30-104">Prepare your organization's network for Microsoft Teams</span></span>


<span data-ttu-id="9dc30-105">Teams は 3 つの形態のトラフィックを組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="9dc30-105">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="9dc30-106">Office 365 オンライン環境と Teams クライアント間のデータ トラフィック (信号、プレゼンス、チャット、ファイルのアップロードとダウンロード、OneNote 同期)。</span><span class="sxs-lookup"><span data-stu-id="9dc30-106">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="9dc30-107">ピアツーピアのリアルタイムのコミュニケーション トラフィック (音声、ビデオ、デスクトップ共有)。</span><span class="sxs-lookup"><span data-stu-id="9dc30-107">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="9dc30-108">会議型のリアルタイムのコミュニケーション トラフィック (音声、ビデオ、デスクトップ共有)。</span><span class="sxs-lookup"><span data-stu-id="9dc30-108">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="9dc30-p102">この組み合わせは 2 つのレベルにおけるネットワークに対して影響を及ぼします。ピアツーピアのシナリオの場合、トラフィックは Microsoft Teams クライアント間で直接にフローします。会議のシナリオの場合、トラフィックは Office 365 環境と Microsoft Teams クライアント間をフローします。最適なトラフィック フローを実現するには、内部ネットワーク セグメント間 (WAN 上でのサイト間) のフロー、さらにネットワーク サイトと Office 365 間のフローの両方を許可する必要があります。適切なポートを開かなかったり、特定のポートを自動的に遮断すると、ネットワーク エクスペリエンスの質が低下します。</span><span class="sxs-lookup"><span data-stu-id="9dc30-p102">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios. To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365. Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="9dc30-112">会議は iOS と Android モバイル デバイスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9dc30-112">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="9dc30-113">Microsoft Teams でリアルタイム メディアの最適な操作性を実現するには、Office 365 のネットワーク要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc30-113">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="9dc30-114">詳細については、「[Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9dc30-114">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="9dc30-115">2 つの重要なネットワーク セグメント (クライアントから Microsoft Edge、Customer Edge から Microsoft Edge) については、以下の推奨事項を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="9dc30-115">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="9dc30-116">値</span><span class="sxs-lookup"><span data-stu-id="9dc30-116">Value</span></span>  |<span data-ttu-id="9dc30-117">クライアントから Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9dc30-117">Client to Microsoft Edge</span></span>  |<span data-ttu-id="9dc30-118">Customer Edge から Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9dc30-118">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="9dc30-119">**遅延 (一方向)** \*</span><span class="sxs-lookup"><span data-stu-id="9dc30-119">**Latency (one way)** \*</span></span>  |<span data-ttu-id="9dc30-120">< 50 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="9dc30-120">< 50ms</span></span>          |<span data-ttu-id="9dc30-121">< 30 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="9dc30-121">< 30ms</span></span>         |
|<span data-ttu-id="9dc30-122">**遅延 (RTT または往復時間)** \*</span><span class="sxs-lookup"><span data-stu-id="9dc30-122">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="9dc30-123">< 100 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="9dc30-123">< 100ms</span></span>   |<span data-ttu-id="9dc30-124">< 60 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="9dc30-124">< 60ms</span></span> |
|<span data-ttu-id="9dc30-125">**バースト パケット損失**</span><span class="sxs-lookup"><span data-stu-id="9dc30-125">**Burst packet loss**</span></span>    |<span data-ttu-id="9dc30-126">< 任意の 200 ミリ秒間隔で 10%</span><span class="sxs-lookup"><span data-stu-id="9dc30-126"><10% during any 200ms interval</span></span>         |<span data-ttu-id="9dc30-127">< 任意の 200 ミリ秒間隔で 1%</span><span class="sxs-lookup"><span data-stu-id="9dc30-127"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="9dc30-128">**パケット損失**</span><span class="sxs-lookup"><span data-stu-id="9dc30-128">**Packet loss**</span></span>     |<span data-ttu-id="9dc30-129">< 任意の 15 秒間隔で 1%</span><span class="sxs-lookup"><span data-stu-id="9dc30-129"><1% during any 15s interval</span></span>          |<span data-ttu-id="9dc30-130">< 任意の 15 秒間隔で 0.1%</span><span class="sxs-lookup"><span data-stu-id="9dc30-130"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="9dc30-131">**パケット到着間ジッター**</span><span class="sxs-lookup"><span data-stu-id="9dc30-131">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="9dc30-132">< 15 秒間隔で 30 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="9dc30-132"><30ms during any 15s interval</span></span>         |<span data-ttu-id="9dc30-133">< 任意の 15 秒間隔で 15 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="9dc30-133"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="9dc30-134">**パケットの並べ替え**</span><span class="sxs-lookup"><span data-stu-id="9dc30-134">**Packet reorder**</span></span>    |<span data-ttu-id="9dc30-135">< 順序が適切でないパケットが 0.05%</span><span class="sxs-lookup"><span data-stu-id="9dc30-135"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="9dc30-136">< 順序が適切でないパケットが 0.01%</span><span class="sxs-lookup"><span data-stu-id="9dc30-136"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="9dc30-137">\*待機時間メトリック ターゲットは、会社の 1 つまたは複数のサイトと  Microsoft edge が同じ大陸にあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="9dc30-137">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="9dc30-138">Microsoft のネットワーク エッジへの会社のサイト接続には、WiFi またはその他のワイヤレス テクノロジとして使用できるファーストホップ ネットワーク アクセスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9dc30-138">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="9dc30-139">ネットワークのパフォーマンス目標は適切な帯域幅や[QoS 計画](QoS-in-Teams.md)を想定しています。</span><span class="sxs-lookup"><span data-stu-id="9dc30-139">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="9dc30-140">つまり、ネットワーク接続負荷のピーク時は、要件が Teams リアルタイム メディア トラフィックに直接適用されます。</span><span class="sxs-lookup"><span data-stu-id="9dc30-140">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="9dc30-141">両方のネットワーク セグメントをテストするために、[ネットワーク評価ツール](https://go.microsoft.com/fwlink/?linkid=855799)を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="9dc30-141">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="9dc30-142">このツールは、クライアント PC に直接展開したり、お客様のネットワーク エッジに接続された PC に展開したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="9dc30-142">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="9dc30-143">ツールに含まれているドキュメントは限定的ですが、ツールの使用についてのより詳細なドキュメントは「[Network Readiness Assessment (ネットワークの準備状況の評価)](https://go.microsoft.com/fwlink/?linkid=855800)」にあります。</span><span class="sxs-lookup"><span data-stu-id="9dc30-143">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="9dc30-144">このネットワークの準備状況の評価を実行することによって、Microsoft Teams などのリアルタイム メディア アプリケーションを実行するためのネットワークの準備状況を検証することができます。</span><span class="sxs-lookup"><span data-stu-id="9dc30-144">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="9dc30-145">これは Skype for Business を展開するカスタマ向けに推奨される Network Readiness Assessment と同じです。</span><span class="sxs-lookup"><span data-stu-id="9dc30-145">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="9dc30-146">帯域幅要件</span><span class="sxs-lookup"><span data-stu-id="9dc30-146">Bandwidth requirements</span></span>
<span data-ttu-id="9dc30-147">Microsoft Teams を使用すると、最高のオーディオ、ビデオ、およびコンテンツのエクスペリエンスをネットワークの状態に関係なく共有できます。</span><span class="sxs-lookup"><span data-stu-id="9dc30-147">Microsoft Teams gives you the best audio, video and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="9dc30-148">可変コーデックを使用すると、限られた帯域幅の環境で最小限の影響でメディアをネゴシエートできます。</span><span class="sxs-lookup"><span data-stu-id="9dc30-148">With variable codecs, media can be negotiated in limited bandwidth environments with minimal impact.</span></span> <span data-ttu-id="9dc30-149">しかし帯域幅が問題にならない場合は、最大 1080 p のビデオ解像度、最大 30 fps のビデオと 15 fps コンテンツの、ハイファイ オーディオなど、エクスペリエンスを品質に合わせて最適化できます。</span><span class="sxs-lookup"><span data-stu-id="9dc30-149">But where bandwidth is not a concern, experiences can be optimized for quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span>

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]


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

<a name="additional-network-considerations"></a><span data-ttu-id="9dc30-150">ネットワークに関する追加の考慮事項</span><span class="sxs-lookup"><span data-stu-id="9dc30-150">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="9dc30-151">外部の名前解決</span><span class="sxs-lookup"><span data-stu-id="9dc30-151">External Name Resolution</span></span>

<span data-ttu-id="9dc30-152">Teams を実行するすべてのクライアント コンピュータが外部 DNS クエリを解決して、Office 365 によって提供されるサービスを検出できること、およびファイアウォールが接続を妨げていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9dc30-152">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="9dc30-153">ファイアウォールのポートを構成する方法については、「 [Office 365 の URL と IP 範囲](office-365-urls-ip-address-ranges.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9dc30-153">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="9dc30-154">NAT プール サイズ</span><span class="sxs-lookup"><span data-stu-id="9dc30-154">NAT Pool Size</span></span>

<span data-ttu-id="9dc30-155">複数のユーザーまたはデバイスがネットワーク アドレス変換 (NAT) またはポート アドレス変換 (PAT) を使用して Office 365 にアクセスする場合は、パブリック ルーティング可能な各 IP アドレスの後ろに隠れているデバイスが、サポートされる数値を超過していないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc30-155">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="9dc30-156">このリスクを軽減するには、適切なパブリック IP アドレスを NAT プールに割り当ててポート枯渇を回避します。</span><span class="sxs-lookup"><span data-stu-id="9dc30-156">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="9dc30-157">ポート枯渇は、Office 365 サービスに接続するときに発生するエンドユーザーやデバイスの問題の原因となります。</span><span class="sxs-lookup"><span data-stu-id="9dc30-157">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="9dc30-158">詳細については、[Office 365 の NAT サポート](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9dc30-158">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="9dc30-159">**侵入検知/防御のガイダンス**</span><span class="sxs-lookup"><span data-stu-id="9dc30-159">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="9dc30-160">送信接続の追加のセキュリティ レイヤとして環境に侵入検知/防御システム (IDS/IPS) が配備されている場合は、送信先から Office 365 URL へのトラフィックがホワイトリストに記載されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9dc30-160">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="9dc30-161">ネットワーク正常性の確認</span><span class="sxs-lookup"><span data-stu-id="9dc30-161">Network health determination</span></span>
-----------------

<span data-ttu-id="9dc30-162">ネットワーク内で Microsoft Teams を実装する計画を行う場合は、必要とされる帯域幅とすべての必須 IP アドレスへのアクセスを確保していること、正しいポートが開かれていること、リアルタイム メディアのパフォーマンス要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dc30-162">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="9dc30-163">これらの条件を満たすことができない場合は通話や会議中の品質が悪くなるため、エンドユーザーは Teams の最適なエクスペリエンスを得ることができません。</span><span class="sxs-lookup"><span data-stu-id="9dc30-163">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="9dc30-164">これらの要件を満たしていない場合は、先に進む前にプロジェクトを中断して、条件を満たすことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9dc30-164">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![判断ポイントを表すアイコン](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="9dc30-166">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="9dc30-166">Decision Point</span></span>         |<span data-ttu-id="9dc30-167">リアルタイム メディアをサポートするためにネットワーク能力を評価したことはありますか?</span><span class="sxs-lookup"><span data-stu-id="9dc30-167">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="9dc30-168">ネットワークが正しく評価されていない場合やリアルタイム メディアをサポートできないことが事前に分かっている場合は、ビデオや画面共有の機能を無効にして、ネットワークへの影響を軽減し、Teams エクスペリエンスの質を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="9dc30-168">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![次の手順を示すアイコン](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="9dc30-170">次のステップ</span><span class="sxs-lookup"><span data-stu-id="9dc30-170">Next Steps</span></span>         |<span data-ttu-id="9dc30-171">ネットワークの品質が不明な場合: [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) のガイダンスに従って、お客様のネットワークでリアルタイム メディアに対する準備が整っているかどうかを判別してください。</span><span class="sxs-lookup"><span data-stu-id="9dc30-171">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="9dc30-172">ネットワークの品質が乏しい場合: ネットワーク改善の手順を実行して、高品質なリアルタイム メディアに適した環境を整えてください。</span><span class="sxs-lookup"><span data-stu-id="9dc30-172">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="9dc30-173">十分なネットワーク品質: すべての IP アドレスやポートに正しくアクセスできることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9dc30-173">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="9dc30-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="9dc30-174">Related Topics</span></span>

[<span data-ttu-id="9dc30-175">ビデオ : ネットワーク計画</span><span class="sxs-lookup"><span data-stu-id="9dc30-175">Video: Network Planning</span></span>](https://aka.ms/teams-networking)
