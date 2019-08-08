---
title: 通話分析および通話品質ダッシュボード
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: conceptual
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 通話分析と通話品質ダッシュボードと、それらを使用して通話品質の問題を監視およびトラブルシューティングする場合について説明します。
ms.openlocfilehash: 1130e901ca8c7103c9dd73990c4c0af47898203d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237519"
---
# <a name="call-analytics-and-call-quality-dashboard"></a><span data-ttu-id="8a85a-103">通話分析および通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="8a85a-103">Call Analytics and Call Quality Dashboard</span></span>

<span data-ttu-id="8a85a-104">Microsoft Teams と Skype for Business では、通話品質の問題を監視してトラブルシューティングするための2つの方法が用意されています。通話分析と通話品質ダッシュボード (CQD)。</span><span class="sxs-lookup"><span data-stu-id="8a85a-104">Microsoft Teams and Skype for Business give you two ways to monitor and troubleshoot call-quality problems: Call Analytics and Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="8a85a-105">この記事では、これらの両方について説明し、どのような場合にそれぞれの方法を使用するべきかを示します。</span><span class="sxs-lookup"><span data-stu-id="8a85a-105">This article describes both and tells you when to use each one.</span></span>

<span data-ttu-id="8a85a-106">通話分析と CQD は並列で実行され、個別に、または一緒に使うことができます。</span><span class="sxs-lookup"><span data-stu-id="8a85a-106">Call Analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="8a85a-107">たとえば、通話の問題のトラブルシューティングについては、コミュニケーションサポート担当者がより多くの情報が必要であると判断したとします。</span><span class="sxs-lookup"><span data-stu-id="8a85a-107">For example, say a communications support specialist determines that they need more help troubleshooting a call problem.</span></span> <span data-ttu-id="8a85a-108">通信サポートスペシャリストは、通信サポートエンジニアに通話を渡し、コミュニケーションサポートスペシャリストよりも詳細な情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8a85a-108">The communications support specialist passes the call to a communications support engineer, who has access to more information in Call Analytics than the communications support specialist.</span></span> <span data-ttu-id="8a85a-109">さらに、通信サポートエンジニアがネットワークエンジニアに問題を通知することができます。</span><span class="sxs-lookup"><span data-stu-id="8a85a-109">In turn, the communications support engineer can alert a network engineer to an issue.</span></span> <span data-ttu-id="8a85a-110">ネットワークエンジニアは、CQD をチェックして、サイトに関連する全体的な問題が、通話の問題の原因になっている可能性があるかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8a85a-110">The network engineer might check CQD to see if an overall site-related issue could be a contributing cause of call problems.</span></span>

## <a name="whats-call-analytics-and-when-should-i-use-it"></a><span data-ttu-id="8a85a-111">通話分析とは何ですか? どのような場合に使用するものですか?</span><span class="sxs-lookup"><span data-stu-id="8a85a-111">What's Call Analytics, and when should I use it?</span></span>

<span data-ttu-id="8a85a-112">**通話分析は[Microsoft Teams 管理センター](https://admin.teams.microsoft.com)で利用できるようになりました。**</span><span class="sxs-lookup"><span data-stu-id="8a85a-112">**Call Analytics is now available in the [Microsoft Teams admin center](https://admin.teams.microsoft.com).**</span></span> <span data-ttu-id="8a85a-113">すべての通話情報とユーザーのデータを表示するには、[**通話履歴**] タブを使用します。この操作を行うには、ユーザーのプロファイルページで、ダッシュボードからユーザーを検索するか、左側のナビゲーションでユーザー \*\*\*\* を検索します。</span><span class="sxs-lookup"><span data-stu-id="8a85a-113">To see all of the call information and data for a user, use the **Call History** tab. You can do this by looking on the user's profile page by either searching for the user from the dashboard or finding the user from **Users** in the left navigation.</span></span>

<span data-ttu-id="8a85a-114">[通話分析] には、Microsoft Teams または Skype for Business アカウントの各ユーザーの特定の通話と会議に関連するデバイス、ネットワーク、接続に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a85a-114">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user in a Microsoft Teams or Skype for Business account.</span></span> <span data-ttu-id="8a85a-115">このユーザの通話品質が悪いのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="8a85a-115">Why did this user have a poor call this afternoon?</span></span> <span data-ttu-id="8a85a-116">Microsoft Teams と Skype for Business の通話品質と接続の問題のトラブルシューティングを行うには、通話分析を使用して、Office 365 管理者またはトレーニングされたヘルプデスクエージェントが、電話に関連するデバイス、ネットワーク、接続、その他の要因を調査します。</span><span class="sxs-lookup"><span data-stu-id="8a85a-116">Using Call Analytics, an Office 365 admin or trained helpdesk agent can investigate the device, network, connectivity, and other factors related to his call to troubleshoot call quality and connection problems in Microsoft Teams and Skype for Business.</span></span>

<span data-ttu-id="8a85a-117">Microsoft Teams 管理センターでユーザーのこの情報を表示するには、[ユーザーの詳細] ページでそのユーザーの [**通話履歴**] タブをクリックして、過去30日間にユーザーが参加したすべての通話と会議を表示します。</span><span class="sxs-lookup"><span data-stu-id="8a85a-117">To see this information for a user in the Microsoft Teams admin center, click the **Call History** tab for that user in the user detail page, showing all the calls and meetings that user has participated in for the last 30 days.</span></span>

![すべての分析ユーザーデータのスクリーンショット。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

<span data-ttu-id="8a85a-119">詳細なメディアとネットワークの統計情報など、特定のセッションに関する追加情報を取得するには、セッションをクリックして詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="8a85a-119">To get additional information about a given session including detailed media and networking statistics, click on a session to see the details.</span></span>

![通話分析のユーザーセッションデータのスクリーンショット。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

<span data-ttu-id="8a85a-121">外部ベンダーからのヘルプデスクエージェントなど、管理者以外のユーザーが通話分析を使用できるようにする場合は、通話分析を使用できるようにアクセス許可を割り当てることができますが、Microsoft Teams 管理センターの残りの部分にはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="8a85a-121">If you want non-admins, such as helpdesk agents from an external vendor, to use Call Analytics, you can assign permissions so that they can use Call Analytics, but they can't access the rest of the Microsoft Teams admin center:</span></span> 
  
- <span data-ttu-id="8a85a-122">**通信がサポートされているヘルプデスクエージェント: スペシャリストの権限**: 担当者は、通話分析で一部のデータと個人情報 (PII) を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8a85a-122">**Helpdesk agents with communications support specialist permissions**: Agents see a limited set of data and personally identifiable information (PII) in Call Analytics.</span></span> <span data-ttu-id="8a85a-123">通話のトラブルシューティングを行うことはできますが、会議の問題はコミュニケーションサポートエンジニアに渡します。</span><span class="sxs-lookup"><span data-stu-id="8a85a-123">They can troubleshoot calls, but they will hand off problems with meetings to a communications support engineer.</span></span>
    
- <span data-ttu-id="8a85a-124">**通信サポートエンジニアのアクセス許可を持つヘルプデスクエージェント**: エージェントは、通話分析で利用可能なすべてのデータを表示し、通話と会議の両方のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="8a85a-124">**Helpdesk agents with communications support engineer permissions**: Agents see all available data in Call Analytics and troubleshoot both calls and meetings.</span></span> <span data-ttu-id="8a85a-125">通話ログやユーザー情報に対するフル アクセスが付与されています。</span><span class="sxs-lookup"><span data-stu-id="8a85a-125">They have full access to call logs and customer information.</span></span>

> [!NOTE]
> <span data-ttu-id="8a85a-126">通信サポートスペシャリストの役割は、プレビューポータルでの階層1のサポートロールと同じであり、通信サポートエンジニアロールは、プレビューポータルの階層2のサポートロールと同じです。</span><span class="sxs-lookup"><span data-stu-id="8a85a-126">The communications support specialist role is equivalent to tier 1 support role from the preview portal and the communications support engineer role is equivalent to tier 2 support role from the preview portal.</span></span>

<span data-ttu-id="8a85a-127">通信サポートスペシャリストと通信サポートエンジニアロールの詳細については、「 [Microsoft teams の管理者ロールを使用してチームを管理する](using-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a85a-127">For more information about the communications support specialist and communications support engineer roles, see [Use Microsoft Teams admin roles to manage teams](using-admin-roles.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a85a-128">ヘルプデスクのエージェントの権限とネットワークトポロジのアップロードは、Microsoft Teams 管理センターで利用できます。</span><span class="sxs-lookup"><span data-stu-id="8a85a-128">Helpdesk agent permissions and network topology upload are available in the Microsoft Teams admin center.</span></span> <span data-ttu-id="8a85a-129">通信サポートスペシャリストおよび通信サポートエンジニアは、このポータルを使って通話分析と通話品質ダッシュボードにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8a85a-129">Communications Support Specialists and Communications Support Engineers can use this portal to access Call Analytics and the Call Quality Dashboard.</span></span>
    
<span data-ttu-id="8a85a-130">通話分析のセットアップの詳細については、「[Skype for Business の通話分析のセットアップ](set-up-call-analytics.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8a85a-130">For details about setting up Call Analytics, see [Set up Skype for Business Call Analytics](set-up-call-analytics.md).</span></span> <span data-ttu-id="8a85a-131">ヘルプデスクエージェントが通話分析を使用する方法について詳しくは、「[通話分析を使用して低品質の通話品質をトラブルシューティングする」を](use-call-analytics-to-troubleshoot-poor-call-quality.md)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8a85a-131">For more information about how Helpdesk agents can work with Call Analytics, see [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a><span data-ttu-id="8a85a-132">通話品質ダッシュボードとは何ですか? どのような場合に使用するものですか?</span><span class="sxs-lookup"><span data-stu-id="8a85a-132">What's the Call Quality Dashboard, and when should I use it?</span></span>
  
<span data-ttu-id="8a85a-133">通話分析は管理者およびヘルプデスクエージェントが特定の通話に関する通話品質の問題を解決するために設計されていますが、通話品質ダッシュボード (CQD) は、チーム管理者、Skype for Business 管理者、ネットワークエンジニアがネットワークを最適化するために設計されています。</span><span class="sxs-lookup"><span data-stu-id="8a85a-133">Whereas Call Analytics is designed to help admins and helpdesk agents troubleshoot call quality problems with specific calls, the Call Quality Dashboard (CQD) is designed to help Teams admins, Skype for Business admins, and network engineers optimize a network.</span></span> <span data-ttu-id="8a85a-134">CQD では、特定のユーザーからフォーカスが移動され、チーム全体または Skype for Business 組織の集計情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a85a-134">CQD shifts focus from specific users and instead looks at aggregate information for an entire Teams or Skype for Business organization.</span></span> <span data-ttu-id="8a85a-135">詳細については、「 [Teams および Skype For Business Online の通話品質ダッシュボードの機能](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a85a-135">For more details, see [Features of the Call Quality Dashboard for Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).</span></span>
  
<span data-ttu-id="8a85a-136">ユーザーの通話品質の低下は、他の多くのユーザーにも影響するネットワークの問題が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8a85a-136">Maybe the user's poor call quality is due to a network issue that's also affecting many other users.</span></span> <span data-ttu-id="8a85a-137">CQD には個別の通話エクスペリエンスは表示されませんが、Microsoft Teams または Skype for Business を使用して発信した通話の全体的な品質は、キャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="8a85a-137">The individual call experience isn't visible in CQD, but the overall quality of calls made using Microsoft Teams or Skype for Business is captured.</span></span> <span data-ttu-id="8a85a-138">CQD では、全体のパターンが明らかに示され、ネットワーク エンジニアは確かな情報に基づく通話品質の評価を行えるようになります。</span><span class="sxs-lookup"><span data-stu-id="8a85a-138">With the CQD, overall patterns may become apparent, allowing network engineers to make informed assessments of call quality.</span></span> <span data-ttu-id="8a85a-139">CQD は通話品質の指標のレポートを提供します。これにより、全体的な通話品質、サーバークライアントストリーム、クライアントクライアントストリーム、音声品質[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)を把握できます。</span><span class="sxs-lookup"><span data-stu-id="8a85a-139">CQD provides reports of call quality metrics that give you insights into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span>
  
![通話品質ダッシュボードのスクリーンショット。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="8a85a-141">CQD の場所で強化されたレポートを使用して、問題が単一ユーザーに限定されているか、またはユーザーの大きなセグメントに影響を与えるかを判断するために、ユーザーの建物内の総通話品質と信頼性を評価できます。</span><span class="sxs-lookup"><span data-stu-id="8a85a-141">With the help of CQD's Location-Enhanced Reports, aggregate call quality and reliability within the user's building can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span>

![通話品質ダッシュボードの場所の拡張されたレポートのスクリーンショット。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

> [!NOTE]
> <span data-ttu-id="8a85a-143">CQD での建物またはエンドポイント固有のビューを有効にするには、管理者が CQD のテナントデータアップロードページで[建物またはエンドポイントの情報をアップロード](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a85a-143">To enable building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information) on CQD's Tenant Data Upload page.</span></span> 

<span data-ttu-id="8a85a-144">ヘルプデスクエージェントなどの非管理者が通話品質ダッシュボードを使用できるようにするには、これらのユーザーに**Teams Communications Support エンジニア**、 **Teams コミュニケーションサポートスペシャリスト**、または**レポート閲覧**者の役割を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8a85a-144">If you want non-admins, such as helpdesk agents, to use Call Quality Dashboard, you can assign those users the **Teams Communications Support Engineer**, **Teams Communications Support Specialist**, or **Reports Reader** role.</span></span> <span data-ttu-id="8a85a-145">次の役割を持つユーザーは、通話品質ダッシュボードにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8a85a-145">Users with the following roles can access Call Quality Dashboard:</span></span>

- <span data-ttu-id="8a85a-146">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="8a85a-146">Global Administrator</span></span>
- <span data-ttu-id="8a85a-147">グローバルリーダー</span><span class="sxs-lookup"><span data-stu-id="8a85a-147">Global Reader</span></span>
- <span data-ttu-id="8a85a-148">Skype for Business 管理者</span><span class="sxs-lookup"><span data-stu-id="8a85a-148">Skype for Business Administrator</span></span>
- <span data-ttu-id="8a85a-149">Teams サービス管理者</span><span class="sxs-lookup"><span data-stu-id="8a85a-149">Teams Service Administrator</span></span>
- <span data-ttu-id="8a85a-150">Teams 通信管理者</span><span class="sxs-lookup"><span data-stu-id="8a85a-150">Teams Communications Administrator</span></span>
- <span data-ttu-id="8a85a-151">Teams 通信サポート エンジニア</span><span class="sxs-lookup"><span data-stu-id="8a85a-151">Teams Communications Support Engineer</span></span>
- <span data-ttu-id="8a85a-152">Teams 通信サポート スペシャリスト</span><span class="sxs-lookup"><span data-stu-id="8a85a-152">Teams Communications Support Specialist</span></span>
- <span data-ttu-id="8a85a-153">レポートリーダー</span><span class="sxs-lookup"><span data-stu-id="8a85a-153">Reports Reader</span></span>

> [!NOTE]
> <span data-ttu-id="8a85a-154">Teams 通信サポートエンジニア、Teams 通信サポートスペシャリスト、およびレポートリーダーの役割は、CQD のテナントデータアップロードページ上のファイルを変更したり、テナントの CQD をアクティブ化したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8a85a-154">The Teams Communications Support Engineer, Teams Communications Support Specialist, and Reports Reader roles cannot modify files on CQD's Tenant Data Upload page nor activate CQD for a tenant.</span></span>

<span data-ttu-id="8a85a-155">これらの役割の詳細については、「 [Office 365 管理者ロールについ](/office365/admin/add-users/about-admin-roles)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a85a-155">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="8a85a-156">CQD の詳細については、「 [Microsoft teams および skype For Business online の通話品質ダッシュボードをオンにして使用する](turning-on-and-using-call-quality-dashboard.md)」と「 [Microsoft teams および Skype for Business Online の通話品質ダッシュボードで利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a85a-156">For more information about CQD, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](turning-on-and-using-call-quality-dashboard.md) and [Dimensions and measures available in Call Quality Dashboard for Microsoft Teams and Skype for Business Online](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8a85a-157">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8a85a-157">Related topics</span></span>

[<span data-ttu-id="8a85a-158">ビデオ: 通話品質の概要</span><span class="sxs-lookup"><span data-stu-id="8a85a-158">Video: Call Quality Overview</span></span>](https://aka.ms/teams-quality)

[<span data-ttu-id="8a85a-159">通話分析をセットアップする</span><span class="sxs-lookup"><span data-stu-id="8a85a-159">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="8a85a-160">通話分析を使用して低品質の通話をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="8a85a-160">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="8a85a-161">Microsoft Teams および Skype for Business Online で通話品質ダッシュボードをオンにして使用する</span><span class="sxs-lookup"><span data-stu-id="8a85a-161">Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online</span></span>](turning-on-and-using-call-quality-dashboard.md)
