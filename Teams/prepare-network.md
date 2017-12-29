---
title: "Microsoft Teams 用に組織のネットワークを準備する | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "ネットワーク要件、帯域幅要件、その他の考慮事項といった Microsoft Teams ネットワークの準備と管理について説明します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 64d7ba35e8882fc0baa3522e1a5779b3e7ef8aaf
ms.sourcegitcommit: 83aa84750e0bd210c24b3bd7315020a451d3f056
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2017
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="36871-104">Microsoft Teams 用に組織のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="36871-104">Prepare your organization's network for Microsoft Teams</span></span>
=================================================

<span data-ttu-id="36871-105">Microsoft Teams は 3 つの形態のトラフィックを組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="36871-105">Microsoft Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="36871-106">Office 365 オンライン環境と Microsoft Teams クライアント間のデータ トラフィック (信号、プレゼンス、チャット、ファイルのアップロードとダウンロード、OneNote 同期)。</span><span class="sxs-lookup"><span data-stu-id="36871-106">Data traffic between the Office 365 online environment and the Microsoft Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="36871-107">ピアツーピアのリアルタイムのコミュニケーション トラフィック (音声、ビデオ、デスクトップ共有)。</span><span class="sxs-lookup"><span data-stu-id="36871-107">Peer to peer real time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="36871-108">会議型のリアルタイムのコミュニケーション トラフィック (音声、ビデオ、デスクトップ共有)。</span><span class="sxs-lookup"><span data-stu-id="36871-108">Conferencing real time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="36871-p102">この組み合わせは 2 つのレベルにおけるネットワークに対して影響を及ぼします。ピアツーピアの場合、トラフィックは Microsoft Teams クライアント間で直接にフローします。会議のシナリオの場合、トラフィックは Office 365 環境と Microsoft Teams クライアント間をフローします。最適なトラフィック フローを実現するには、内部ネットワーク セグメント間 (WAN 上でのサイト間) のフロー、さらにネットワーク サイトと Office 365 間のフローの両方を許可する必要があります。適切なポートを開かなかったり、特定のポートを自動的に遮断すると、ネットワーク エクスペリエンスの質が低下します。</span><span class="sxs-lookup"><span data-stu-id="36871-p102">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer to peer and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios. To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example between sites over the WAN) as well as between the network sites and Office 365. Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="36871-112">現在、iOS と Android モバイル デバイスでは会議がサポートされていますが、Windows Phone ではサポートされていません (Windows Phone でのサポートは準備中です)。</span><span class="sxs-lookup"><span data-stu-id="36871-112">Currently, meetings are supported on iOS and Android mobile devices, but not on Windows Phone (support for Windows Phone is coming soon).</span></span>

<span data-ttu-id="36871-113">Microsoft Teams でリアルタイム メディアの最適な操作性を実現するには、Office 365 のネットワーク要件を満たす必要があります (詳しくは、「[Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917?ui=en-US&rs=en-US&ad=US)」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="36871-113">To get an optimal experience with real time media within Microsoft Teams, it is required to meet the Networking Requirements for Office 365 (please see the following source for more details: [Media Quality and Network Connectivity Performance for Skype for Business Online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917?ui=en-US&rs=en-US&ad=US) )</span></span>

<span data-ttu-id="36871-114">次の 2 つの重要なネットワーク セグメント (クライアントから Microsoft Edge、Customer Edge から Microsoft Edge) は、以下の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="36871-114">The two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge) must met the following requirements:</span></span>


|<span data-ttu-id="36871-115">値</span><span class="sxs-lookup"><span data-stu-id="36871-115">Value</span></span>  |<span data-ttu-id="36871-116">クライアントから Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="36871-116">Client to Microsoft Edge</span></span>  |<span data-ttu-id="36871-117">Customer Edge から Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="36871-117">Customer Edge to Microsoft Edge</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="36871-118">**遅延 (一方向)**</span><span class="sxs-lookup"><span data-stu-id="36871-118">**Latency (one way)**</span></span>     |<span data-ttu-id="36871-119">< 50 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="36871-119">< 50ms</span></span>          |<span data-ttu-id="36871-120">< 30 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="36871-120">< 30ms</span></span>          |
|<span data-ttu-id="36871-121">**遅延 (RTT または往復時間)**</span><span class="sxs-lookup"><span data-stu-id="36871-121">**Latency (RTT or Round-trip Time)**</span></span> |<span data-ttu-id="36871-122">< 100 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="36871-122">< 100ms</span></span>         |<span data-ttu-id="36871-123">< 60 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="36871-123">< 60ms</span></span>         |
|<span data-ttu-id="36871-124">**バースト パケット損失**</span><span class="sxs-lookup"><span data-stu-id="36871-124">**Burst packet loss**</span></span>    |<span data-ttu-id="36871-125">< 任意の 200 ミリ秒間隔で 10%</span><span class="sxs-lookup"><span data-stu-id="36871-125"><10% during any 200ms interval</span></span>         |<span data-ttu-id="36871-126">< 任意の 200 ミリ秒間隔で 1%</span><span class="sxs-lookup"><span data-stu-id="36871-126"><1% during any 200 ms interval</span></span>         |
|<span data-ttu-id="36871-127">**パケット損失**</span><span class="sxs-lookup"><span data-stu-id="36871-127">**Packet loss**</span></span>     |<span data-ttu-id="36871-128">< 任意の 15 秒間隔で 1%</span><span class="sxs-lookup"><span data-stu-id="36871-128"><1% during any 15s interval</span></span>          |<span data-ttu-id="36871-129">< 任意の 15 秒間隔で 0.1%</span><span class="sxs-lookup"><span data-stu-id="36871-129"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="36871-130">**パケット到着間ジッター**</span><span class="sxs-lookup"><span data-stu-id="36871-130">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="36871-131">< 15 秒間隔で 30 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="36871-131"><30ms during any 15s interval</span></span>         |<span data-ttu-id="36871-132">< 任意の 15 秒間隔で 15 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="36871-132"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="36871-133">**パケットの並べ替え**</span><span class="sxs-lookup"><span data-stu-id="36871-133">**Packet reorder**</span></span>    |<span data-ttu-id="36871-134">< 順序が適切でないパケットが 0.05%</span><span class="sxs-lookup"><span data-stu-id="36871-134"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="36871-135">< 順序が適切でないパケットが 0.01%</span><span class="sxs-lookup"><span data-stu-id="36871-135"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="36871-p103">これらのネットワーク セグメントの両方をテストするには、Network Assessment Tool を使用できます (提供元: [https://www.microsoft.com/en-us/download/details.aspx?id=53885](https://go.microsoft.com/fwlink/?linkid=855799))。このツールは、クライアント PC で直接展開するか、Customer Network Edge に接続された PC/ラップトップで展開できます。このツールには簡易的なマニュアルが含まれています。このツールの使用法について詳細なマニュアルについては、[Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800) にアクセスしてください。この Network Readiness Assessment を実行すると、Microsoft Teams などのリアルタイム アプリケーションの実行に対するネットワークの準備を検証できます。</span><span class="sxs-lookup"><span data-stu-id="36871-p103">To test both network segments a Network Assessment Tool can be used (source: [https://www.microsoft.com/en-us/download/details.aspx?id=53885](https://go.microsoft.com/fwlink/?linkid=855799)). This tool can be deployed on both the client PC directly, as well as a PC/laptop connected to the Customer Network Edge. The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800). By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>



> [!NOTE]
> <span data-ttu-id="36871-140">これは Skype for Business を展開するカスタマ向けに推奨される Network Readiness Assessment と同じです。</span><span class="sxs-lookup"><span data-stu-id="36871-140">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>

<a name="bandwidth-requirements"></a><span data-ttu-id="36871-141">帯域幅要件</span><span class="sxs-lookup"><span data-stu-id="36871-141">Bandwidth requirements</span></span>
----------

<span data-ttu-id="36871-p104">Microsoft Teams の帯域幅の計算は複雑であるため、それを支援する計算ツールが用意されています。この計算ツールにアクセスするには、<http://aka.ms/bwcalc/> に移動してください。</span><span class="sxs-lookup"><span data-stu-id="36871-p104">Bandwidth calculations for Microsoft Teams are complex and to help with this, a calculator has been created. To access the calculator, go here: <http://aka.ms/bwcalc/>.</span></span>

<span data-ttu-id="36871-144">以下の内容は、付属的な背景情報として利用できます。ただし、[帯域幅計算ツール](https://aka.ms/bwcalc) を使用して必要な項目を追跡する場合は、推奨事項として参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="36871-144">The content you will find below can be used as supplemental background information, however it is recommended that customers use the [Bandwidth Calculator](https://aka.ms/bwcalc) to track their needs.</span></span>



> [!IMPORTANT]
><span data-ttu-id="36871-p105">必要とされる帯域幅が利用できない場合は、Microsoft Teams 内部のメディア スタックにより、利用可能な帯域幅の不足量を補うため音声/ビデオ セッションの品質が低下し、その結果、通話や会議の品質も影響を受けます。Microsoft Teams クライアントはビデオの品質よりもオーディオの品質を優先します。したがって、必要とされる帯域幅を利用可能な状態にすることが非常に重要になります。</span><span class="sxs-lookup"><span data-stu-id="36871-p105">If the required bandwidth is not available, the media stack inside Microsoft Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Microsoft Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.</span></span>


|<span data-ttu-id="36871-148">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="36871-148">Activity</span></span>  |<span data-ttu-id="36871-149">ダウンロードの帯域幅</span><span class="sxs-lookup"><span data-stu-id="36871-149">Download Bandwidth</span></span>  |<span data-ttu-id="36871-150">アップロードの帯域幅</span><span class="sxs-lookup"><span data-stu-id="36871-150">Upload Bandwidth</span></span>  |<span data-ttu-id="36871-151">トラフィック フロー</span><span class="sxs-lookup"><span data-stu-id="36871-151">Traffic Flow</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="36871-152">**ピアツーピア音声通話**</span><span class="sxs-lookup"><span data-stu-id="36871-152">**Peer to peer Audio Call**</span></span>     |<span data-ttu-id="36871-153">0.1 Mb</span><span class="sxs-lookup"><span data-stu-id="36871-153">0.1 Mb</span></span>         |<span data-ttu-id="36871-154">0.1Mb</span><span class="sxs-lookup"><span data-stu-id="36871-154">0.1Mb</span></span>         |<span data-ttu-id="36871-155">クライアント <> クライアント</span><span class="sxs-lookup"><span data-stu-id="36871-155">Client <> Client</span></span>         |
|<span data-ttu-id="36871-156">**ピアツーピア ビデオ通話 (全画面)**</span><span class="sxs-lookup"><span data-stu-id="36871-156">**Peer to peer Video Call (full screen)**</span></span>     |<span data-ttu-id="36871-157">4 Mb</span><span class="sxs-lookup"><span data-stu-id="36871-157">4 Mb</span></span>         |<span data-ttu-id="36871-158">4Mb</span><span class="sxs-lookup"><span data-stu-id="36871-158">4Mb</span></span>         |<span data-ttu-id="36871-159">クライアント <> クライアント</span><span class="sxs-lookup"><span data-stu-id="36871-159">Client <> Client</span></span>          |
|<span data-ttu-id="36871-160">**ピアツーピア デスクトップ共有 (1920*1080 解像度)**</span><span class="sxs-lookup"><span data-stu-id="36871-160">**Peer to peer Desktop Sharing (1920*1080 resolution)**</span></span>     |<span data-ttu-id="36871-161">4 Mb</span><span class="sxs-lookup"><span data-stu-id="36871-161">4 Mb</span></span>         |<span data-ttu-id="36871-162">4 Mb</span><span class="sxs-lookup"><span data-stu-id="36871-162">4 Mb</span></span>         |<span data-ttu-id="36871-163">クライアント <> クライアント</span><span class="sxs-lookup"><span data-stu-id="36871-163">Client <> Client</span></span>          |
|<span data-ttu-id="36871-164">**2 人が参加する会議**</span><span class="sxs-lookup"><span data-stu-id="36871-164">**2 Participant Meeting**</span></span>     |<span data-ttu-id="36871-165">4 Mb</span><span class="sxs-lookup"><span data-stu-id="36871-165">4 Mb</span></span>         |<span data-ttu-id="36871-166">4 Mb</span><span class="sxs-lookup"><span data-stu-id="36871-166">4 Mb</span></span>         |<span data-ttu-id="36871-167">クライアント <> Office 365</span><span class="sxs-lookup"><span data-stu-id="36871-167">Client <> Office 365</span></span>         |
|<span data-ttu-id="36871-168">**3 人が参加する会議**</span><span class="sxs-lookup"><span data-stu-id="36871-168">**3 participant meeting**</span></span>     |<span data-ttu-id="36871-169">8 Mb</span><span class="sxs-lookup"><span data-stu-id="36871-169">8 Mb</span></span>         |<span data-ttu-id="36871-170">6.5 Mb</span><span class="sxs-lookup"><span data-stu-id="36871-170">6.5 Mb</span></span>         |<span data-ttu-id="36871-171">クライアント <> Office 365</span><span class="sxs-lookup"><span data-stu-id="36871-171">Client <> Office 365</span></span>           |
|<span data-ttu-id="36871-172">**4 人が参加する会議**</span><span class="sxs-lookup"><span data-stu-id="36871-172">**4 participant meeting**</span></span>     |<span data-ttu-id="36871-173">5.5 Mb</span><span class="sxs-lookup"><span data-stu-id="36871-173">5.5 Mb</span></span>         |<span data-ttu-id="36871-174">4 Mb</span><span class="sxs-lookup"><span data-stu-id="36871-174">4 Mb</span></span>         |<span data-ttu-id="36871-175">クライアント <> Office 365</span><span class="sxs-lookup"><span data-stu-id="36871-175">Client <> Office 365</span></span>           |
|<span data-ttu-id="36871-176">**5 人以上が参加する会議**</span><span class="sxs-lookup"><span data-stu-id="36871-176">**5 participant+ meeting**</span></span>     |<span data-ttu-id="36871-177">6 Mb</span><span class="sxs-lookup"><span data-stu-id="36871-177">6 Mb</span></span>         |<span data-ttu-id="36871-178">1.5 Mb</span><span class="sxs-lookup"><span data-stu-id="36871-178">1.5 Mb</span></span>         |<span data-ttu-id="36871-179">クライアント <> Office 365</span><span class="sxs-lookup"><span data-stu-id="36871-179">Client <> Office 365</span></span>           |


<a name="additional-network-considerations"></a><span data-ttu-id="36871-180">ネットワークに関する追加の考慮事項</span><span class="sxs-lookup"><span data-stu-id="36871-180">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="36871-181">**外部の名前解決**</span><span class="sxs-lookup"><span data-stu-id="36871-181">**External Name Resolution**</span></span>

<span data-ttu-id="36871-182">Microsoft Teams を実行するすべてのクライアント コンピュータが外部 DNS クエリを解決して、Office 365 によって提供されるサービスを検出できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="36871-182">Ensure that all the client computers running Microsoft Teams client can resolve external DNS queries to discover the services provided by Office 365.</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="36871-183">**NAT プール サイズ**</span><span class="sxs-lookup"><span data-stu-id="36871-183">**NAT Pool Size**</span></span>

<span data-ttu-id="36871-184">複数のユーザーまたはデバイスがネットワーク アドレス変換 (NAT) またはポート アドレス変換 (PAT) を使用して Office 365 にアクセスする場合は、パブリック ルーティング可能な各 IP アドレスの後ろに隠れているデバイスが、サポートされる数値を超過していないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36871-184">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP addresses do not exceed the supported number.</span></span>

<span data-ttu-id="36871-p106">このリスクを軽減するには、適切なパブリック IP アドレスを NAT プールに割り当ててポート枯渇を回避します。ポート枯渇は、Office 365 サービスに接続するときに発生するエンドユーザーやデバイスの問題の原因となります。詳しくは、「[Office 365 の NAT サポート](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9)」ガイドをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="36871-p106">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion. Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services. For more information, please refer to [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9) guide.</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="36871-188">**侵入検知/防御のガイダンス**</span><span class="sxs-lookup"><span data-stu-id="36871-188">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="36871-189">送信接続の追加のセキュリティ レイヤとして環境に侵入検知/防御システム (IDS/IPS) が配備されている場合は、送信先から Office 365 URL へのトラフィックがホワイトリストに記載されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="36871-189">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="36871-190">ネットワーク正常性の確認</span><span class="sxs-lookup"><span data-stu-id="36871-190">Network health determination</span></span>
-----------------

<span data-ttu-id="36871-191">ネットワーク内で Microsoft Teams を実装する計画を行う場合は、必要とされる帯域幅とすべての必須 IP アドレスへのアクセスが確保されていること、正しいポートが開かれていること、リアルタイム メディアのパフォーマンス要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36871-191">When planning on the implementation of Microsoft Teams within your network, you must ensure to have the required bandwidth, access to all required IP addresses, the correct ports opened, and are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="36871-192">これらの条件を満たすことができない場合は通話や会議中の品質が悪くなるため、エンドユーザーは Microsoft Teams の最適なエクスペリエンスを得ることができません。</span><span class="sxs-lookup"><span data-stu-id="36871-192">If you know you will not meet these criteria, your end users will not get an optimal experience from Microsoft Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="36871-193">これらの要件を満たしていない場合は、先に進む前にプロジェクトを中断して、条件を満たすことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="36871-193">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="36871-195">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="36871-195">Decision Point</span></span>         |<span data-ttu-id="36871-196">リアルタイム メディアをサポートするためにネットワーク能力を評価したことはありますか?</span><span class="sxs-lookup"><span data-stu-id="36871-196">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="36871-197">ネットワークが正しく評価されていない場合やリアルタイム メディアをサポートできないことが事前に分かっている場合は、ビデオや画面共有の機能を無効にして、ネットワークへの影響を軽減し、Teams エクスペリエンスの質を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="36871-197">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![次のステップ アイコン。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="36871-199">次のステップ</span><span class="sxs-lookup"><span data-stu-id="36871-199">Next Steps</span></span>         |<span data-ttu-id="36871-200">ネットワークの品質が不明な場合: skypeoperationsframework.com で入手できる Network Readiness Assessment のガイダンスに従って、お客様のネットワークでリアルタイム メディアに対する準備が整っているかどうかを判別してください。</span><span class="sxs-lookup"><span data-stu-id="36871-200">Network Quality Unknown: Follow the Network Readiness Assessment guidance at skypeoperationsframework.com to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="36871-201">ネットワークの品質が乏しい場合: ネットワーク改善の手順を実行して、高品質なリアルタイム メディアに適した環境を整えてください。</span><span class="sxs-lookup"><span data-stu-id="36871-201">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="36871-202">十分なネットワーク品質: すべての IP アドレスやポートに正しくアクセスできることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="36871-202">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

