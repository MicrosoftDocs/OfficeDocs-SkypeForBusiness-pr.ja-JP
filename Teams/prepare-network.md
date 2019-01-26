---
title: Microsoft Teams 用に組織のネットワークを準備する
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: arachman
description: ネットワーク要件、帯域幅要件、その他の考慮事項といった Microsoft Teams ネットワークの準備と管理について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2af8872253e2962322712a013cb3043a7da2d81b
ms.sourcegitcommit: c0679cbaf7df38769f722afd65c4232311d25515
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2019
ms.locfileid: "29562630"
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="bcf72-104">Microsoft Teams 用に組織のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="bcf72-104">Prepare your organization's network for Microsoft Teams</span></span>
=================================================

> [!Tip]
> <span data-ttu-id="bcf72-105">については、次のセッションを監視するチームをするための方法、ネットワークとの最適なネットワーク接続の最適な計画を立てる方法を活用:[チーム ネットワークの計画](https://aka.ms/teams-networking)</span><span class="sxs-lookup"><span data-stu-id="bcf72-105">Watch the following session to learn how to Teams leverages your network and how to best plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking)</span></span>


<span data-ttu-id="bcf72-106">Teams は 3 つの形態のトラフィックを組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="bcf72-106">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="bcf72-107">Office 365 オンライン環境と Teams クライアント間のデータ トラフィック (信号、プレゼンス、チャット、ファイルのアップロードとダウンロード、OneNote 同期)。</span><span class="sxs-lookup"><span data-stu-id="bcf72-107">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="bcf72-108">ピアツーピアのリアルタイムのコミュニケーション トラフィック (音声、ビデオ、デスクトップ共有)。</span><span class="sxs-lookup"><span data-stu-id="bcf72-108">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="bcf72-109">会議型のリアルタイムのコミュニケーション トラフィック (音声、ビデオ、デスクトップ共有)。</span><span class="sxs-lookup"><span data-stu-id="bcf72-109">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="bcf72-p102">この組み合わせは 2 つのレベルにおけるネットワークに対して影響を及ぼします。ピアツーピアのシナリオの場合、トラフィックは Microsoft Teams クライアント間で直接にフローします。会議のシナリオの場合、トラフィックは Office 365 環境と Microsoft Teams クライアント間をフローします。最適なトラフィック フローを実現するには、内部ネットワーク セグメント間 (WAN 上でのサイト間) のフロー、さらにネットワーク サイトと Office 365 間のフローの両方を許可する必要があります。適切なポートを開かなかったり、特定のポートを自動的に遮断すると、ネットワーク エクスペリエンスの質が低下します。</span><span class="sxs-lookup"><span data-stu-id="bcf72-p102">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios. To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365. Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="bcf72-113">会議は、iOS および Android モバイル デバイスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bcf72-113">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="bcf72-114">Microsoft Teams でリアルタイム メディアの最適な操作性を実現するには、Office 365 のネットワーク要件を満たす必要があります </span><span class="sxs-lookup"><span data-stu-id="bcf72-114">To get an optimal experience with real time media within Microsoft Teams, it is required to meet the networking requirements for Office 365.</span></span> <span data-ttu-id="bcf72-115">詳細については、「[Skype for Business Online におけるメディアの品質とネットワーク接続性のパフォーマンス](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bcf72-115">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="bcf72-116">2 つ定義するネットワーク セグメント (マイクロソフトのエッジにクライアント) およびマイクロソフトのエッジにエッジを顧客、次の推奨事項を検討してください。</span><span class="sxs-lookup"><span data-stu-id="bcf72-116">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="bcf72-117">値</span><span class="sxs-lookup"><span data-stu-id="bcf72-117">Value</span></span>  |<span data-ttu-id="bcf72-118">クライアントから Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bcf72-118">Client to Microsoft Edge</span></span>  |<span data-ttu-id="bcf72-119">Customer Edge から Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bcf72-119">Customer Edge to Microsoft Edge</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="bcf72-120">**遅延 (一方向)**</span><span class="sxs-lookup"><span data-stu-id="bcf72-120">**Latency (one way)**</span></span>     |<span data-ttu-id="bcf72-121">< 50 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="bcf72-121">< 50ms</span></span>          |<span data-ttu-id="bcf72-122">< 30 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="bcf72-122">< 30ms</span></span>          |
|<span data-ttu-id="bcf72-123">**遅延 (RTT または往復時間)**</span><span class="sxs-lookup"><span data-stu-id="bcf72-123">**Latency (RTT or Round-trip Time)**</span></span> |<span data-ttu-id="bcf72-124">< 100 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="bcf72-124">< 100ms</span></span>         |<span data-ttu-id="bcf72-125">< 60 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="bcf72-125">< 60ms</span></span>         |
|<span data-ttu-id="bcf72-126">**バースト パケット損失**</span><span class="sxs-lookup"><span data-stu-id="bcf72-126">**Burst packet loss**</span></span>    |<span data-ttu-id="bcf72-127">< 任意の 200 ミリ秒間隔で 10%</span><span class="sxs-lookup"><span data-stu-id="bcf72-127"><10% during any 200ms interval</span></span>         |<span data-ttu-id="bcf72-128">< 任意の 200 ミリ秒間隔で 1%</span><span class="sxs-lookup"><span data-stu-id="bcf72-128"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="bcf72-129">**パケット損失**</span><span class="sxs-lookup"><span data-stu-id="bcf72-129">**Packet loss**</span></span>     |<span data-ttu-id="bcf72-130">< 任意の 15 秒間隔で 1%</span><span class="sxs-lookup"><span data-stu-id="bcf72-130"><1% during any 15s interval</span></span>          |<span data-ttu-id="bcf72-131">< 任意の 15 秒間隔で 0.1%</span><span class="sxs-lookup"><span data-stu-id="bcf72-131"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="bcf72-132">**パケット到着間ジッター**</span><span class="sxs-lookup"><span data-stu-id="bcf72-132">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="bcf72-133">< 15 秒間隔で 30 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="bcf72-133"><30ms during any 15s interval</span></span>         |<span data-ttu-id="bcf72-134">< 任意の 15 秒間隔で 15 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="bcf72-134"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="bcf72-135">**パケットの並べ替え**</span><span class="sxs-lookup"><span data-stu-id="bcf72-135">**Packet reorder**</span></span>    |<span data-ttu-id="bcf72-136">< 順序が適切でないパケットが 0.05%</span><span class="sxs-lookup"><span data-stu-id="bcf72-136"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="bcf72-137">< 順序が適切でないパケットが 0.01%</span><span class="sxs-lookup"><span data-stu-id="bcf72-137"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="bcf72-138">両方のネットワーク セグメントをテストするために、[Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799) を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="bcf72-138">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="bcf72-139">このツールは、クライアント PC に直接展開したり、Customer Network Edge に接続された PC に展開したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="bcf72-139">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="bcf72-140">ツールに含まれているドキュメントは限定的ですが、ツールの使用についてのより詳細なドキュメントは「[Network Readiness Assessment (ネットワークの準備状況の評価)](https://go.microsoft.com/fwlink/?linkid=855800)」にあります。</span><span class="sxs-lookup"><span data-stu-id="bcf72-140">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="bcf72-141">この Network Readiness Assessment を実行することによって、Microsoft Teams などのリアルタイム メディア アプリケーションを実行するためのネットワークの準備状況を検証することができます。</span><span class="sxs-lookup"><span data-stu-id="bcf72-141">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="bcf72-142">これは Skype for Business を展開するカスタマ向けに推奨される Network Readiness Assessment と同じです。</span><span class="sxs-lookup"><span data-stu-id="bcf72-142">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>

<a name="bandwidth-requirements"></a><span data-ttu-id="bcf72-143">帯域幅要件</span><span class="sxs-lookup"><span data-stu-id="bcf72-143">Bandwidth requirements</span></span>
----------

<span data-ttu-id="bcf72-144">Microsoft Teams の帯域幅の計算は複雑であるため、それを支援する計算ツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bcf72-144">Bandwidth calculations for Microsoft Teams are complex and to help with this, a calculator has been created.</span></span> <span data-ttu-id="bcf72-145">この計算ツールにアクセスするには、「[Network Planner in MyAdvisor (MyAdvisor での Network Planner)](https://aka.ms/bwcalc/)」に移動してください。</span><span class="sxs-lookup"><span data-stu-id="bcf72-145">To access the calculator, go to [Network Planner in MyAdvisor](https://aka.ms/bwcalc/).</span></span>

> [!NOTE]
> <span data-ttu-id="bcf72-146">チームの帯域幅の処理が Skype でオンライン ビジネスの向上: チームの呼び出しや、会議の経験 (オーディオ、ビデオ、および共有) は、高品質でのみ 1.2 Mbps が必要です。</span><span class="sxs-lookup"><span data-stu-id="bcf72-146">Teams bandwidth handling improves on Skype for Business Online: for a high quality calling or meeting experience (with audio, video, and sharing), Teams requires only 1.2 Mbps.</span></span> <span data-ttu-id="bcf72-147">拡張性にも十分な帯域幅が利用可能な場合に非常に高品質の最大さらにします。</span><span class="sxs-lookup"><span data-stu-id="bcf72-147">It can also scale up further for super high quality if there is enough available bandwidth.</span></span> <span data-ttu-id="bcf72-148">チームの要求には、低帯域幅の条件が検出されると、チームが迅速に再調整して、帯域幅の使用可能な帯域幅に適応します。</span><span class="sxs-lookup"><span data-stu-id="bcf72-148">When a Teams request encounters a low bandwidth condition, Teams can quickly readjust bandwidth usage to adapt to available bandwidth.</span></span>

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

<a name="additional-network-considerations"></a><span data-ttu-id="bcf72-149">ネットワークに関する追加の考慮事項</span><span class="sxs-lookup"><span data-stu-id="bcf72-149">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="bcf72-150">**外部の名前解決**</span><span class="sxs-lookup"><span data-stu-id="bcf72-150">**External Name Resolution**</span></span>

<span data-ttu-id="bcf72-151">Teams を実行するすべてのクライアント コンピュータが外部 DNS クエリを解決して、Office 365 によって提供されるサービスを検出できることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bcf72-151">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365.</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="bcf72-152">**NAT プール サイズ**</span><span class="sxs-lookup"><span data-stu-id="bcf72-152">**NAT Pool Size**</span></span>

<span data-ttu-id="bcf72-153">複数のユーザーまたはデバイスがネットワーク アドレス変換 (NAT) またはポート アドレス変換 (PAT) を使用して Office 365 にアクセスする場合は、パブリック ルーティング可能な各 IP アドレスの後ろに隠れているデバイスが、サポートされる数値を超過していないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcf72-153">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="bcf72-154">このリスクを軽減するには、適切なパブリック IP アドレスを NAT プールに割り当ててポート枯渇を回避します。</span><span class="sxs-lookup"><span data-stu-id="bcf72-154">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="bcf72-155">ポート枯渇は、Office 365 サービスに接続するときに発生するエンドユーザーやデバイスの問題の原因となります。</span><span class="sxs-lookup"><span data-stu-id="bcf72-155">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="bcf72-156">詳細については、「[Office 365 の NAT サポート](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9)」ガイドをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bcf72-156">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="bcf72-157">**侵入検知/防御のガイダンス**</span><span class="sxs-lookup"><span data-stu-id="bcf72-157">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="bcf72-158">送信接続の追加のセキュリティ レイヤとして環境に侵入検知/防御システム (IDS/IPS) が配備されている場合は、送信先から Office 365 URL へのトラフィックがホワイトリストに記載されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bcf72-158">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="bcf72-159">ネットワーク正常性の確認</span><span class="sxs-lookup"><span data-stu-id="bcf72-159">Network health determination</span></span>
-----------------

<span data-ttu-id="bcf72-160">ネットワーク内で Microsoft Teams を実装する計画を行う場合は、必要とされる帯域幅とすべての必須 IP アドレスへのアクセスを確保していること、正しいポートが開かれていること、リアルタイム メディアのパフォーマンス要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcf72-160">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="bcf72-161">これらの条件を満たすことができない場合は通話や会議中の品質が悪くなるため、エンドユーザーは Teams の最適なエクスペリエンスを得ることができません。</span><span class="sxs-lookup"><span data-stu-id="bcf72-161">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="bcf72-162">これらの要件を満たしていない場合は、先に進む前にプロジェクトを中断して、条件を満たすことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bcf72-162">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="bcf72-164">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="bcf72-164">Decision Point</span></span>         |<span data-ttu-id="bcf72-165">リアルタイム メディアをサポートするためにネットワーク能力を評価したことはありますか?</span><span class="sxs-lookup"><span data-stu-id="bcf72-165">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="bcf72-166">ネットワークが正しく評価されていない場合やリアルタイム メディアをサポートできないことが事前に分かっている場合は、ビデオや画面共有の機能を無効にして、ネットワークへの影響を軽減し、Teams エクスペリエンスの質を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="bcf72-166">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![次のステップ アイコン。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="bcf72-168">次のステップ</span><span class="sxs-lookup"><span data-stu-id="bcf72-168">Next Steps</span></span>         |<span data-ttu-id="bcf72-169">ネットワークの品質が不明な場合: [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) のガイダンスに従って、お客様のネットワークでリアルタイム メディアに対する準備が整っているかどうかを判別してください。</span><span class="sxs-lookup"><span data-stu-id="bcf72-169">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="bcf72-170">ネットワークの品質が乏しい場合: ネットワーク改善の手順を実行して、高品質なリアルタイム メディアに適した環境を整えてください。</span><span class="sxs-lookup"><span data-stu-id="bcf72-170">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="bcf72-171">十分なネットワーク品質: すべての IP アドレスやポートに正しくアクセスできることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bcf72-171">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

