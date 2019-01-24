---
title: 呼び出しを分析し、通話品質のダッシュ ボード
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 分析機能を呼び出すと品質のダッシュ ボードを呼び出すを監視し、通話品質の問題のトラブルシューティングに使用する場合について説明します。
ms.openlocfilehash: a212afea9f8d5010fa68af66ce72b39280a7d11c
ms.sourcegitcommit: 09fcd68e30e7f83110f98172382c74f970b339a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2019
ms.locfileid: "29442438"
---
# <a name="call-analytics-and-call-quality-dashboard"></a><span data-ttu-id="b8e0b-103">呼び出しを分析し、通話品質のダッシュ ボード</span><span class="sxs-lookup"><span data-stu-id="b8e0b-103">Call Analytics and Call Quality Dashboard</span></span>

<span data-ttu-id="b8e0b-104">マイクロソフトのチームとビジネス用の Skype が得を監視し、通話品質の問題をトラブルシューティングするための 2 つの方法: 呼び出しの分析と品質のダッシュ ボードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-104">Microsoft Teams and Skype for Business give you two ways to monitor and troubleshoot call-quality problems: Call Analytics and Call Quality Dashboard.</span></span> <span data-ttu-id="b8e0b-105">この記事では、これらの両方について説明し、どのような場合にそれぞれの方法を使用するべきかを示します。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-105">This article describes both and tells you when to use each one.</span></span>
  
<span data-ttu-id="b8e0b-106">**コール分析では、マイクロソフトのチームとビジネス管理センターの Skype です。**</span><span class="sxs-lookup"><span data-stu-id="b8e0b-106">**Call Analytics is now available in the Microsoft Teams and Skype for Business Admin Center.**</span></span> <span data-ttu-id="b8e0b-107">すべてのコール情報とユーザーのデータを表示するには、[**呼び出し履歴**] タブを使用します。ダッシュ ボードからユーザーを検索するか、[プロファイル] ページでユーザーの検索、または左側のナビゲーションで、**ユーザー**からユーザーを検索してこれを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-107">To see all of the call information and data for a user, use the **Call History** tab. You can do this by looking on the user's profile page by either searching for the user from the dashboard or finding the user from **Users** in the left navigation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8e0b-108">ヘルプデスク エージェントのアクセス許可とネットワーク トポロジのアップロードがで使用できる新しい管理ポータルで、今後数か月。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-108">Helpdesk agent permissions and network topology upload will be available in the new admin portal in the coming months.</span></span> <span data-ttu-id="b8e0b-109">使用を続行する間、https://adminportal.services.skypeforbusiness.comの第 1 層および第 2 層のヘルプデスクへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-109">In the meantime, you can continue to use  https://adminportal.services.skypeforbusiness.com for Tier 1 and Tier 2 helpdesk access.</span></span>
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a><span data-ttu-id="b8e0b-110">通話分析とは何ですか? どのような場合に使用するものですか?</span><span class="sxs-lookup"><span data-stu-id="b8e0b-110">What's Call Analytics, and when should I use it?</span></span>

<span data-ttu-id="b8e0b-111">分析機能の呼び出しは、デバイス、ネットワーク、および特定のコールとビジネス アカウントに、マイクロソフトのチームまたは Skype では、各ユーザーが会議に関連する接続に関する詳細情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-111">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user in a Microsoft Teams or Skype for Business account.</span></span> <span data-ttu-id="b8e0b-112">Office 365 管理者の場合、マイクロソフトのチームとビジネス用の Skype の通話品質と接続の問題のトラブルシューティングを行う分析機能の呼び出しを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-112">If you're an Office 365 admin, you can use Call Analytics to troubleshoot call quality and connection problems in Microsoft Teams and Skype for Business.</span></span>

<span data-ttu-id="b8e0b-113">マイクロソフト チーム & ビジネス管理センターの Skype のユーザーにこの情報を表示するには、すべての通話や会議を表示してそのユーザーが過去 30 日間の参加しているユーザーの詳細ページで、そのユーザーの [**通話履歴**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-113">To see this information for a user in the Microsoft Teams & Skype for Business Admin Center, click the **Call History** tab for that user in the user detail page, showing all the calls and meetings that user has participated in for the last 30 days.</span></span>

![ユーザー データの分析機能を呼び出します。](media/call-analytics-user-data.png)

<span data-ttu-id="b8e0b-115">メディアの詳細を含む、ネットワークの統計情報の特定のセッションに関する追加情報を取得するには、詳細を表示するセッションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-115">To get additional information about a given session including detailed media and networking statistics, click on a session to see the details.</span></span>

![ユーザー セッション データの分析機能を呼び出します。](media/call-analytics-user-data-session.png)

<span data-ttu-id="b8e0b-117">管理者以外が、外部の仕入先からのヘルプデスク担当者などをする場合は分析機能の呼び出しを使用することができますアクセス許可を割り当てる分析機能の呼び出しを使用することができますが、マイクロソフトのチーム & ビジネス管理センターの Skype の残りの部分にアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-117">If you want non-admins, such as helpdesk agents from an external vendor, to use Call Analytics, you can assign permissions so that they can use Call Analytics, but they can't access the rest of the Microsoft Teams & Skype for Business Admin Center:</span></span> 
  
- <span data-ttu-id="b8e0b-118">**ヘルプデスク エージェント通信のスペシャ リストのアクセス許可をサポートする**: エージェントは、限られたデータと分析の呼び出しで、個人を特定できる情報 (PII) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-118">**Helpdesk agents with communications support specialist permissions**: Agents see a limited set of data and personally identifiable information (PII) in Call Analytics.</span></span> <span data-ttu-id="b8e0b-119">呼び出しをトラブルシューティングすることができますが、通信のサポート ・ エンジニアに会議の問題を渡します。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-119">They can troubleshoot calls, but they will hand off problems with meetings to a communications support engineer.</span></span>
    
- <span data-ttu-id="b8e0b-120">**通信ヘルプデスク担当者は、エンジニア リングのアクセス許可をサポート**: エージェントは、分析機能の呼び出しで使用可能なすべてのデータを参照してくださいし、通話や会議の両方のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-120">**Helpdesk agents with communications support engineer permissions**: Agents see all available data in Call Analytics and troubleshoot both calls and meetings.</span></span> <span data-ttu-id="b8e0b-121">通話ログやユーザー情報に対するフル アクセスが付与されています。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-121">They have full access to call logs and customer information.</span></span>

> [!NOTE]
> <span data-ttu-id="b8e0b-122">通信のサポート ・ スペシャ リストの役割は、第 1 層のサポートに相当と通信のサポート ・ エンジニアの役割は、第 2 層のサポートに相当します。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-122">The communications support specialist role is equivalent to tier 1 support and the communications support engineer role is equivalent to tier 2 support.</span></span>

<span data-ttu-id="b8e0b-123">サポート担当者との通信通信の詳細については、エンジニアの役割をサポートして、[チームを管理する管理者の役割を使用してマイクロソフトのチーム](using-admin-roles.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-123">For more information about the communications support specialist and communications support engineer roles, see [Use Microsoft Teams admin roles to manage teams](using-admin-roles.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8e0b-124">ヘルプデスク エージェントのアクセス許可とネットワーク トポロジのアップロードは、マイクロソフトのチーム & ビジネス管理センターの Skype で利用できます。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-124">Helpdesk agent permissions and network topology upload are available in the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="b8e0b-125">通信のサポート ・ スペシャ リストとの通信のサポート エンジニアは、分析機能の呼び出しと呼び出し品質のダッシュ ボードにアクセスするのにはこのポータルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-125">Communications Support Specialists and Communications Support Engineers can use this portal to access Call Analytics and the Call Quality Dashboard.</span></span>
    
<span data-ttu-id="b8e0b-126">通話分析のセットアップの詳細については、「[Skype for Business の通話分析のセットアップ](set-up-call-analytics.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-126">For details about setting up Call Analytics, see [Set up Skype for Business Call Analytics](set-up-call-analytics.md).</span></span> <span data-ttu-id="b8e0b-127">ヘルプデスクの担当者が分析機能の呼び出しを機能させる方法の詳細については、[品質の低い呼び出しのトラブルシューティングを行うコール分析機能の使用](use-call-analytics-to-troubleshoot-poor-call-quality.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-127">For more information about how Helpdesk agents can work with Call Analytics, see [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a><span data-ttu-id="b8e0b-128">通話品質ダッシュボードとは何ですか? どのような場合に使用するものですか?</span><span class="sxs-lookup"><span data-stu-id="b8e0b-128">What's the Call Quality Dashboard, and when should I use it?</span></span>

<span data-ttu-id="b8e0b-129">呼び出しの分析では、ユーザーによって発生した通話の音質に関する情報の詳細に特定できます。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-129">Call Analytics gives you detailed, specific information about the call quality experienced by users.</span></span> <span data-ttu-id="b8e0b-130">ユーザー Tony Smith は午後の不適切な呼び出しを理由がでしたか。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-130">Why did user Tony Smith have a poor call this afternoon?</span></span> <span data-ttu-id="b8e0b-131">分析機能の呼び出しを使用すると、マイクロソフトのチームまたは業務管理者またはヘルプデスクの訓練を受けたエージェントの Skype 調べることができます、デバイス、ネットワーク、接続、およびトニーの呼び出しに関連するその他の要因です。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-131">Using Call Analytics, a Microsoft Teams or Skype for Business admin or trained helpdesk agent can investigate the device, network, connectivity, and other factors related to Tony's call.</span></span>
  
<span data-ttu-id="b8e0b-132">通話分析が、特定の通話の品質に関する問題を管理者やヘルプデスク エージェントがトラブルシューティングできるように設計されているのに対し、通話品質ダッシュボード (CQD) は Skype for Business 管理者やネットワーク エンジニアがネットワークを最適化できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-132">Where CA is designed to help admins and helpdesk agents troubleshoot call quality problems with specific calls, the Call Quality Dashboard (CQD) is designed to help Skype for Business admins and network engineers optimize a network.</span></span> <span data-ttu-id="b8e0b-133">CQD では特定のユーザーから焦点を外して、代わりに Skype for Business 組織全体の集計された情報について考察することになります。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-133">CQD shifts focus from specific users and instead looks at aggregate information for an entire Skype for Business organization.</span></span> 
  
<span data-ttu-id="b8e0b-p111">Tony の通話が低品質であったことは、他の数多くのユーザーにも影響を及ぼしている、ネットワークの問題がおそらく原因だと考えられます。Tony の個人的な通話経験については CQD で見ることはできませんが、Skype for Business を使用した通話の品質の全体像を把握できます。CQD では、全体のパターンが明らかに示され、ネットワーク エンジニアは確かな情報に基づく通話品質の評価を行えるようになります。CQD は通話品質の指標のレポートを提供し、全体的な通話品質、サーバーとクライアント間およびクライアント同士の間のストリーム、および音声品質の [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252) についての洞察を得られます。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-p111">Maybe Tony's poor call quality is due to a network issue that's also affecting many other users. Tony's individual call experience isn't visible in CQD, but the overall quality of calls made using Skype for Business is captured. With the CQD, overall patterns may become apparent, allowing network engineers to make informed assessments of call quality. CQD provides reports of call quality metrics that give you insights into overall call quality, server-client and client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![Screenshot of Call Quality Dashboard in the Skype for Business Admin Center. Tabs shown are Overall Call Quality, Server - Client, Client - Client, and View Quality SLA.](media/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
<span data-ttu-id="b8e0b-140">詳細については、「[Skype for Business Online の通話品質ダッシュボードの機能](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-140">For more details, see [Features of the Call Quality Dashboard for Skype for Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).</span></span>
  
<span data-ttu-id="b8e0b-141">呼び出しの分析と救難が並列で実行し、個別にまたは一緒に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-141">Call Analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="b8e0b-142">たとえば、サポート ・ スペシャ リストは、呼び出しに関する問題のトラブルシューティング ヘルプが必要があることを決定する通信があるとします。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-142">For example, say a communications support specialist determines that they need more help troubleshooting a call problem.</span></span> <span data-ttu-id="b8e0b-143">通信のサポート担当者は、分析機能の呼び出しで通信スペシャ リストのサポートの詳細については、アクセス権を持つ通信サポート ・ エンジニアへの呼び出しを渡します。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-143">The communications support specialist passes the call to a communications support engineer, who has access to more information in Call Analytics than the communications support specialist.</span></span> <span data-ttu-id="b8e0b-144">さらに、通信のサポート ・ エンジニアは、ネットワーク ・ エンジニアの問題を警告できます。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-144">In turn, the communications support engineer can alert a network engineer to an issue.</span></span> <span data-ttu-id="b8e0b-145">ネットワーク エンジニア リングは、全体的なサイトに関連する問題が呼び出しに関する問題の原因の原因になる可能性があるかどう救難をチェックします。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-145">The network engineer might check CQD to see if an overall site-related issue could be a contributing cause of call problems.</span></span>
  
<span data-ttu-id="b8e0b-146">救難に関する詳細について[を有効にしてマイクロソフトのチームとビジネス オンラインの Skype の品質ダッシュ ボードの呼び出しを使用して](turning-on-and-using-call-quality-dashboard.md)、[ディメンションとメジャーのマイクロソフトのチームとビジネス オンラインの Skype の品質ダッシュ ボードの呼び出しで使用可能な](dimensions-and-measures-available-in-call-quality-dashboard.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8e0b-146">For more information about CQD, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md) and [Dimensions and measures available in Call Quality Dashboard for Microsoft Teams and Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b8e0b-147">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b8e0b-147">Related topics</span></span>

[<span data-ttu-id="b8e0b-148">分析機能の呼び出しを設定します</span><span class="sxs-lookup"><span data-stu-id="b8e0b-148">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="b8e0b-149">通話分析を使用して低い通話品質をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="b8e0b-149">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="b8e0b-150">有効にして、マイクロソフトのチームと Skype のオンライン ビジネスの品質のダッシュ ボードの呼び出しを使用して</span><span class="sxs-lookup"><span data-stu-id="b8e0b-150">Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>](turning-on-and-using-call-quality-dashboard.md)