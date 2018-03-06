---
title: "Microsoft Teams 用に組織のネットワークを準備する"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: arachman
description: "ネットワーク要件、帯域幅要件、その他の考慮事項といった Microsoft Teams ネットワークの準備と管理について説明します。"
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0528d958f7e7f8f06f4dbfb1e38b297577436c56
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="d2168-104">Microsoft Teams 用に組織のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="d2168-104">Prepare your organization's network for Microsoft Teams</span></span>
=================================================

<span data-ttu-id="d2168-105">Teams は 3 つの形態のトラフィックを組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="d2168-105">Microsoft Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="d2168-106">Office 365 オンライン環境と Teams クライアント間のデータ トラフィック (信号、プレゼンス、チャット、ファイルのアップロードとダウンロード、OneNote 同期)。</span><span class="sxs-lookup"><span data-stu-id="d2168-106">Data traffic between the Office 365 online environment and the Microsoft Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="d2168-107">ピアツーピアのリアルタイムのコミュニケーション トラフィック (音声、ビデオ、デスクトップ共有)。</span><span class="sxs-lookup"><span data-stu-id="d2168-107">Conferencing real time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="d2168-108">会議型のリアルタイムのコミュニケーション トラフィック (音声、ビデオ、デスクトップ共有)。</span><span class="sxs-lookup"><span data-stu-id="d2168-108">Conferencing real time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="d2168-p102">この組み合わせは 2 つのレベルにおけるネットワークに対して影響を及ぼします。ピアツーピアの場合、トラフィックは Teams クライアント間で直接にフローします。会議のシナリオの場合、トラフィックは Office 365 環境と Teams クライアント間をフローします。最適なトラフィック フローを実現するには、内部ネットワーク セグメント間 (WAN 上でのサイト間) のフロー、さらにネットワーク サイトと Office 365 間のフローの両方を許可する必要があります。適切なポートを開かなかったり、特定のポートを自動的に遮断すると、ネットワーク エクスペリエンスの質が低下します。</span><span class="sxs-lookup"><span data-stu-id="d2168-p102">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer to peer and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios. To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example between sites over the WAN) as well as between the network sites and Office 365. Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="d2168-112">現在、iOS と Android モバイル デバイスでは会議がサポートされていますが、Windows Phone ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d2168-112">Currently, meetings are supported on iOS and Android mobile devices, but not on Windows Phone (support for Windows Phone is coming soon).</span></span>

<span data-ttu-id="d2168-113">Teams でリアルタイム メディアの最適な操作性を実現するには、Office 365 のネットワーク要件を満たす必要があります (詳しくは、「[Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="d2168-113">To get an optimal experience with real time media within Microsoft Teams, it is required to meet the Networking Requirements for Office 365 (please see the following source for more details: [Media Quality and Network Connectivity Performance for Skype for Business Online](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917) )</span></span> 

<span data-ttu-id="d2168-114">次の 2 つの重要なネットワーク セグメント (クライアントから Microsoft Edge、Customer Edge から Microsoft Edge) は、以下の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2168-114">The two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge) must met the following requirements:</span></span>


|<span data-ttu-id="d2168-115">値</span><span class="sxs-lookup"><span data-stu-id="d2168-115">Value</span></span>  |<span data-ttu-id="d2168-116">クライアントから Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d2168-116">Client to Microsoft Edge</span></span>  |<span data-ttu-id="d2168-117">Customer Edge から Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d2168-117">Customer Edge to Microsoft Edge</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="d2168-118">**遅延 (一方向)**</span><span class="sxs-lookup"><span data-stu-id="d2168-118">**Latency (one way)**</span></span>     |<span data-ttu-id="d2168-119">< 50 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="d2168-119">< 50ms</span></span>          |<span data-ttu-id="d2168-120">< 30 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="d2168-120">< 30ms</span></span>          |
|<span data-ttu-id="d2168-121">**遅延 (RTT または往復時間)**</span><span class="sxs-lookup"><span data-stu-id="d2168-121">**Latency (RTT or Round-trip Time)**</span></span> |<span data-ttu-id="d2168-122">< 100 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="d2168-122">< 100ms</span></span>         |<span data-ttu-id="d2168-123">< 60 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="d2168-123">< 60ms</span></span>         |
|<span data-ttu-id="d2168-124">**バースト パケット損失**</span><span class="sxs-lookup"><span data-stu-id="d2168-124">**Burst packet loss**</span></span>    |<span data-ttu-id="d2168-125">< 任意の 200 ミリ秒間隔で 10%</span><span class="sxs-lookup"><span data-stu-id="d2168-125"><10% during any 200ms interval</span></span>         |<span data-ttu-id="d2168-126">< 任意の 200 ミリ秒間隔で 1%</span><span class="sxs-lookup"><span data-stu-id="d2168-126"><1% during any 200 ms interval</span></span>         |
|<span data-ttu-id="d2168-127">**パケット損失**</span><span class="sxs-lookup"><span data-stu-id="d2168-127">**Packet loss**</span></span>     |<span data-ttu-id="d2168-128">< 任意の 15 秒間隔で 1%</span><span class="sxs-lookup"><span data-stu-id="d2168-128"><1% during any 15s interval</span></span>          |<span data-ttu-id="d2168-129">< 任意の 15 秒間隔で 0.1%</span><span class="sxs-lookup"><span data-stu-id="d2168-129"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="d2168-130">**パケット到着間ジッター**</span><span class="sxs-lookup"><span data-stu-id="d2168-130">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="d2168-131">< 15 秒間隔で 30 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="d2168-131"><30ms during any 15s interval</span></span>         |<span data-ttu-id="d2168-132">< 任意の 15 秒間隔で 15 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="d2168-132"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="d2168-133">**パケットの並べ替え**</span><span class="sxs-lookup"><span data-stu-id="d2168-133">**Packet reorder**</span></span>    |<span data-ttu-id="d2168-134">< 順序が適切でないパケットが 0.05%</span><span class="sxs-lookup"><span data-stu-id="d2168-134"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="d2168-135">< 順序が適切でないパケットが 0.01%</span><span class="sxs-lookup"><span data-stu-id="d2168-135"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="d2168-136">両方のネットワーク セグメントをテストするために、[Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799) をダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="d2168-136">To test both network segments, you can download the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="d2168-137">このツールは、クライアント PC に直接展開したり、Customer Network Edge に接続された PC に展開したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="d2168-137">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="d2168-138">ツールに含まれているドキュメントは限定的なものですので、ダウンロードとともに提供される詳細なドキュメントを必ず確認してください。</span><span class="sxs-lookup"><span data-stu-id="d2168-138">The tool includes limited documentation, so don't miss the extensive documentation included with the download.</span></span> <span data-ttu-id="d2168-139">この Network Readiness Assessment を実行することによって、Teams などのリアルタイム メディア アプリケーションを実行するためのネットワークの準備状況を検証することができます。</span><span class="sxs-lookup"><span data-stu-id="d2168-139">By running this Network Readiness Assessment, you can validate your network’s readiness to run a real-time media application such as Teams.</span></span>



> [!NOTE]
> <span data-ttu-id="d2168-140">これは Skype for Business を展開するカスタマ向けに推奨される Network Readiness Assessment と同じです。</span><span class="sxs-lookup"><span data-stu-id="d2168-140">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>

<a name="bandwidth-requirements"></a><span data-ttu-id="d2168-141">帯域幅要件</span><span class="sxs-lookup"><span data-stu-id="d2168-141">Bandwidth requirements</span></span>
----------

<span data-ttu-id="d2168-p104">Teams の帯域幅の計算は複雑であるため、それを支援する計算ツールが用意されています。この計算ツールにアクセスするには、<http://aka.ms/bwcalc> に移動してください。</span><span class="sxs-lookup"><span data-stu-id="d2168-p104">Bandwidth calculations for Microsoft Teams are complex and to help with this, a calculator has been created. To access the calculator, go here: <http://aka.ms/bwcalc/>.</span></span>

<span data-ttu-id="d2168-144">以下の内容は、付属的な背景情報として利用できます。ただし、[帯域幅計算ツール](https://aka.ms/bwcalc) を使用して必要な項目を追跡する場合は、推奨事項として参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="d2168-144">The content you will find below can be used as supplemental background information, however it is recommended that customers use the [Bandwidth Calculator](https://aka.ms/bwcalc) to track their needs.</span></span>



> [!IMPORTANT]
><span data-ttu-id="d2168-p105">必要とされる帯域幅が利用できない場合は、Teams 内部のメディア スタックにより、利用可能な帯域幅の不足量を補うため音声/ビデオ セッションの品質が低下し、その結果、通話や会議の品質も影響を受けます。Teams クライアントはビデオの品質よりもオーディオの品質を優先します。したがって、必要とされる帯域幅を利用可能な状態にすることが非常に重要になります。</span><span class="sxs-lookup"><span data-stu-id="d2168-p105">If the required bandwidth is not available, the media stack inside Microsoft Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Microsoft Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.</span></span>


|<span data-ttu-id="d2168-148">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="d2168-148">Activity</span></span>  |<span data-ttu-id="d2168-149">ダウンロードの帯域幅</span><span class="sxs-lookup"><span data-stu-id="d2168-149">Download Bandwidth</span></span>  |<span data-ttu-id="d2168-150">アップロードの帯域幅</span><span class="sxs-lookup"><span data-stu-id="d2168-150">Upload Bandwidth</span></span>  |<span data-ttu-id="d2168-151">トラフィック フロー</span><span class="sxs-lookup"><span data-stu-id="d2168-151">Traffic Flow</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="d2168-152">**ピアツーピア音声通話**</span><span class="sxs-lookup"><span data-stu-id="d2168-152">**Peer to peer Audio Call**</span></span>     |<span data-ttu-id="d2168-153">0.1 Mb</span><span class="sxs-lookup"><span data-stu-id="d2168-153">0.1 Mb</span></span>         |<span data-ttu-id="d2168-154">0.1Mb</span><span class="sxs-lookup"><span data-stu-id="d2168-154">0.1Mb</span></span>         |<span data-ttu-id="d2168-155">クライアント <> クライアント</span><span class="sxs-lookup"><span data-stu-id="d2168-155">Client <> Client</span></span>         |
|<span data-ttu-id="d2168-156">**ピアツーピア ビデオ通話 (全画面)**</span><span class="sxs-lookup"><span data-stu-id="d2168-156">**Peer to peer Video Call (full screen)**</span></span>     |<span data-ttu-id="d2168-157">4 Mb</span><span class="sxs-lookup"><span data-stu-id="d2168-157">4 Mb</span></span>         |<span data-ttu-id="d2168-158">4Mb</span><span class="sxs-lookup"><span data-stu-id="d2168-158">4Mb</span></span>         |<span data-ttu-id="d2168-159">クライアント <> クライアント</span><span class="sxs-lookup"><span data-stu-id="d2168-159">Client <> Client</span></span>          |
|<span data-ttu-id="d2168-160">**ピアツーピア デスクトップ共有 (1920\*1080 解像度)**</span><span class="sxs-lookup"><span data-stu-id="d2168-160">**Peer to peer Desktop Sharing (19201080 resolution)**</span></span>     |<span data-ttu-id="d2168-161">4 Mb</span><span class="sxs-lookup"><span data-stu-id="d2168-161">4 Mb</span></span>         |<span data-ttu-id="d2168-162">4 Mb</span><span class="sxs-lookup"><span data-stu-id="d2168-162">4 Mb</span></span>         |<span data-ttu-id="d2168-163">クライアント <> クライアント</span><span class="sxs-lookup"><span data-stu-id="d2168-163">Client <> Client</span></span>          |
|<span data-ttu-id="d2168-164">**2 人が参加する会議**</span><span class="sxs-lookup"><span data-stu-id="d2168-164">**2 Participant Meeting**</span></span>     |<span data-ttu-id="d2168-165">4 Mb</span><span class="sxs-lookup"><span data-stu-id="d2168-165">4 Mb</span></span>         |<span data-ttu-id="d2168-166">4 Mb</span><span class="sxs-lookup"><span data-stu-id="d2168-166">4 Mb</span></span>         |<span data-ttu-id="d2168-167">クライアント <> Office 365</span><span class="sxs-lookup"><span data-stu-id="d2168-167">Client <> Office 365</span></span>         |
|<span data-ttu-id="d2168-168">**3 人が参加する会議**</span><span class="sxs-lookup"><span data-stu-id="d2168-168">**3 participant meeting**</span></span>     |<span data-ttu-id="d2168-169">8 Mb</span><span class="sxs-lookup"><span data-stu-id="d2168-169">8 Mb</span></span>         |<span data-ttu-id="d2168-170">6.5 Mb</span><span class="sxs-lookup"><span data-stu-id="d2168-170">6.5 Mb</span></span>         |<span data-ttu-id="d2168-171">クライアント <> Office 365</span><span class="sxs-lookup"><span data-stu-id="d2168-171">Client <> Office 365</span></span>           |
|<span data-ttu-id="d2168-172">**4 人が参加する会議**</span><span class="sxs-lookup"><span data-stu-id="d2168-172">**4 participant meeting**</span></span>     |<span data-ttu-id="d2168-173">5.5 Mb</span><span class="sxs-lookup"><span data-stu-id="d2168-173">5.5 Mb</span></span>         |<span data-ttu-id="d2168-174">4 Mb</span><span class="sxs-lookup"><span data-stu-id="d2168-174">4 Mb</span></span>         |<span data-ttu-id="d2168-175">クライアント <> Office 365</span><span class="sxs-lookup"><span data-stu-id="d2168-175">Client <> Office 365</span></span>           |
|<span data-ttu-id="d2168-176">**5 人以上が参加する会議**</span><span class="sxs-lookup"><span data-stu-id="d2168-176">**5 participant+ meeting**</span></span>     |<span data-ttu-id="d2168-177">6 Mb</span><span class="sxs-lookup"><span data-stu-id="d2168-177">6 Mb</span></span>         |<span data-ttu-id="d2168-178">1.5 Mb</span><span class="sxs-lookup"><span data-stu-id="d2168-178">1.5 Mb</span></span>         |<span data-ttu-id="d2168-179">クライアント <> Office 365</span><span class="sxs-lookup"><span data-stu-id="d2168-179">Client <> Office 365</span></span>           |


<a name="additional-network-considerations"></a><span data-ttu-id="d2168-180">ネットワークに関する追加の考慮事項</span><span class="sxs-lookup"><span data-stu-id="d2168-180">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="d2168-181">**外部の名前解決**</span><span class="sxs-lookup"><span data-stu-id="d2168-181">**External Name Resolution**</span></span>

<span data-ttu-id="d2168-182">Teams を実行するすべてのクライアント コンピュータが外部 DNS クエリを解決して、Office 365 によって提供されるサービスを検出できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d2168-182">Ensure that all the client computers running Microsoft Teams client can resolve external DNS queries to discover the services provided by Office 365.</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="d2168-183">**NAT プール サイズ**</span><span class="sxs-lookup"><span data-stu-id="d2168-183">**NAT Pool Size**</span></span>

<span data-ttu-id="d2168-184">複数のユーザーまたはデバイスがネットワーク アドレス変換 (NAT) またはポート アドレス変換 (PAT) を使用して Office 365 にアクセスする場合は、パブリック ルーティング可能な各 IP アドレスの後ろに隠れているデバイスが、サポートされる数値を超過していないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2168-184">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP addresses do not exceed the supported number.</span></span>

<span data-ttu-id="d2168-p106">このリスクを軽減するには、適切なパブリック IP アドレスを NAT プールに割り当ててポート枯渇を回避します。ポート枯渇は、Office 365 サービスに接続するときに発生するエンドユーザーやデバイスの問題の原因となります。詳しくは、「[Office 365 の NAT サポート](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9)」ガイドをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d2168-p106">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion. Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services. For more information, please refer to [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9) guide.</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="d2168-188">**侵入検知/防御のガイダンス**</span><span class="sxs-lookup"><span data-stu-id="d2168-188">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="d2168-189">送信接続の追加のセキュリティ レイヤとして環境に侵入検知/防御システム (IDS/IPS) が配備されている場合は、送信先から Office 365 URL へのトラフィックがホワイトリストに記載されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d2168-189">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="d2168-190">ネットワーク正常性の確認</span><span class="sxs-lookup"><span data-stu-id="d2168-190">Network health determination</span></span>
-----------------

<span data-ttu-id="d2168-191">ネットワーク内で Teams を実装する計画を行う場合は、必要とされる帯域幅とすべての必須 IP アドレスへのアクセスが確保されていること、正しいポートが開かれていること、リアルタイム メディアのパフォーマンス要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2168-191">When planning on the implementation of Microsoft Teams within your network, you must ensure to have the required bandwidth, access to all required IP addresses, the correct ports opened, and are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="d2168-192">これらの条件を満たすことができない場合は通話や会議中の品質が悪くなるため、エンドユーザーは Teams の最適なエクスペリエンスを得ることができません。</span><span class="sxs-lookup"><span data-stu-id="d2168-192">If you know you will not meet these criteria, your end users will not get an optimal experience from Microsoft Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="d2168-193">これらの要件を満たしていない場合は、先に進む前にプロジェクトを中断して、条件を満たすことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d2168-193">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="d2168-195">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="d2168-195">Decision Point</span></span>         |<span data-ttu-id="d2168-196">リアルタイム メディアをサポートするためにネットワーク能力を評価したことはありますか?</span><span class="sxs-lookup"><span data-stu-id="d2168-196">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="d2168-197">ネットワークが正しく評価されていない場合やリアルタイム メディアをサポートできないことが事前に分かっている場合は、ビデオや画面共有の機能を無効にして、ネットワークへの影響を軽減し、Teams エクスペリエンスの質を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="d2168-197">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![次のステップ アイコン。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="d2168-199">次のステップ</span><span class="sxs-lookup"><span data-stu-id="d2168-199">Next Steps</span></span>         |<span data-ttu-id="d2168-200">ネットワークの品質が不明な場合: [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) のガイダンスに従って、お客様のネットワークでリアルタイム メディアに対する準備が整っているかどうかを判別してください。</span><span class="sxs-lookup"><span data-stu-id="d2168-200">Network Quality Unknown: Follow the Network Readiness Assessment guidance at skypeoperationsframework.com to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="d2168-201">ネットワークの品質が乏しい場合: ネットワーク改善の手順を実行して、高品質なリアルタイム メディアに適した環境を整えてください。</span><span class="sxs-lookup"><span data-stu-id="d2168-201">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="d2168-202">十分なネットワーク品質: すべての IP アドレスやポートに正しくアクセスできることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d2168-202">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

