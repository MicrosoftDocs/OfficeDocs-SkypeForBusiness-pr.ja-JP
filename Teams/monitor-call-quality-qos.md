---
title: マイクロソフトのチームで QoS とモニターの呼び出しの分析機能を実装します。
author: jambirk
ms.author: MyAdvisor
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jambirk
description: マイクロソフトのチームでは、サービスの品質 (QoS) 設定を呼び出して分析し、品質のダッシュ ボードを呼び出すを使用します。
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: d0f82a546057558cc6c69c9c0de19bc9ccb021cd
ms.sourcegitcommit: 788e3526ff973454f3904c33d867691a2fae814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "28328177"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a><span data-ttu-id="16eb5-103">マイクロソフトのチームで QoS と通話品質の監視を実装します。</span><span class="sxs-lookup"><span data-stu-id="16eb5-103">Implement QoS and Monitor Call Quality in Microsoft Teams</span></span>

## <a name="get-started"></a><span data-ttu-id="16eb5-104">開始します。</span><span class="sxs-lookup"><span data-stu-id="16eb5-104">Get Started</span></span>

<span data-ttu-id="16eb5-105">ユーザーでは、呼び出しを実行すると、会議を保持しているチームを使用を開始するに気付く場合がありますスピーカー点の ups または会議との間で切るか。</span><span class="sxs-lookup"><span data-stu-id="16eb5-105">As your users start using Teams for making calls and holding meetings, they may find speakers breaking ups or chopping in and out of a call or meeting.</span></span> <span data-ttu-id="16eb5-106">共有ビデオがフリーズまたは pixellate、または完全に失敗します。</span><span class="sxs-lookup"><span data-stu-id="16eb5-106">Shared video may freeze or pixellate, or fail altogether.</span></span> <span data-ttu-id="16eb5-107">IP パケットを音声とビデオのトラフィックがネットワークの輻輳が発生して、順序に関係なく、あるいはまったくの到着を表すためです。</span><span class="sxs-lookup"><span data-stu-id="16eb5-107">This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all.</span></span> <span data-ttu-id="16eb5-108">これを防止し、それらが表面化、主にサービスの品質 (QoS) とは、他の問題を特定する方法もあります。</span><span class="sxs-lookup"><span data-stu-id="16eb5-108">There are ways to prevent this and identify other problems when they surface, primarily Quality of Service (QoS).</span></span>

<span data-ttu-id="16eb5-109">[**サービスの品質 (QoS)**](monitor-call-quality-qos.md)は、パケットの遅延や輻輳、影響を特定し、はるかに少ない輻輳が発生したために優先的な処置を持つパケットを提供する方法です。</span><span class="sxs-lookup"><span data-stu-id="16eb5-109">[**Quality of Service (QoS)**](monitor-call-quality-qos.md)  is a way to identify packets that are sensitive to delays and congestion, and then provide the packets with preferential treatment so they encounter far less congestion.</span></span> <span data-ttu-id="16eb5-110">こことだけ言っておきますである多くの Mail を使用して文字を送信するように: 送信する、本レートが届いてすぐと取得がはるかに速く、最初のクラスを送信する場合、および優先度のメールを送信する場合に十分であります。、2 日以内に到達します。</span><span class="sxs-lookup"><span data-stu-id="16eb5-110">For now, we'll just say that it's a lot like sending a letter through the Mail: If you send it book rate it gets there pretty soon and that's good enough, if you send it first class it gets there a lot faster, and if you send it Priority Mail, it gets there within two days.</span></span> <span data-ttu-id="16eb5-111">ネットワークがコースのメールよりも高速に実行しますが、それはそのまま実行速度が一部のアプリケーションにとって重要で、他のユーザーのために重要ではない場合は true。</span><span class="sxs-lookup"><span data-stu-id="16eb5-111">Of course networks run faster than the mail, but it still runs true that speed is critical for some applications and is not so critical for others.</span></span> <span data-ttu-id="16eb5-112">このトピックは、本質的に詳細な最初は、理解するのには注意が必要ですが発生するので、ユーザーに大きな違いは、時間とエネルギーをあらかじめへの投資価値があります。</span><span class="sxs-lookup"><span data-stu-id="16eb5-112">This subject is inherently detailed and tricky to understand at first, but it makes a huge difference in the user experience so it's worth investing time and energy upfront.</span></span>

<span data-ttu-id="16eb5-113">チームは、セットアップ中に内部ネットワークの QoS を実装する理想的ですが、小さい場合は、十分なことができますオプション。</span><span class="sxs-lookup"><span data-stu-id="16eb5-113">Ideally you would implement QoS on your internal network while setting up Teams, but if you're small enough it can be optional.</span></span> <span data-ttu-id="16eb5-114">これにより、遅延に依存した音声とビデオのトラフィックを他のトラフィックよりも優先順位を取得します。</span><span class="sxs-lookup"><span data-stu-id="16eb5-114">This allows the delay-sensitive voice and video traffic to get prioritized ahead of other traffic.</span></span> <span data-ttu-id="16eb5-115">ネットワーク内およびスイッチとルーターで、すべてのクライアント デバイスでは、この優先順位付けを行うと。</span><span class="sxs-lookup"><span data-stu-id="16eb5-115">You'd do this prioritization on all the client devices, as well as on the switches and routers in your network.</span></span>

<span data-ttu-id="16eb5-116">検索し、実行中の操作で発生する問題のトラブルシューティングを行うには、[**分析機能の呼び出しと呼び出し品質のダッシュ ボード**](difference-between-call-analytics-and-call-quality-dashboard.md)が使用されます。</span><span class="sxs-lookup"><span data-stu-id="16eb5-116">[**Call Analytics and Call Quality Dashboard**](difference-between-call-analytics-and-call-quality-dashboard.md) are used to find and troubleshoot problems that come up during ongoing operation.</span></span>  

<span data-ttu-id="16eb5-117">分析機能の呼び出しは、デバイス、ネットワーク、および特定のコールとビジネス アカウントに、マイクロソフトのチームまたは Skype では、各ユーザーが会議に関連する接続に関する詳細情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="16eb5-117">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user in a Microsoft Teams or Skype for Business account.</span></span> <span data-ttu-id="16eb5-118">Office 365 管理者の場合、特定の呼び出しで発生した通話品質と接続の問題をトラブルシューティングする分析機能の呼び出しを使用できます。</span><span class="sxs-lookup"><span data-stu-id="16eb5-118">If you're an Office 365 admin, you can use Call Analytics to troubleshoot call quality and connection problems experienced in a specific call.</span></span> <span data-ttu-id="16eb5-119">識別し、問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="16eb5-119">This can help you to identify and eliminate problems.</span></span>

<span data-ttu-id="16eb5-120">通話品質ダッシュ ボード (救難) は、管理者を支援するように設計されていますおよびネットワーク ・ エンジニアの**ネットワーク**を最適化、分析されず、1 回の呼び出しのトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="16eb5-120">Call Quality Dashboard (CQD) is designed to help admins and network engineers optimize a **network**, not analyze and troubleshoot a single call.</span></span> <span data-ttu-id="16eb5-121">救難は、組織全体の集計情報を確認するのには特定のユーザーからフォーカスを移動します。</span><span class="sxs-lookup"><span data-stu-id="16eb5-121">CQD shifts focus from specific users to look at aggregated information for an entire organization.</span></span> <span data-ttu-id="16eb5-122">これは、こともできますを特定して問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="16eb5-122">This can also help you to identify and eliminate problems.</span></span>

## <a name="related-topics"></a><span data-ttu-id="16eb5-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="16eb5-123">Related Topics</span></span>

[<span data-ttu-id="16eb5-124">マイクロソフトのチームに QoS を実装します。</span><span class="sxs-lookup"><span data-stu-id="16eb5-124">Implement QoS for Microsoft Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="16eb5-125">分析機能の呼び出しを設定します</span><span class="sxs-lookup"><span data-stu-id="16eb5-125">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="16eb5-126">通話分析を使用して低い通話品質をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="16eb5-126">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="16eb5-127">有効にして、品質のダッシュ ボードの呼び出しを使用します。</span><span class="sxs-lookup"><span data-stu-id="16eb5-127">Turning on and using Call Quality Dashboard </span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="16eb5-128">通話品質ダッシュボードで利用できるディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="16eb5-128">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="16eb5-129">通話品質ダッシュボードでのストリーム分類</span><span class="sxs-lookup"><span data-stu-id="16eb5-129">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)