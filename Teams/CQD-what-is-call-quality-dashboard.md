---
title: 通話品質ダッシュボード (CQD) とは何ですか?
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
description: 通話品質ダッシュボード (CQD) について説明し、それを使用して Microsoft Teams の会議と通話の品質に関するレポートを表示する方法について説明します。
ms.openlocfilehash: 9ba1956533887314a9ffa7ad994cbb4c81ffe103
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583486"
---
# <a name="what-is-call-quality-dashboard-cqd"></a><span data-ttu-id="78833-103">通話品質ダッシュボード (CQD) とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="78833-103">What is Call Quality Dashboard (CQD)?</span></span>

<span data-ttu-id="78833-104">Microsoft 通話品質ダッシュボード (CQD)- [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) -Microsoft Teams、skype For Business Online、skype For Business Server 2019 で、**組織全体のレベル**で通話と会議の品質を示します。</span><span class="sxs-lookup"><span data-stu-id="78833-104">The Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

  
<span data-ttu-id="78833-105">CQD の最新バージョンには、[ほぼリアルタイム (NRT) データフィード](CQD-data-and-reports.md)が含まれています。つまり、通話の終了後30分以内に CQD で通話記録を利用できます。</span><span class="sxs-lookup"><span data-stu-id="78833-105">The latest version of CQD features a [near-real-time (NRT) data feed](CQD-data-and-reports.md), which means that call records are available in CQD within 30 minutes of the end of a call.</span></span>

<span data-ttu-id="78833-106">CQD には、[エンドユーザーを特定できる情報 (euii) データ](CQD-data-and-reports.md#euii-data)が含まれていますが、 [Microsoft 365 全体の euii](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)と同じ方法で管理されます。</span><span class="sxs-lookup"><span data-stu-id="78833-106">Wherever CQD includes [end-user identifiable information (EUII) data](CQD-data-and-reports.md#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="78833-107">CQD は、チーム管理者、Skype for Business 管理者、およびネットワークエンジニアが組織全体のレベルで通話と会議の品質を監視できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="78833-107">CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level.</span></span> <span data-ttu-id="78833-108">CQD を使用して、パフォーマンスを向上するために**ネットワークの最適化**を支援します。</span><span class="sxs-lookup"><span data-stu-id="78833-108">You'll use CQD to help you **optimize your network** to drive performance quality.</span></span> <span data-ttu-id="78833-109">**特定のユーザー**の通話と会議の情報を表示する必要がある場合は、CQD データとユーザーごとの[通話分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)を組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="78833-109">When you need to look into call and meeting information for a **specific user**, use CQD data in conjunction with per-user [call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>

<span data-ttu-id="78833-110">たとえば、CQD を使用すると、ユーザーの低品質の通話音質 (ユーザーごとの通話分析を使用した場合) が、ネットワークの問題が原因であることを確認できます。これは、他の多くのユーザーにも影響します。</span><span class="sxs-lookup"><span data-stu-id="78833-110">For example, using CQD, you can determine that a user's poor call quality (which you observed using per-user call analytics) is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="78833-111">CQD は、個々の通話環境と、Teams または Skype for Business を使って発信した通話の全体的な品質を把握します。</span><span class="sxs-lookup"><span data-stu-id="78833-111">CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business.</span></span> <span data-ttu-id="78833-112">CQD を使用すると、全体的なパターンが明らかになることがあります。これにより、ネットワークエンジニアは、通話品質について通知を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="78833-112">With CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="78833-113">CQD は通話品質指標のレポートを提供します。これにより、全体的な通話品質、サーバークライアントストリーム、クライアントクライアントストリーム、音声品質[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)を把握できます。</span><span class="sxs-lookup"><span data-stu-id="78833-113">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![通話品質ダッシュボードのスクリーンショット。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="78833-115">CQD では、建物やエンドポイントの情報をアップロードすることをお勧めします。これにより、場所で強化されたレポートを使用して、ユーザーの建物内の通話品質と信頼性を分析することができます。</span><span class="sxs-lookup"><span data-stu-id="78833-115">In CQD, we encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building.</span></span> <span data-ttu-id="78833-116">問題が1人のユーザーに限定されているか、またはユーザーの大きなセグメントに影響するかを判断するために、データを評価することができます。</span><span class="sxs-lookup"><span data-stu-id="78833-116">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span> <span data-ttu-id="78833-117">CQD で建物またはエンドポイント固有のビューを有効にするには、管理者が、CQD**テナントデータアップロード**ページで[建物またはエンドポイントの情報をアップロード](CQD-upload-tenant-building-data.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78833-117">To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](CQD-upload-tenant-building-data.md) on the CQD **Tenant Data Upload** page.</span></span>

![通話品質ダッシュボードの場所の拡張されたレポートのスクリーンショット。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

<span data-ttu-id="78833-119">チームの管理者またはサポートエンジニアがチームのサービス品質を管理するための詳細なガイダンスを提供[している skype 通話と会議の品質](quality-of-experience-review-guide.md)に関する記事をお見逃しなく。</span><span class="sxs-lookup"><span data-stu-id="78833-119">Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide.md) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.</span></span>

## <a name="older-version-of-cqd-cqdlynccom"></a><span data-ttu-id="78833-120">以前のバージョンの CQD (CQD.lync.com)</span><span class="sxs-lookup"><span data-stu-id="78833-120">Older version of CQD (CQD.lync.com)</span></span>

<span data-ttu-id="78833-121">CQD の現在のバージョン ( https://CQD.Teams.microsoft.com) CQD の旧バージョンは置き換えられ https://CQD.lync.com) ます。</span><span class="sxs-lookup"><span data-stu-id="78833-121">The current version of CQD (https://CQD.Teams.microsoft.com) is replacing the older version of CQD (https://CQD.lync.com).</span></span> <span data-ttu-id="78833-122">引き続き CQD.lync.com (Skype for Business 管理センターから利用可能) を使用できますが、2020年7月1日の時点では、CQD のデータを使用しています。Teams.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="78833-122">You can still use CQD.lync.com (available from the Skype for Business admin center), but as of July 1, 2020, it's using the data from CQD.Teams.microsoft.com.</span></span> <span data-ttu-id="78833-123">CQD.lync.com へのアクセスをすぐにオフにします。そのため、CQD に移動してください。まだインストールしていない場合は、Teams.microsoft.com します。</span><span class="sxs-lookup"><span data-stu-id="78833-123">We'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78833-124">2020年7月1日以降、古い CQD (CQD.lync.com) から文書作成またはクエリのデータを表示または変更することはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="78833-124">As of July 1, 2020, you can no longer view or modify your building or query data from the old CQD (CQD.lync.com).</span></span> <span data-ttu-id="78833-125">CQD.lync.com からまだこのデータを移行しておらず、引き続き必要な場合は、サポートチケットを記録してください。</span><span class="sxs-lookup"><span data-stu-id="78833-125">If you haven't already migrated this data from CQD.lync.com and still need it, log a support ticket.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="78833-126">Power BI を使用して CQD データを分析する</span><span class="sxs-lookup"><span data-stu-id="78833-126">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="78833-127">2020年1月の新[機能: POWER BI クエリテンプレートをダウンロードして CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)します。</span><span class="sxs-lookup"><span data-stu-id="78833-127">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="78833-128">CQD データの分析と報告に使用できる、カスタマイズ可能な Power BI テンプレート。</span><span class="sxs-lookup"><span data-stu-id="78833-128">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="78833-129">詳細については、「 [POWER BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78833-129">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>



## <a name="related-topics"></a><span data-ttu-id="78833-130">関連トピック</span><span class="sxs-lookup"><span data-stu-id="78833-130">Related topics</span></span>

[<span data-ttu-id="78833-131">Teams の通話品質を向上させて監視する</span><span class="sxs-lookup"><span data-stu-id="78833-131">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="78833-132">通話品質ダッシュボード (CQD) を設定する</span><span class="sxs-lookup"><span data-stu-id="78833-132">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="78833-133">テナントのアップロードとデータの構築</span><span class="sxs-lookup"><span data-stu-id="78833-133">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="78833-134">CQD データとレポート</span><span class="sxs-lookup"><span data-stu-id="78833-134">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="78833-135">CQD を使用して通話と会議の品質を管理する</span><span class="sxs-lookup"><span data-stu-id="78833-135">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="78833-136">CQD で使用できるディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="78833-136">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="78833-137">CQD でのストリームの分類</span><span class="sxs-lookup"><span data-stu-id="78833-137">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="78833-138">Power BI を使用して CQD データを分析する</span><span class="sxs-lookup"><span data-stu-id="78833-138">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)


[<span data-ttu-id="78833-139">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="78833-139">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)