---
title: 通話品質ダッシュボード (CQD) とは
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 通話品質ダッシュボード (CQD) と、それを使用して Microsoft Teams の会議および通話品質に関するレポートを表示する方法について説明します。
ms.openlocfilehash: c78e427ef87f7485932fac207c10add71c8bf269
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094941"
---
# <a name="what-is-call-quality-dashboard-cqd"></a><span data-ttu-id="58857-103">通話品質ダッシュボード (CQD) とは</span><span class="sxs-lookup"><span data-stu-id="58857-103">What is Call Quality Dashboard (CQD)?</span></span>

<span data-ttu-id="58857-104">Microsoft 通話品質ダッシュボード (CQD) [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - Microsoft Teams、Skype for Business Online、Skype for Business Server 2019 の通話と会議の品質を組織全体のレベルで表示します。</span><span class="sxs-lookup"><span data-stu-id="58857-104">The Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

  
<span data-ttu-id="58857-105">最新バージョンの CQD は、ほぼリアルタイム [(NRT)](CQD-data-and-reports.md)データ フィードを備え、通話の終了から 30 分以内に CQD で通話レコードを利用できます。</span><span class="sxs-lookup"><span data-stu-id="58857-105">The latest version of CQD features a [near-real-time (NRT) data feed](CQD-data-and-reports.md), which means that call records are available in CQD within 30 minutes of the end of a call.</span></span>

<span data-ttu-id="58857-106">CQD にエンド ユーザーを特定できる [情報 (EUII)](CQD-data-and-reports.md#euii-data)データが含まれる場合は [、Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)全体で EUII と同じ方法で管理されます。</span><span class="sxs-lookup"><span data-stu-id="58857-106">Wherever CQD includes [end-user identifiable information (EUII) data](CQD-data-and-reports.md#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="58857-107">CQD は、Teams 管理者、Skype for Business 管理者、ネットワーク エンジニアが、組織全体のレベルで通話と会議の品質を監視するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="58857-107">CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level.</span></span> <span data-ttu-id="58857-108">CQD を使用して、パフォーマンスの品質を向上するために **ネットワーク** を最適化します。</span><span class="sxs-lookup"><span data-stu-id="58857-108">You'll use CQD to help you **optimize your network** to drive performance quality.</span></span> <span data-ttu-id="58857-109">特定のユーザーの通話と会議の情報を調える必要がある場合は、CQD データとユーザーごとの通話分析を[組み合わせて使用します](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="58857-109">When you need to look into call and meeting information for a **specific user**, use CQD data in conjunction with per-user [call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>

<span data-ttu-id="58857-110">たとえば、CQD を使用すると、ユーザーの低品質 (ユーザーごとの通話分析を使用して確認した) がネットワークの問題に起因し、他の多くのユーザーにも影響を与えると判断できます。</span><span class="sxs-lookup"><span data-stu-id="58857-110">For example, using CQD, you can determine that a user's poor call quality (which you observed using per-user call analytics) is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="58857-111">CQD は、個々の通話エクスペリエンスと、Teams または Skype for Business を使用して行われた通話の全体的な品質の両方をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="58857-111">CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business.</span></span> <span data-ttu-id="58857-112">CQD では、全体的なパターンが明らかになる可能性があります。そのため、ネットワーク エンジニアは、情報に基づいた通話品質の評価を行います。</span><span class="sxs-lookup"><span data-stu-id="58857-112">With CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="58857-113">CQD は、全体的な通話品質、サーバーとクライアントのストリーム、クライアントとクライアントのストリーム、音声品質 SLA に関する洞察を提供する通話品質メトリックのレポートを提供 [します](https://go.microsoft.com/fwlink/p/?linkid=846252)。</span><span class="sxs-lookup"><span data-stu-id="58857-113">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![通話品質ダッシュボードのスクリーンショット。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="58857-115">CQD では、建物とエンドポイントの情報をアップロードして、Location-Enhanced レポートを使用して、ユーザーの建物内の通話品質と信頼性を分析することができます。</span><span class="sxs-lookup"><span data-stu-id="58857-115">In CQD, we encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building.</span></span> <span data-ttu-id="58857-116">データを評価して、問題が 1 人のユーザーに分離されているのか、ユーザーの大きなセグメントに影響を与えるのか判断できます。</span><span class="sxs-lookup"><span data-stu-id="58857-116">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span> <span data-ttu-id="58857-117">CQD で作成またはエンドポイント固有のビューを有効にする場合、管理者 [](CQD-upload-tenant-building-data.md)は CQD テナント データアップロード ページで建物またはエンドポイントの情報を **アップロードする必要** があります。</span><span class="sxs-lookup"><span data-stu-id="58857-117">To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](CQD-upload-tenant-building-data.md) on the CQD **Tenant Data Upload** page.</span></span>

![通話品質ダッシュボードの通話品質レポートLocation-Enhancedスクリーンショット。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

<span data-ttu-id="58857-119">Teams のサービス品質[](quality-of-experience-review-guide.md)の管理を担当する Teams 管理者またはサポート エンジニアに詳細なガイダンスを提供する、通話と会議の品質の管理に関する記事をお見逃しなく。</span><span class="sxs-lookup"><span data-stu-id="58857-119">Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide.md) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.</span></span>

## <a name="older-version-of-cqd-cqdlynccom"></a><span data-ttu-id="58857-120">以前のバージョンの CQD (CQD.lync.com)</span><span class="sxs-lookup"><span data-stu-id="58857-120">Older version of CQD (CQD.lync.com)</span></span>

<span data-ttu-id="58857-121">現在のバージョンの CQD ( https://CQD.Teams.microsoft.com) は古いバージョンの CQD ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="58857-121">The current version of CQD (https://CQD.Teams.microsoft.com) is replacing the older version of CQD (https://CQD.lync.com).</span></span> <span data-ttu-id="58857-122">CQD.lync.com (Skype for Business 管理センターから利用できます) は引き続き使用できますが、2020 年 7 月 1 日現在、CQD からのデータが使用されています。Teams.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="58857-122">You can still use CQD.lync.com (available from the Skype for Business admin center), but as of July 1, 2020, it's using the data from CQD.Teams.microsoft.com.</span></span> <span data-ttu-id="58857-123">このサイトへのアクセスは間もなく CQD.lync.com されますので、CQD に移動する必要があります。Teams.microsoft.com まだ行っていない場合は、この設定を行います。</span><span class="sxs-lookup"><span data-stu-id="58857-123">We'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58857-124">2020 年 7 月 1 日の現在、古い CQD (CQD.lync.com) の建物やクエリ のデータは表示または変更できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="58857-124">As of July 1, 2020, you can no longer view or modify your building or query data from the old CQD (CQD.lync.com).</span></span> <span data-ttu-id="58857-125">このデータを引き続き移行していない CQD.lync.com 場合は、サポート チケットを記録します。</span><span class="sxs-lookup"><span data-stu-id="58857-125">If you haven't already migrated this data from CQD.lync.com and still need it, log a support ticket.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="58857-126">Power BI を使用して CQD データを分析する</span><span class="sxs-lookup"><span data-stu-id="58857-126">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="58857-127">2020 年 1 月の新機能: [CQD 用の Power BI クエリ テンプレートをダウンロードします](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="58857-127">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="58857-128">カスタマイズ可能な Power BI テンプレートを使用して、CQD データを分析およびレポートできます。</span><span class="sxs-lookup"><span data-stu-id="58857-128">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="58857-129">詳細 [については、「Power BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58857-129">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>



## <a name="related-topics"></a><span data-ttu-id="58857-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="58857-130">Related topics</span></span>

[<span data-ttu-id="58857-131">Teams の通話品質の向上と監視</span><span class="sxs-lookup"><span data-stu-id="58857-131">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="58857-132">通話品質ダッシュボード (CQD) を設定する</span><span class="sxs-lookup"><span data-stu-id="58857-132">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="58857-133">テナントと建物のデータをアップロードする</span><span class="sxs-lookup"><span data-stu-id="58857-133">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="58857-134">CQD データとレポート</span><span class="sxs-lookup"><span data-stu-id="58857-134">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="58857-135">CQD を使用して通話と会議の品質を管理する</span><span class="sxs-lookup"><span data-stu-id="58857-135">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="58857-136">CQD で使用できるディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="58857-136">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="58857-137">CQD でのストリームの分類</span><span class="sxs-lookup"><span data-stu-id="58857-137">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="58857-138">Power BI を使用して CQD データを分析する</span><span class="sxs-lookup"><span data-stu-id="58857-138">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)


[<span data-ttu-id="58857-139">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="58857-139">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)