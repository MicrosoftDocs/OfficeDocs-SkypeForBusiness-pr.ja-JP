---
title: "通話分析と通話品質ダッシュボードの違いを教えてください"
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
description: Learn about Call Analytics and Call Quality Dashboard and when to use them to monitor and troubleshoot call-quality problems in Skype for Business.
ms.openlocfilehash: a17b98451013f24810fd437fa3eb638f98610a8f
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
# <a name="whats-the-difference-between-call-analytics-and-call-quality-dashboard"></a><span data-ttu-id="30d06-103">通話分析と通話品質ダッシュボードの違いを教えてください</span><span class="sxs-lookup"><span data-stu-id="30d06-103">What's the difference between Call Analytics and Call Quality Dashboard?</span></span>

<span data-ttu-id="30d06-p101">[] Skype for Business では、通話品質の問題を監視してトラブルシューティングするために、通話分析と通話品質ダッシュボードという 2 つの方法を利用できます。この記事では、これらの両方について説明し、どのような場合にそれぞれの方法を使用するべきかを示します。</span><span class="sxs-lookup"><span data-stu-id="30d06-p101">Skype for Business gives you two ways to monitor and troubleshoot call-quality problems: Call Analytics and Call Quality Dashboard. This article describes both and tells you when to use each one.</span></span>
  
> [!NOTE]
> <span data-ttu-id="30d06-p102">通話分析は現在プレビューとして提供されています。ここに記載されるテキストと画像は実際の使用時のものと一致しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="30d06-p102">Call Analytics is currently in preview. Text and images described here may not match your experience.</span></span> 
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a><span data-ttu-id="30d06-108">通話分析とは何ですか? どのような場合に使用するものですか?</span><span class="sxs-lookup"><span data-stu-id="30d06-108">What's Call Analytics, and when should I use it?</span></span>

<span data-ttu-id="30d06-p103">通話分析は、Skype for Business アカウント内の各ユーザーの特定の通話および会議に関係するデバイス、ネットワーク、接続性についての詳細情報を示します。Skype for Business 管理者である場合は、Skype for Business の通話品質と接続に関する問題をトラブルシューティングするために通話分析を使用できます。</span><span class="sxs-lookup"><span data-stu-id="30d06-p103">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user in a Skype for Business account. If you're a Skype for Business admin, you can use Call Analytics to troubleshoot Skype for Business call quality and connection problems.</span></span>
  
<span data-ttu-id="30d06-111">管理者以外の、たとえば外部ベンダーからのヘルプデスク エージェントなどの人に通話分析を使用してほしい場合は、その人に通話分析を使用できる、ただし Skype for Business 管理センターの他の部分にはアクセスできないアクセス許可を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="30d06-111">If you want non-admins, such as helpdesk agents from an external vendor, to use Call Analytics, you can assign permissions so that they can use Call Analytics but they can't access the rest of the Skype for Business Admin center:</span></span> 
  
- <span data-ttu-id="30d06-p104">**階層 1 のアクセス許可を持つヘルプデスク エージェント**: エージェントは、通話分析において制限されたデータのセットと個人を特定できる情報 (PII) を見ることができます。通話に対してはトラブルシューティングを行えますが、会議に関する問題は階層 2 のエージェントに引き渡すことになります。</span><span class="sxs-lookup"><span data-stu-id="30d06-p104">**Helpdesk agents with Tier 1 permissions**: Agents see a limited set of data and personally identifiable information (PII) in Call Analytics. They can troubleshoot calls, but they will hand off problems with meetings to a Tier 2 agent.</span></span>
    
- <span data-ttu-id="30d06-p105">**階層 2 のアクセス許可を持つヘルプデスク エージェント**: エージェントは通話分析において利用できるデータをすべて見ることができ、通話と会議の両方についてトラブルシューティングできます。通話ログやユーザー情報に対するフル アクセスが付与されています。</span><span class="sxs-lookup"><span data-stu-id="30d06-p105">**Helpdesk agents with Tier 2 permissions**: Agents see all available data in Call Analytics and troubleshoot both calls and meetings. They have full access to call logs and customer information.</span></span>
    
<span data-ttu-id="30d06-116">通話分析のセットアップの詳細については、「[Skype for Business の通話分析のセットアップ](set-up-call-analytics.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="30d06-116">For details about setting up Call Analytics, see [Set up Skype for Business Call Analytics](set-up-call-analytics.md).</span></span> <span data-ttu-id="30d06-117">ヘルプデスクの担当者が分析機能の呼び出しを機能させる方法の詳細については、[品質の低い呼び出しのトラブルシューティングを行うコール分析機能の使用](use-call-analytics-to-troubleshoot-poor-call-quality.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30d06-117">For more information about how Helpdesk agents can work with Call Analytics, see [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a><span data-ttu-id="30d06-118">通話品質ダッシュボードとは何ですか? どのような場合に使用するものですか?</span><span class="sxs-lookup"><span data-stu-id="30d06-118">What's the Call Quality Dashboard, and when should I use it?</span></span>

<span data-ttu-id="30d06-p107">通話分析では、ユーザーが経験した通話品質についての詳細な特定の情報が提供されます。Tony Smith というユーザーが今日の午後に低品質の通話を経験した原因を突き止めるために、通話分析を使用して、Skype for Business 管理者または訓練されたヘルプデスク エージェントがデバイス、ネットワーク、接続性その他の Tony の通話に関係する要素を調査することができます。</span><span class="sxs-lookup"><span data-stu-id="30d06-p107">Call Analytics gives you detailed, specific information about the call quality experienced by users. Why did user Tony Smith have a poor call this afternoon? Using Call Analytics, a Skype for Business admin or trained helpdesk agent can investigate the device, network, connectivity, and other factors related to Tony's call.</span></span>
  
<span data-ttu-id="30d06-p108">通話分析が、特定の通話の品質に関する問題を管理者やヘルプデスク エージェントがトラブルシューティングできるように設計されているのに対し、通話品質ダッシュボード (CQD) は Skype for Business 管理者やネットワーク エンジニアがネットワークを最適化できるように設計されています。CQD では特定のユーザーから焦点を外して、代わりに Skype for Business 組織全体の集計された情報について考察することになります。</span><span class="sxs-lookup"><span data-stu-id="30d06-p108">Where CA is designed to help admins and helpdesk agents troubleshoot call quality problems with specific calls, the Call Quality Dashboard (CQD) is designed to help Skype for Business admins and network engineers optimize a network. CQD shifts focus from specific users and instead looks at aggregate information for an entire Skype for Business organization.</span></span> 
  
<span data-ttu-id="30d06-p109">Tony の通話が低品質であったことは、他の数多くのユーザーにも影響を及ぼしている、ネットワークの問題がおそらく原因だと考えられます。Tony の個人的な通話経験については CQD で見ることはできませんが、Skype for Business を使用した通話の品質の全体像を把握できます。CQD では、全体のパターンが明らかに示され、ネットワーク エンジニアは確かな情報に基づく通話品質の評価を行えるようになります。CQD は通話品質の指標のレポートを提供し、全体的な通話品質、サーバーとクライアント間およびクライアント同士の間のストリーム、および音声品質の [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252) についての洞察を得られます。</span><span class="sxs-lookup"><span data-stu-id="30d06-p109">Maybe Tony's poor call quality is due to a network issue that's also affecting many other users. Tony's individual call experience isn't visible in CQD, but the overall quality of calls made using Skype for Business is captured. With the CQD, overall patterns may become apparent, allowing network engineers to make informed assessments of call quality. CQD provides reports of call quality metrics that give you insights into overall call quality, server-client and client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![Screenshot of Call Quality Dashboard in the Skype for Business Admin Center. Tabs shown are Overall Call Quality, Server - Client, Client - Client, and View Quality SLA.](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
<span data-ttu-id="30d06-130">詳細については、「[Skype for Business Online の通話品質ダッシュボードの機能](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="30d06-130">For more details, see [Features of the Call Quality Dashboard for Skype for Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).</span></span>
  
<span data-ttu-id="30d06-p111">通話分析と CQD を並行して実行し、それぞれ別個に使用したり一緒に組み合わせて使用することができます。たとえば、階層 1 のエージェントが、通話の問題をトラブルシューティングするためにより多くのサポートが必要である場合を考えます。階層 1 のエージェントは、通話を階層 2 のエージェントに渡します。階層 2 のエージェントは、階層 1 のエージェントよりも多くの通話分析の情報にアクセスできます。さらに、階層 2 のエージェントはネットワーク エンジニアが問題を見逃さないようにアラートを出すことができます。ネットワーク エンジニアは CQD をチェックして全体的なサイト関連の問題が通話の問題の原因を成しているかを確認します。</span><span class="sxs-lookup"><span data-stu-id="30d06-p111">Call Analytics and CQD run in parallel and can be used independently or together. For example, say a Tier 1 agent determines that they need more help troubleshooting a call problem. The Tier 1 agent passes the call to a Tier 2 agent, who has access to more information in Call Analytics than the Tier 1 agent. In turn, the Tier 2 agent can alert a network engineer to an issue. The network engineer may check CQD to see if an overall site-related issue could be a contributing cause of call problems.</span></span>
  
<span data-ttu-id="30d06-136">救難に関する詳細について[を有効にしてマイクロソフトのチームとビジネス オンラインの Skype の品質ダッシュ ボードの呼び出しを使用して](turning-on-and-using-call-quality-dashboard.md)、[ディメンションとメジャーのマイクロソフトのチームとビジネス オンラインの Skype の品質ダッシュ ボードの呼び出しで使用可能な](dimensions-and-measures-available-in-call-quality-dashboard.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30d06-136">For more information about CQD, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md) and [Dimensions and measures available in Call Quality Dashboard for Microsoft Teams and Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="30d06-137">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="30d06-137">Related topics</span></span>
[<span data-ttu-id="30d06-138">Skype for Business の通話分析をセットアップする</span><span class="sxs-lookup"><span data-stu-id="30d06-138">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="30d06-139">通話分析を使用して Skype for Business の低い通話品質をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="30d06-139">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)