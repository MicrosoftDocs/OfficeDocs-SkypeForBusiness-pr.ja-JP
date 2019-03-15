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
ms.openlocfilehash: 57f8ffc7d5cedeb6117deffb99ad48ccbe17b48f
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640731"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="b0c84-104">Microsoft Teams 用に組織のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="b0c84-104">Prepare your organization's network for Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="b0c84-105">については、次のセッションを監視するチームをするための方法、ネットワークとの最適なネットワーク接続の最適な計画を立てる方法を活用:[チーム ネットワークの計画](https://aka.ms/teams-networking)</span><span class="sxs-lookup"><span data-stu-id="b0c84-105">Watch the following session to learn how to Teams leverages your network and how to best plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking)</span></span>


<span data-ttu-id="b0c84-106">チームでは、トラフィックの 3 つのフォームを結合します。</span><span class="sxs-lookup"><span data-stu-id="b0c84-106">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="b0c84-107">データ トラフィックは、Office 365 のオンライン環境とクライアントの間のチーム (信号、プレゼンス、チャット、ファイルのアップロードとダウンロード、OneNote の同期)。</span><span class="sxs-lookup"><span data-stu-id="b0c84-107">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="b0c84-108">ピア ツー ピアのリアルタイム通信トラフィックが (オーディオ、ビデオ、デスクトップの共有)。</span><span class="sxs-lookup"><span data-stu-id="b0c84-108">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="b0c84-109">会議のリアルタイム通信トラフィックが (オーディオ、ビデオ、デスクトップの共有)。</span><span class="sxs-lookup"><span data-stu-id="b0c84-109">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="b0c84-110">これは、2 つのレベル上のネットワークに影響を与える: ピア ツー ピアのシナリオを直接マイクロソフトのチームのクライアント間でトラフィック フローし、トラフィックがマイクロソフト チーム クライアントと Office 365 環境の間のシナリオを満たすためです。</span><span class="sxs-lookup"><span data-stu-id="b0c84-110">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios.</span></span> <span data-ttu-id="b0c84-111">両方 (たとえば、WAN 経由でサイト) 間の内部ネットワークのセグメントの間に間でフローを許可するトラフィックに最適なトラフィックのフローを確認するには、ネットワーク サイトと Office 365。</span><span class="sxs-lookup"><span data-stu-id="b0c84-111">To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365.</span></span> <span data-ttu-id="b0c84-112">正しいポートを開くか、積極的に特定のポートをブロックしないと、劣化した経験です。</span><span class="sxs-lookup"><span data-stu-id="b0c84-112">Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="b0c84-113">会議は、iOS および Android モバイル デバイスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b0c84-113">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="b0c84-114">マイクロソフトのチーム内でのリアルタイム メディアに最適なエクスペリエンスを得るには、ネットワークは、Office 365 のネットワーク要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0c84-114">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="b0c84-115">詳細については、[メディアの品質とビジネス オンラインの Skype のネットワーク接続のパフォーマンス](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c84-115">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="b0c84-116">2 つ定義するネットワーク セグメント (マイクロソフトのエッジにクライアント) およびマイクロソフトのエッジにエッジを顧客、次の推奨事項を検討してください。</span><span class="sxs-lookup"><span data-stu-id="b0c84-116">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="b0c84-117">値</span><span class="sxs-lookup"><span data-stu-id="b0c84-117">Value</span></span>  |<span data-ttu-id="b0c84-118">クライアントはマイクロソフトのエッジ</span><span class="sxs-lookup"><span data-stu-id="b0c84-118">Client to Microsoft Edge</span></span>  |<span data-ttu-id="b0c84-119">マイクロソフトのエッジにエッジを顧客</span><span class="sxs-lookup"><span data-stu-id="b0c84-119">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="b0c84-120">**待機時間 (1 つの方法)**\*</span><span class="sxs-lookup"><span data-stu-id="b0c84-120">**Latency (one way)** \*</span></span>  |<span data-ttu-id="b0c84-121">_lt _ 往復</span><span class="sxs-lookup"><span data-stu-id="b0c84-121">< 50ms</span></span>          |<span data-ttu-id="b0c84-122">_lt _ 30ms</span><span class="sxs-lookup"><span data-stu-id="b0c84-122">< 30ms</span></span>         |
|<span data-ttu-id="b0c84-123">**RTT (ラウンドト リップ時間) の待機時間**\*</span><span class="sxs-lookup"><span data-stu-id="b0c84-123">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="b0c84-124">_lt _ 100 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="b0c84-124">< 100ms</span></span>   |<span data-ttu-id="b0c84-125">_lt _ 60 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="b0c84-125">< 60ms</span></span> |
|<span data-ttu-id="b0c84-126">**バースト パケット ロス**</span><span class="sxs-lookup"><span data-stu-id="b0c84-126">**Burst packet loss**</span></span>    |<span data-ttu-id="b0c84-127">200 ミリ秒間隔で <10%</span><span class="sxs-lookup"><span data-stu-id="b0c84-127"><10% during any 200ms interval</span></span>         |<span data-ttu-id="b0c84-128">200 ミリ秒間隔で <1%</span><span class="sxs-lookup"><span data-stu-id="b0c84-128"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="b0c84-129">**パケット損失**</span><span class="sxs-lookup"><span data-stu-id="b0c84-129">**Packet loss**</span></span>     |<span data-ttu-id="b0c84-130">任意の 15 秒間 <1% の間隔</span><span class="sxs-lookup"><span data-stu-id="b0c84-130"><1% during any 15s interval</span></span>          |<span data-ttu-id="b0c84-131"><0.1%、15 秒間の間隔</span><span class="sxs-lookup"><span data-stu-id="b0c84-131"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="b0c84-132">**パケット間到着ジッタ**</span><span class="sxs-lookup"><span data-stu-id="b0c84-132">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="b0c84-133"><30ms、15 秒間の間隔</span><span class="sxs-lookup"><span data-stu-id="b0c84-133"><30ms during any 15s interval</span></span>         |<span data-ttu-id="b0c84-134"><15ms、15 秒間の間隔</span><span class="sxs-lookup"><span data-stu-id="b0c84-134"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="b0c84-135">**パケット順序の変更**</span><span class="sxs-lookup"><span data-stu-id="b0c84-135">**Packet reorder**</span></span>    |<span data-ttu-id="b0c84-136"><0.05% 不適切な順序のパケット</span><span class="sxs-lookup"><span data-stu-id="b0c84-136"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="b0c84-137"><0.01% 不適切な順序のパケット</span><span class="sxs-lookup"><span data-stu-id="b0c84-137"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="b0c84-138">\*遅延のメトリック ターゲットは、会社のサイトまたはサイトを想定し、同じ大陸には、マイクロソフトのエッジ。</span><span class="sxs-lookup"><span data-stu-id="b0c84-138">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="b0c84-139">Microsoft ネットワークのエッジに、企業サイトの接続には、WiFi または他のワイヤレス技術は、最初のホップ ネットワーク アクセスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b0c84-139">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="b0c84-140">ネットワーク パフォーマンスの目標は、適切な帯域幅と[QoS の計画](QoS-in-Teams.md)と仮定します。</span><span class="sxs-lookup"><span data-stu-id="b0c84-140">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="b0c84-141">つまり、要件は、ピーク負荷の下では、ネットワーク接続とチーム リアルタイム メディアのトラフィックを直接適用されます。</span><span class="sxs-lookup"><span data-stu-id="b0c84-141">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="b0c84-142">両方のネットワーク セグメントをテストするには、[ネットワーク評価ツール](https://go.microsoft.com/fwlink/?linkid=855799)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0c84-142">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="b0c84-143">直接およびお客様のネットワークのエッジに接続されている PC では、両方のクライアント コンピューターでこのツールを展開できます。</span><span class="sxs-lookup"><span data-stu-id="b0c84-143">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="b0c84-144">ツールには、制限付きのマニュアルが含まれていますが、ツールの使用方法をより深いレベルのマニュアルを参照してください:[ネットワーク対応の評価](https://go.microsoft.com/fwlink/?linkid=855800)。</span><span class="sxs-lookup"><span data-stu-id="b0c84-144">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="b0c84-145">このネットワーク対応の評価を実行すると、マイクロソフトのチームなどのリアルタイム メディアのアプリケーションを実行するのには、ネットワークの準備を検証できます。</span><span class="sxs-lookup"><span data-stu-id="b0c84-145">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="b0c84-146">これは、ビジネス用の Skype を正常に展開しているお客様向けの実行に推奨されている同じネットワーク対応の評価です。</span><span class="sxs-lookup"><span data-stu-id="b0c84-146">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="b0c84-147">帯域幅の要件</span><span class="sxs-lookup"><span data-stu-id="b0c84-147">Bandwidth requirements</span></span>

<span data-ttu-id="b0c84-148">マイクロソフト チームの帯域幅の計算は複雑で、これを支援するため、電卓が作成されました。</span><span class="sxs-lookup"><span data-stu-id="b0c84-148">Bandwidth calculations for Microsoft Teams are complex and to help with this, a calculator has been created.</span></span> <span data-ttu-id="b0c84-149">計算機にアクセスするには、MyAdvisor では、[ネットワークの計画](https://aka.ms/bwcalc/)に移動します。</span><span class="sxs-lookup"><span data-stu-id="b0c84-149">To access the calculator, go to [Network Planner](https://aka.ms/bwcalc/)  in MyAdvisor.</span></span>

> [!NOTE]
> <span data-ttu-id="b0c84-150">チームの帯域幅の処理が Skype でオンライン ビジネスの向上: チームの呼び出しや、会議の経験 (オーディオ、ビデオ、および共有) は、高品質でのみ 1.2 Mbps が必要です。</span><span class="sxs-lookup"><span data-stu-id="b0c84-150">Teams bandwidth handling improves on Skype for Business Online: for a high quality calling or meeting experience (with audio, video, and sharing), Teams requires only 1.2 Mbps.</span></span> <span data-ttu-id="b0c84-151">拡張性にも十分な帯域幅が利用可能な場合に非常に高品質の最大さらにします。</span><span class="sxs-lookup"><span data-stu-id="b0c84-151">It can also scale up further for super high quality if there is enough available bandwidth.</span></span> <span data-ttu-id="b0c84-152">チームの要求には、低帯域幅の条件が検出されると、チームが迅速に再調整して、帯域幅の使用可能な帯域幅に適応します。</span><span class="sxs-lookup"><span data-stu-id="b0c84-152">When a Teams request encounters a low bandwidth condition, Teams can quickly readjust bandwidth usage to adapt to available bandwidth.</span></span>

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

<a name="additional-network-considerations"></a><span data-ttu-id="b0c84-153">追加のネットワークに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="b0c84-153">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="b0c84-154">外部の名前解決</span><span class="sxs-lookup"><span data-stu-id="b0c84-154">External Name Resolution</span></span>

<span data-ttu-id="b0c84-155">チームのクライアントを実行するすべてのクライアント コンピューターで、Office 365 が提供するサービスを検出するのには外部の DNS クエリを解決できることと、ファイアウォールがアクセスを遮断していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0c84-155">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="b0c84-156">ファイアウォール ポートを構成する方法の詳細については、 [Office 365 の Url と IP の範囲](office-365-urls-ip-address-ranges.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c84-156">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="b0c84-157">NAT プール サイズ</span><span class="sxs-lookup"><span data-stu-id="b0c84-157">NAT Pool Size</span></span>

<span data-ttu-id="b0c84-158">複数のユーザーとデバイスは、ネットワーク アドレス変換 (NAT) またはポート アドレス変換 (PAT) を使用して Office 365 にアクセスするときは、公的にルーティング可能な各 IP アドレスの背後にある非表示のデバイスがサポートされている数を超えていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0c84-158">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="b0c84-159">このリスクを軽減するには、ポートの枯渇を防ぐために適切なパブリック IP アドレスが NAT プールに割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0c84-159">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="b0c84-160">ポートの消費と、内部のエンド ・ ユーザーとデバイスは、Office 365 サービスに接続するときの問題に直面します。</span><span class="sxs-lookup"><span data-stu-id="b0c84-160">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="b0c84-161">詳細については、 [NAT は、Office 365 のサポート](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0c84-161">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="b0c84-162">**侵入検知と防止の手引き**</span><span class="sxs-lookup"><span data-stu-id="b0c84-162">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="b0c84-163">お客様の環境が、侵入検知および防止システム (IDS/IPS) の送信接続のセキュリティの追加レイヤーとして配置されている場合、Office 365 の Url へのリンク先をすべてのトラフィックが whitelisted ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0c84-163">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="b0c84-164">ネットワーク正常性の決定</span><span class="sxs-lookup"><span data-stu-id="b0c84-164">Network health determination</span></span>
-----------------

<span data-ttu-id="b0c84-165">マイクロソフト チームのネットワーク内での実装を計画するときことを必要な帯域幅がある場合、すべて必須の IP アドレスを開くと、適切なポートへのアクセスがあり、リアルタイム メディアのパフォーマンス要件を達成します。.</span><span class="sxs-lookup"><span data-stu-id="b0c84-165">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="b0c84-166">これらの条件に適合していない場合は、エンド ・ ユーザーは表示されません最適なエクスペリエンス チームから品質が悪いため通話や会議中に。</span><span class="sxs-lookup"><span data-stu-id="b0c84-166">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="b0c84-167">いないこれらの条件を満たす必要があります、これは、時間を続行する前に、条件を満たしていることを確認するプロジェクトを一時停止を検討してください。</span><span class="sxs-lookup"><span data-stu-id="b0c84-167">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![判断ポイント アイコン。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="b0c84-169">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="b0c84-169">Decision Point</span></span>         |<span data-ttu-id="b0c84-170">リアルタイム メディアをサポートするため、ネットワークの機能を評価するでしょうか。</span><span class="sxs-lookup"><span data-stu-id="b0c84-170">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="b0c84-171">ネットワークが適切に評価されていない、またはリアルタイム メディアができないことがわかって、無効にしてもビデオと画面の共有ネットワークへの影響とチーム エクスペリエンスの低下を軽減する機能ですか。</span><span class="sxs-lookup"><span data-stu-id="b0c84-171">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![次のステップ アイコン。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="b0c84-173">次のステップ</span><span class="sxs-lookup"><span data-stu-id="b0c84-173">Next Steps</span></span>         |<span data-ttu-id="b0c84-174">ネットワーク品質不明: ネットワークのリアルタイム メディアの準備ができたかを判断するのには[ネットワーク対応の評価](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="b0c84-174">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="b0c84-175">ネットワークの品質が低下します。 は、高品質リアルタイム メディアの適切な環境を提供するネットワークの改善手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b0c84-175">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="b0c84-176">ネットワーク満足: は、すべての IP アドレスとポートが正しくアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b0c84-176">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="b0c84-177">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b0c84-177">Related Topics</span></span>

[<span data-ttu-id="b0c84-178">ビデオ: ネットワークの計画</span><span class="sxs-lookup"><span data-stu-id="b0c84-178">Video: Network Planning</span></span>](https://aka.ms/teams-networking)