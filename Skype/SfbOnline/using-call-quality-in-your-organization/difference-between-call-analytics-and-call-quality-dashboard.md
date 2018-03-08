---
title: "通話の分析手法と通話品質のダッシュ ボードの違いは何ですか。"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: "分析を呼び出すと通話品質のダッシュ ボードを監視し、Skype for Business で通話品質の問題のトラブルシューティングに使用する場合について説明します。"
ms.openlocfilehash: a17b98451013f24810fd437fa3eb638f98610a8f
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="whats-the-difference-between-call-analytics-and-call-quality-dashboard"></a><span data-ttu-id="6dd52-103">通話の分析手法と通話品質のダッシュ ボードの違いは何ですか。</span><span class="sxs-lookup"><span data-stu-id="6dd52-103">What's the difference between Call Analytics and Call Quality Dashboard?</span></span>

<span data-ttu-id="6dd52-p101">Skype for Business を使用する 2 つの方法を監視し、通話品質の問題のトラブルシューティング: 通話の分析手法と通話品質のダッシュ ボード。この記事では、両方を説明し、それぞれの使い方を説明します。</span><span class="sxs-lookup"><span data-stu-id="6dd52-p101">Skype for Business gives you two ways to monitor and troubleshoot call-quality problems: Call Analytics and Call Quality Dashboard. This article describes both and tells you when to use each one.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6dd52-p102">通話の分析は、現在のプレビューです。テキストと画像がここに示されたは、操作が一致しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="6dd52-p102">Call Analytics is currently in preview. Text and images described here may not match your experience.</span></span> 
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a><span data-ttu-id="6dd52-108">通話の分析を使用することとについて</span><span class="sxs-lookup"><span data-stu-id="6dd52-108">What's Call Analytics, and when should I use it?</span></span>

<span data-ttu-id="6dd52-p103">分析を通話には、デバイス、ネットワーク、および特定の呼び出しと Skype for Business アカウントでは、各ユーザーの会議に関連する接続に関する詳細情報が表示されます。Skype for Business の管理者の場合、Skype for Business 通話の品質との接続の問題のトラブルシューティングに通話の分析を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6dd52-p103">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user in a Skype for Business account. If you're a Skype for Business admin, you can use Call Analytics to troubleshoot Skype for Business call quality and connection problems.</span></span>
  
<span data-ttu-id="6dd52-111">場合は、外部のベンダーからヘルプデスク エージェントなど以外の管理者、分析の通話を使用する割り当てることができますアクセス許可通話の分析を使用することができますが、Skype for Business 管理センターの残りの部分にアクセスできないようにします。</span><span class="sxs-lookup"><span data-stu-id="6dd52-111">If you want non-admins, such as helpdesk agents from an external vendor, to use Call Analytics, you can assign permissions so that they can use Call Analytics but they can't access the rest of the Skype for Business Admin center:</span></span> 
  
- <span data-ttu-id="6dd52-p104">**第 1 層のアクセス許可を持つヘルプデスク エージェント**: エージェントに限られたデータと個人を特定できる情報 (PII) で通話の分析を参照してください。呼び出しのトラブルシューティングを行うが、第 2 エージェントに会議の問題が渡しますされます。</span><span class="sxs-lookup"><span data-stu-id="6dd52-p104">**Helpdesk agents with Tier 1 permissions**: Agents see a limited set of data and personally identifiable information (PII) in Call Analytics. They can troubleshoot calls, but they will hand off problems with meetings to a Tier 2 agent.</span></span>
    
- <span data-ttu-id="6dd52-p105">**第 2 のアクセス許可を持つヘルプデスク エージェント**: エージェント通話分析で利用可能なすべてのデータを表示し、通話と会議の両方のトラブルシューティングを行います。通話ログと顧客情報へのフル アクセスがあります。</span><span class="sxs-lookup"><span data-stu-id="6dd52-p105">**Helpdesk agents with Tier 2 permissions**: Agents see all available data in Call Analytics and troubleshoot both calls and meetings. They have full access to call logs and customer information.</span></span>
    
<span data-ttu-id="6dd52-p106">分析の呼び出しを設定する方法の詳細については、「 [Skype for Business 通話分析を設定する](set-up-call-analytics.md)」を参照してください。分析を呼び出すと連携できるヘルプデスク エージェントに関する詳細については、[低下通話品質のトラブルシューティングに使用する着信の分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6dd52-p106">For details about setting up Call Analytics, see [Set up Skype for Business Call Analytics](set-up-call-analytics.md). For more information about how Helpdesk agents can work with Call Analytics, see [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a><span data-ttu-id="6dd52-118">通話品質のダッシュ ボードを使用することとについて</span><span class="sxs-lookup"><span data-stu-id="6dd52-118">What's the Call Quality Dashboard, and when should I use it?</span></span>

<span data-ttu-id="6dd52-p107">通話の分析は、通話品質のユーザーが発生したについて、特定の詳細を説明します。「本日午後通話を低下させるユーザー: 鈴木があるでしたか。通話の分析を使用して、デバイス、ネットワーク、接続、およびトニーの通話に関連するその他の要因 Skype for Business の管理者またはトレーニング ヘルプデスク エージェントできます調査します。</span><span class="sxs-lookup"><span data-stu-id="6dd52-p107">Call Analytics gives you detailed, specific information about the call quality experienced by users. Why did user Tony Smith have a poor call this afternoon? Using Call Analytics, a Skype for Business admin or trained helpdesk agent can investigate the device, network, connectivity, and other factors related to Tony's call.</span></span>
  
<span data-ttu-id="6dd52-p108">CA が対応している管理者のために、ヘルプデスク エージェント特定の呼び出し、通話品質の問題のトラブルシューティングを行う場所は、通話品質のダッシュ ボード (CQD) は Skype for Business の管理者に設計されており、ネットワーク エンジニアがネットワークを最適化します。CQD では、特定のユーザーからフォーカスを移動し、集計の情報を全体の Skype for Business の組織の代わりに確認します。</span><span class="sxs-lookup"><span data-stu-id="6dd52-p108">Where CA is designed to help admins and helpdesk agents troubleshoot call quality problems with specific calls, the Call Quality Dashboard (CQD) is designed to help Skype for Business admins and network engineers optimize a network. CQD shifts focus from specific users and instead looks at aggregate information for an entire Skype for Business organization.</span></span> 
  
<span data-ttu-id="6dd52-p109">おそらくトニーの低下が通話品質が他の多くのユーザーにも影響を与えることがネットワークの問題が原因でします。トニーの個別の通話のエクスペリエンスは CQD] に表示されるはありませんが、Skype for Business 使い呼び出しの全体的な品質をキャプチャします。CQD の全体的なパターン可能性があります明らかになります、通話品質の評価を常にネットワーク エンジニアができるようにします。CQD の通話品質の基準をより深く洞察を示すレポート全体通話の品質、server クライアントとクライアント ストリームと音声の品質[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)を提供します。</span><span class="sxs-lookup"><span data-stu-id="6dd52-p109">Maybe Tony's poor call quality is due to a network issue that's also affecting many other users. Tony's individual call experience isn't visible in CQD, but the overall quality of calls made using Skype for Business is captured. With the CQD, overall patterns may become apparent, allowing network engineers to make informed assessments of call quality. CQD provides reports of call quality metrics that give you insights into overall call quality, server-client and client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![Skype for Business 管理センターで通話品質のダッシュ ボードのスクリーン ショット。タブが表示されるは、通話品質の全体的なサーバー - クライアント、クライアント - クライアントでは、品質 SLA を表示します。](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
<span data-ttu-id="6dd52-130">詳細については、 [Skype for Business Online の通話品質のダッシュ ボードの機能](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6dd52-130">For more details, see [Features of the Call Quality Dashboard for Skype for Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).</span></span>
  
<span data-ttu-id="6dd52-p111">通話の分析手法と CQD、並列で実行され、単独または組み合わせて使用することができます。たとえば、1 層のエージェントについて詳しくは、通話の問題のトラブルシューティングが必要があることを決定します。階層 1 エージェント通話分析で階層 1 エージェントよりの詳細については、アクセス権を持つ、2 層エージェントに通話を渡します。でき、層 2 エージェントが問題にネットワーク エンジニアを通知することができます。ネットワーク エンジニア CQD 全体的なサイトに関連する問題が通話の問題の原因の原因になる可能性のあるかどうがオンにします。</span><span class="sxs-lookup"><span data-stu-id="6dd52-p111">Call Analytics and CQD run in parallel and can be used independently or together. For example, say a Tier 1 agent determines that they need more help troubleshooting a call problem. The Tier 1 agent passes the call to a Tier 2 agent, who has access to more information in Call Analytics than the Tier 1 agent. In turn, the Tier 2 agent can alert a network engineer to an issue. The network engineer may check CQD to see if an overall site-related issue could be a contributing cause of call problems.</span></span>
  
<span data-ttu-id="6dd52-136">CQD の詳細については、[有効にして Microsoft チームと Skype for Business Online の品質ダッシュ ボードの通話を使用して](turning-on-and-using-call-quality-dashboard.md)、および[ディメンションとメジャーが通話品質] ダッシュ ボード Microsoft チームと Skype for Business Online で利用できる](dimensions-and-measures-available-in-call-quality-dashboard.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6dd52-136">For more information about CQD, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md) and [Dimensions and measures available in Call Quality Dashboard for Microsoft Teams and Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6dd52-137">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6dd52-137">Related topics</span></span>
[<span data-ttu-id="6dd52-138">Skype for Business 通話分析を設定します。</span><span class="sxs-lookup"><span data-stu-id="6dd52-138">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="6dd52-139">不適切な Skype for Business のトラブルシューティングに使用する通話分析通話品質</span><span class="sxs-lookup"><span data-stu-id="6dd52-139">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)