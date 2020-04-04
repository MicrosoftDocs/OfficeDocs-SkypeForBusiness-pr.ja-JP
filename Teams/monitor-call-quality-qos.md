---
title: QoS の実装と通話分析の監視
author: dstrome
ms.author: dstrome
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: ''
description: '[QoS (Quality of Service)] の設定を使用して、Microsoft Teams で分析と通話品質ダッシュボードを呼び出します。'
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5ecf199f5027774684f5a626c416f789293926d7
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140056"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a><span data-ttu-id="791e5-103">Microsoft Teams で QoS を実装して通話品質を監視する</span><span class="sxs-lookup"><span data-stu-id="791e5-103">Implement QoS and Monitor Call Quality in Microsoft Teams</span></span>

## <a name="get-started"></a><span data-ttu-id="791e5-104">はじめに</span><span class="sxs-lookup"><span data-stu-id="791e5-104">Get Started</span></span>

<span data-ttu-id="791e5-105">ユーザーが Teams を使って電話をかけたり会議を開催したりするときに、発信者の声が出たり、通話または会議を chopping したりする場合があります。</span><span class="sxs-lookup"><span data-stu-id="791e5-105">As your users start using Teams for making calls and holding meetings, they may experience a caller's voice breaking up or chopping in and out of a call or meeting.</span></span> <span data-ttu-id="791e5-106">共有ビデオは、フリーズまたは pixelate、または完全に失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="791e5-106">Shared video may freeze or pixelate, or fail altogether.</span></span> <span data-ttu-id="791e5-107">これは、ネットワークの輻輳を示す音声とビデオのトラフィックを示す IP パケットによって、順番が正しく表示されない、またはまったく表示されないためです。</span><span class="sxs-lookup"><span data-stu-id="791e5-107">This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all.</span></span> <span data-ttu-id="791e5-108">このような問題を特定するには、主にサービス品質 (QoS) の利益を防ぐための方法があります。</span><span class="sxs-lookup"><span data-stu-id="791e5-108">There are ways to identify these problems when they surface and prevent their return, primarily Quality of Service (QoS).</span></span>

<span data-ttu-id="791e5-109">**QoS (Quality Of Service** ) は、ネットワークの遅延に敏感なトラフィック (音声やビデオストリームなど) を使用して、機密性の低いトラフィック (新しいアプリをダウンロードするなど) を使用して、重要度の低いネットワークトラフィック (ダウンロードするための追加機能は大きなものではありません) を可能にする方法です。</span><span class="sxs-lookup"><span data-stu-id="791e5-109">**Quality of Service (QoS)** is a way to allow real-time network traffic (like voice or video streams) that is sensitive to network delays to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="791e5-110">QoS は、Windows グループポリシーオブジェクトと、ポートベースのアクセス制御リストと呼ばれるルーティング機能を使用して、リアルタイムストリーム内のすべてのパケットを識別してマークします。これにより、ネットワークでは、音声、ビデオ、画面の共有をネットワーク帯域幅の専用部分で転送することができます。</span><span class="sxs-lookup"><span data-stu-id="791e5-110">QoS identifies and marks all packets in real-time streams using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, which then helps your network to give voice, video, and screen share streams their own dedicated portions of network bandwidth.</span></span>

 <span data-ttu-id="791e5-111">ここでは、メールを使用して手紙を送信する場合と同じように、郵送料金を送信した場合は、すぐにご利用いただけます。また、最初のクラスを送信した場合は、より高速になり、優先度の高いメールを送信すると、2日以内に送信されます。</span><span class="sxs-lookup"><span data-stu-id="791e5-111">For now, we'll just say that it's a lot like sending a letter through the mail: If you send it book rate it gets there pretty soon and that's good enough, if you send it first class it gets there a lot faster, and if you send it Priority Mail, it gets there within two days.</span></span> <span data-ttu-id="791e5-112">もちろん、ネットワークはメールよりも高速で実行されますが、一部のアプリケーションでは速度が重要であり、他のユーザーにとって重要ではないこともあります。</span><span class="sxs-lookup"><span data-stu-id="791e5-112">Of course networks run faster than the mail, but it still runs true that speed is critical for some applications and is not so critical for others.</span></span> <span data-ttu-id="791e5-113">この主題は、最初は理解しにくいものですが、ユーザーエクスペリエンスに大きな違いがあるため、時間と労力を事前に費やす価値があります。</span><span class="sxs-lookup"><span data-stu-id="791e5-113">This subject is inherently detailed and tricky to understand at first, but it makes a huge difference in the user experience so it's worth investing time and energy upfront.</span></span> <span data-ttu-id="791e5-114">詳細については、「 [Microsoft Teams でサービスの品質 (QoS) を実装する」](QoS-in-Teams.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="791e5-114">Read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md) for a more detailed discussion.</span></span>

<span data-ttu-id="791e5-115">理想的には、内部ネットワークで Teams をセットアップするときに、QoS を実装することをお勧めしますが、小さなサイズの場合はオプションでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="791e5-115">Ideally you would implement QoS on your internal network while setting up Teams, but if you're small enough it can be optional.</span></span> <span data-ttu-id="791e5-116">これにより、遅延に敏感な音声とビデオのトラフィックが、他のトラフィックの優先順位を取得できます。</span><span class="sxs-lookup"><span data-stu-id="791e5-116">This allows the delay-sensitive voice and video traffic to get prioritized ahead of other traffic.</span></span> <span data-ttu-id="791e5-117">この優先順位付けは、 [Microsoft Teams 管理センター](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)のすべての[クライアントデバイス](QoS-in-Teams-clients.md)、およびネットワーク内のスイッチとルーターに対して行います。</span><span class="sxs-lookup"><span data-stu-id="791e5-117">You'd do this prioritization on all the [client devices](QoS-in-Teams-clients.md), in the [Microsoft Teams admin center](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings), as well as on the switches and routers in your network.</span></span>

<span data-ttu-id="791e5-118">[**通話分析と通話品質ダッシュボード**](difference-between-call-analytics-and-call-quality-dashboard.md)を使用して、進行中の操作中に発生する問題の検出とトラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="791e5-118">[**Call Analytics and Call Quality Dashboard**](difference-between-call-analytics-and-call-quality-dashboard.md) are used to find and troubleshoot problems that come up during ongoing operation.</span></span>  

<span data-ttu-id="791e5-119">[**通話分析**] には、Microsoft Teams または Skype for business アカウントの各ユーザーの***特定の通話と会議***に関連するデバイス、ネットワーク、接続に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="791e5-119">**Call Analytics** shows detailed information about the devices, networks, and connectivity related to  ***specific calls and meetings*** for each user in a Microsoft Teams or Skype for Business account.</span></span> <span data-ttu-id="791e5-120">Office 365 管理者の場合は、通話分析を使用して、特定の通話で発生した通話品質や接続の問題のトラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="791e5-120">If you're an Office 365 admin, you can use Call Analytics to troubleshoot call quality and connection problems experienced in a specific call.</span></span> <span data-ttu-id="791e5-121">これは、問題を特定して解決するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="791e5-121">This can help you to identify and eliminate problems.</span></span>

<span data-ttu-id="791e5-122">**通話品質ダッシュボード (CQD)** は、管理者とネットワークエンジニアが1回の通話の分析とトラブルシューティングを行わずに、***ネットワーク***を最適化するために設計されています。</span><span class="sxs-lookup"><span data-stu-id="791e5-122">**Call Quality Dashboard (CQD)** is designed to help admins and network engineers optimize their ***network***, not analyze and troubleshoot a single call.</span></span> <span data-ttu-id="791e5-123">CQD は、特定のユーザーからフォーカスを移動して、組織全体の集計情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="791e5-123">CQD shifts focus from specific users to look at aggregated information for an entire organization.</span></span> <span data-ttu-id="791e5-124">これは、問題を特定して解決するのにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="791e5-124">This can also help you to identify and eliminate problems.</span></span>

## <a name="related-topics"></a><span data-ttu-id="791e5-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="791e5-125">Related Topics</span></span>

[<span data-ttu-id="791e5-126">Microsoft Teams でサービスの品質 (QoS) を実装する</span><span class="sxs-lookup"><span data-stu-id="791e5-126">Implement Quality of Service (QoS) in Microsoft Teams</span></span>](QoS-in-Teams.md)

[<span data-ttu-id="791e5-127">ビデオ: 通話品質の概要</span><span class="sxs-lookup"><span data-stu-id="791e5-127">Video: Call Quality Overview</span></span>](https://aka.ms/teams-quality)

[<span data-ttu-id="791e5-128">通話分析をセットアップする</span><span class="sxs-lookup"><span data-stu-id="791e5-128">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="791e5-129">通話分析を使用して低品質の通話をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="791e5-129">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="791e5-130">通話品質ダッシュボードをオンにして使用する</span><span class="sxs-lookup"><span data-stu-id="791e5-130">Turning on and using Call Quality Dashboard</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="791e5-131">通話品質ダッシュボードで利用できるディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="791e5-131">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="791e5-132">通話品質ダッシュボードでのストリームの分類</span><span class="sxs-lookup"><span data-stu-id="791e5-132">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)