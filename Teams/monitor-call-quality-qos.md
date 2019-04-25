---
title: Microsoft Teams で QoS を実施し、通話分析を監視する
author: jambirk
ms.author: jambirk
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jambirk
description: マイクロソフトのチームでは、サービスの品質 (QoS) 設定を呼び出して分析し、品質のダッシュ ボードを呼び出すを使用します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77730db17e900951f0fe1a60b7c0ae2ccdbfbc5b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32228424"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a><span data-ttu-id="ef9bc-103">マイクロソフトのチームで QoS と通話品質の監視を実装します。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-103">Implement QoS and Monitor Call Quality in Microsoft Teams</span></span>

## <a name="get-started"></a><span data-ttu-id="ef9bc-104">開始します。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-104">Get Started</span></span>

<span data-ttu-id="ef9bc-105">ユーザーでは、呼び出しを実行すると、会議を保持しているチームを使用を開始するように分割することまたは呼び出しとの間で切る、または会議の呼び出し元の音声が発生した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-105">As your users start using Teams for making calls and holding meetings, they may experience a caller's voice breaking up or chopping in and out of a call or meeting.</span></span> <span data-ttu-id="ef9bc-106">共有ビデオがフリーズまたはモザイク、全体が失敗するか。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-106">Shared video may freeze or pixelate, or fail altogether.</span></span> <span data-ttu-id="ef9bc-107">IP パケットを音声とビデオのトラフィックがネットワークの輻輳が発生して、順序に関係なく、あるいはまったくの到着を表すためです。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-107">This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all.</span></span> <span data-ttu-id="ef9bc-108">表面化し、リターンでは、主にサービスの品質 (QoS) を防ぐためにこれらの問題を識別する方法もあります。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-108">There are ways to identify these problems when they surface and prevent their return, primarily Quality of Service (QoS).</span></span>

<span data-ttu-id="ef9bc-109">カット ラインでは、(場所をダウンロードするのには追加の 2 番目に、新しいアプリケーションをダウンロードするなど重要度の低いトラフィックの前にするにはネットワークの遅延に敏感である (音声またはビデオのストリーム) のようなリアルタイムのネットワーク トラフィックを許可する方法は、**サービスの品質 (QoS)** 大きな問題はありません)。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-109">**Quality of Service (QoS)** is a way to allow real-time network traffic (like voice or video streams) that is sensitive to network delays to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="ef9bc-110">ポート ベースのアクセス制御リスト、音声、ビデオ、および画面共有を提供するネットワークを利用すると呼ばれるルーティング機能の独自の専用部分のストリームと QoS を識別し、Windows グループ ポリシー オブジェクトを使用してリアルタイムのストリーム内のすべてのパケットをマークネットワークの帯域幅です。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-110">QoS identifies and marks all packets in real-time streams using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, which then helps your network to give voice, video, and screen share streams their own dedicated portions of network bandwidth.</span></span>

 <span data-ttu-id="ef9bc-111">こことだけ言っておきますである多くの mail を使用して文字を送信するように: 送信する、本レートが届いてすぐと取得がはるかに速く、最初のクラスを送信する場合、および優先度のメールを送信する場合に十分であります。、2 日以内に到達します。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-111">For now, we'll just say that it's a lot like sending a letter through the mail: If you send it book rate it gets there pretty soon and that's good enough, if you send it first class it gets there a lot faster, and if you send it Priority Mail, it gets there within two days.</span></span> <span data-ttu-id="ef9bc-112">ネットワークがコースのメールよりも高速に実行しますが、それはそのまま実行速度が一部のアプリケーションにとって重要で、他のユーザーのために重要ではない場合は true。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-112">Of course networks run faster than the mail, but it still runs true that speed is critical for some applications and is not so critical for others.</span></span> <span data-ttu-id="ef9bc-113">このトピックは、本質的に詳細な最初は、理解するのには注意が必要ですが発生するので、ユーザーに大きな違いは、時間とエネルギーをあらかじめへの投資価値があります。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-113">This subject is inherently detailed and tricky to understand at first, but it makes a huge difference in the user experience so it's worth investing time and energy upfront.</span></span> <span data-ttu-id="ef9bc-114">については詳細な[実装のサービス品質 (QoS) では、マイクロソフトのチーム](QoS-in-Teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-114">Read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md) for a more detailed discussion.</span></span>

<span data-ttu-id="ef9bc-115">チームは、セットアップ中に内部ネットワークの QoS を実装する理想的ですが、小さい場合は、十分なことができますオプション。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-115">Ideally you would implement QoS on your internal network while setting up Teams, but if you're small enough it can be optional.</span></span> <span data-ttu-id="ef9bc-116">これにより、遅延に依存した音声とビデオのトラフィックを他のトラフィックよりも優先順位を取得します。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-116">This allows the delay-sensitive voice and video traffic to get prioritized ahead of other traffic.</span></span> <span data-ttu-id="ef9bc-117">ネットワークですべての[クライアント デバイス](QoS-in-Teams-clients.md)スイッチとルーターだけでなく、[マイクロソフトのチーム管理センター](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)ではこの優先順位付けの操作とします。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-117">You'd do this prioritization on all the [client devices](QoS-in-Teams-clients.md), in the [Microsoft Teams admin center](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings), as well as on the switches and routers in your network.</span></span>

<span data-ttu-id="ef9bc-118">検索し、実行中の操作で発生する問題のトラブルシューティングを行うには、[**分析機能の呼び出しと呼び出し品質のダッシュ ボード**](difference-between-call-analytics-and-call-quality-dashboard.md)が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-118">[**Call Analytics and Call Quality Dashboard**](difference-between-call-analytics-and-call-quality-dashboard.md) are used to find and troubleshoot problems that come up during ongoing operation.</span></span>  

<span data-ttu-id="ef9bc-119">**分析機能を呼び出す**には、デバイス、ネットワーク、およびに関連する***特定の通話や会議***ユーザーごとに、マイクロソフトのチームまたは Skype ビジネス アカウントの接続に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-119">**Call Analytics** shows detailed information about the devices, networks, and connectivity related to  ***specific calls and meetings*** for each user in a Microsoft Teams or Skype for Business account.</span></span> <span data-ttu-id="ef9bc-120">Office 365 管理者の場合、特定の呼び出しで発生した通話品質と接続の問題をトラブルシューティングする分析機能の呼び出しを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-120">If you're an Office 365 admin, you can use Call Analytics to troubleshoot call quality and connection problems experienced in a specific call.</span></span> <span data-ttu-id="ef9bc-121">識別し、問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-121">This can help you to identify and eliminate problems.</span></span>

<span data-ttu-id="ef9bc-122">**呼び出し品質ダッシュ ボード (救難)** は、管理者を支援するように設計されていて、ネットワーク エンジニア、***ネットワーク***を最適化、解析されず、1 回の呼び出しのトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-122">**Call Quality Dashboard (CQD)** is designed to help admins and network engineers optimize their ***network***, not analyze and troubleshoot a single call.</span></span> <span data-ttu-id="ef9bc-123">救難は、組織全体の集計情報を確認するのには特定のユーザーからフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-123">CQD shifts focus from specific users to look at aggregated information for an entire organization.</span></span> <span data-ttu-id="ef9bc-124">これは、こともできますを特定して問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-124">This can also help you to identify and eliminate problems.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ef9bc-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef9bc-125">Related Topics</span></span>

[<span data-ttu-id="ef9bc-126">マイクロソフトのチームでのサービス品質 (QoS) を実装します。</span><span class="sxs-lookup"><span data-stu-id="ef9bc-126">Implement Quality of Service (QoS) in Microsoft Teams</span></span>](QoS-in-Teams.md)

[<span data-ttu-id="ef9bc-127">ビデオ: 通話品質の概要</span><span class="sxs-lookup"><span data-stu-id="ef9bc-127">Video: Call Quality Overview</span></span>](https://aka.ms/teams-quality)

[<span data-ttu-id="ef9bc-128">通話分析をセットアップする</span><span class="sxs-lookup"><span data-stu-id="ef9bc-128">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="ef9bc-129">通話分析を使用して低品質の通話をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="ef9bc-129">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="ef9bc-130">通話品質ダッシュボードをオンにして使用する</span><span class="sxs-lookup"><span data-stu-id="ef9bc-130">Turning on and using Call Quality Dashboard</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="ef9bc-131">通話品質ダッシュボードで利用できるディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="ef9bc-131">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="ef9bc-132">通話品質ダッシュボードでのストリームの分類</span><span class="sxs-lookup"><span data-stu-id="ef9bc-132">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)