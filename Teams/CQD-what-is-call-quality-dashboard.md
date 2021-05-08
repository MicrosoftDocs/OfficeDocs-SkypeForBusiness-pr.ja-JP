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
description: 通話品質ダッシュボード (CQD) と、このダッシュボードを使用して、会議や通話の品質に関するレポートを表示する方法についてMicrosoft Teams。
ms.openlocfilehash: d262449394d9ad880d13897988e40e26dd98578c
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593835"
---
# <a name="what-is-call-quality-dashboard-cqd"></a><span data-ttu-id="a3f05-103">通話品質ダッシュボード (CQD) とは</span><span class="sxs-lookup"><span data-stu-id="a3f05-103">What is Call Quality Dashboard (CQD)?</span></span>

<span data-ttu-id="a3f05-104">Microsoft 通話品質ダッシュボード (CQD) [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - Microsoft Teams、Skype for Business Online、および Skype for Business Server 2019 の通話と会議の品質を組織全体で表示します。</span><span class="sxs-lookup"><span data-stu-id="a3f05-104">The Microsoft Call Quality Dashboard (CQD) - [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) - shows call and meeting quality, at an **org-wide level**, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

  
<span data-ttu-id="a3f05-105">最新バージョンの CQD では、ほぼリアルタイム [(NRT)](CQD-data-and-reports.md)のデータ フィードが備わっています。つまり、呼び出しの終了から 30 分以内に CQD で通話レコードを利用できます。</span><span class="sxs-lookup"><span data-stu-id="a3f05-105">The latest version of CQD features a [near-real-time (NRT) data feed](CQD-data-and-reports.md), which means that call records are available in CQD within 30 minutes of the end of a call.</span></span>

<span data-ttu-id="a3f05-106">CQD にエンド ユーザー識別可能な[情報 (EUII)](CQD-data-and-reports.md#euii-data)データが含まれる場合は、 全体を通じて EUII と同じ方法[で管理Microsoft 365。](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)</span><span class="sxs-lookup"><span data-stu-id="a3f05-106">Wherever CQD includes [end-user identifiable information (EUII) data](CQD-data-and-reports.md#euii-data), it's managed in the same way as [EUII throughout Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

<span data-ttu-id="a3f05-107">CQD は、組織全体のTeams、Skype for Business 管理者、ネットワーク エンジニアが通話と会議の品質を監視するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a3f05-107">CQD is designed to help Teams admins, Skype for Business admins, and network engineers monitor call and meeting quality at an org-wide level.</span></span> <span data-ttu-id="a3f05-108">CQD を使用して、ネットワークを最適化 **して** パフォーマンスの品質を向上させます。</span><span class="sxs-lookup"><span data-stu-id="a3f05-108">You'll use CQD to help you **optimize your network** to drive performance quality.</span></span> <span data-ttu-id="a3f05-109">特定のユーザーの通話と会議の情報を調ぶ必要がある場合は、ユーザーごとの呼び出し分析と組み合わせて CQD データ[を使用します](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="a3f05-109">When you need to look into call and meeting information for a **specific user**, use CQD data in conjunction with per-user [call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>

<span data-ttu-id="a3f05-110">たとえば、CQD を使用すると、ユーザーの低品質 (ユーザーごとの通話分析を使用して観察した) が、他の多くのユーザーにも影響を与えるネットワークの問題が原因と判断できます。</span><span class="sxs-lookup"><span data-stu-id="a3f05-110">For example, using CQD, you can determine that a user's poor call quality (which you observed using per-user call analytics) is due to a network issue that also affects many other users.</span></span> <span data-ttu-id="a3f05-111">CQD は、個々の呼び出しエクスペリエンスと、Teams または Skype for Business を使用して行われた呼び出しの全体的な品質の両方をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="a3f05-111">CQD captures both the individual call experience and the overall quality of calls made using Teams or Skype for Business.</span></span> <span data-ttu-id="a3f05-112">CQD では、全体的なパターンが明らかになる可能性があります。そのため、ネットワーク エンジニアは、通話品質に関する情報に基づいた評価を行います。</span><span class="sxs-lookup"><span data-stu-id="a3f05-112">With CQD, overall patterns may become apparent, so network engineers can make informed assessments of call quality.</span></span> <span data-ttu-id="a3f05-113">CQD は、全体的な通話品質、サーバー クライアント ストリーム、クライアント クライアント ストリーム、音声品質 SLA に関する分析情報を提供する通話品質メトリックのレポートを提供 [します](https://go.microsoft.com/fwlink/p/?linkid=846252)。</span><span class="sxs-lookup"><span data-stu-id="a3f05-113">CQD provides reports of call quality metrics that give you insight into overall call quality, server-client streams, client-client streams, and voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span> 
  
![通話品質ダッシュボードのスクリーンショット。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

<span data-ttu-id="a3f05-115">CQD では、建物とエンドポイントの情報をアップロードして、Location-Enhanced レポートを使用して、ユーザーの建物内の通話品質と信頼性を分析できます。</span><span class="sxs-lookup"><span data-stu-id="a3f05-115">In CQD, we encourage you to upload building and endpoint information, which lets you use Location-Enhanced Reports to analyze call quality and reliability within a user's building.</span></span> <span data-ttu-id="a3f05-116">データを評価して、問題が 1 人のユーザーに分離されているのか、それともより大きなユーザー セグメントに影響を及ぼすのか判断できます。</span><span class="sxs-lookup"><span data-stu-id="a3f05-116">The data can be assessed to determine if the problem is isolated to a single user or affects a larger segment of users.</span></span> <span data-ttu-id="a3f05-117">CQD で構築ビューまたはエンドポイント固有のビューを有効にするには、[](CQD-upload-tenant-building-data.md)管理者が CQD テナント データの作成またはエンドポイント情報を [CQD テナント データ] ページにアップロードアップロードがあります。</span><span class="sxs-lookup"><span data-stu-id="a3f05-117">To turn on building or endpoint-specific views in CQD, an admin must [upload building or endpoint information](CQD-upload-tenant-building-data.md) on the CQD **Tenant Data Upload** page.</span></span>

![通話品質ダッシュボードの [通話レポート] Location-Enhancedスクリーンショット。](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

<span data-ttu-id="a3f05-119">通話と会議品質の[](quality-of-experience-review-guide.md)管理に関する記事をお見逃しなく。この記事では、Teams でサービス品質の管理を担当する Teams 管理者またはサポート エンジニアに関する詳細なガイダンスを提供しています。</span><span class="sxs-lookup"><span data-stu-id="a3f05-119">Don't miss our [Manage call and meeting quality](quality-of-experience-review-guide.md) article, which offers in-depth guidance for the Teams admin or support engineer responsible for managing service quality in Teams.</span></span>

## <a name="legacy-version-of-cqd-cqdlynccom"></a><span data-ttu-id="a3f05-120">従来のバージョンの CQD (CQD.lync.com)</span><span class="sxs-lookup"><span data-stu-id="a3f05-120">Legacy version of CQD (CQD.lync.com)</span></span>

<span data-ttu-id="a3f05-121">現在のバージョンの CQD ( は https://CQD.Teams.microsoft.com) 、従来のバージョンの CQD ( に置き換えました https://CQD.lync.com) 。</span><span class="sxs-lookup"><span data-stu-id="a3f05-121">The current version of CQD (https://CQD.Teams.microsoft.com) has replaced the legacy version of CQD (https://CQD.lync.com).</span></span> <span data-ttu-id="a3f05-122">引き続き CQD.lync.com (Skype for Business 管理センターから利用可能) を使用できますが、2020 年 7 月 1 日の現在、CQD からのデータが使用されています。Teams.microsoft.com、古い CQD (CQD.lync.com) から建物やクエリ データを表示または変更 CQD.lync.com。</span><span class="sxs-lookup"><span data-stu-id="a3f05-122">You can still use CQD.lync.com (available from the Skype for Business admin center), but as of July 1, 2020, it's using the data from CQD.Teams.microsoft.com and you can no longer view or modify your building or query data from the old CQD (CQD.lync.com).</span></span> <span data-ttu-id="a3f05-123">このデータを移行していない場合は CQD.lync.com、サポート チケットを記録します。</span><span class="sxs-lookup"><span data-stu-id="a3f05-123">If you haven't already migrated this data from CQD.lync.com and still need it, log a support ticket.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3f05-124">2021 年 7 月 31 日より、従来のバージョンの CQD (CQD.lync.com) が廃止されます。</span><span class="sxs-lookup"><span data-stu-id="a3f05-124">As of July 31, 2021, we are retiring the legacy version of CQD (CQD.lync.com).</span></span> <span data-ttu-id="a3f05-125">その日付が終わり、自動的に CQD にリダイレクトされます。Teams.microsoft.com にアクセスしようとすると、CQD.lync.com、および見落とされていない建物またはクエリ データは失われます。</span><span class="sxs-lookup"><span data-stu-id="a3f05-125">After that date, you will be automatically redirected to CQD.Teams.microsoft.com when attempting to access CQD.lync.com, and any unmigrated building or query data will be lost.</span></span>

## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="a3f05-126">CQD Power BI分析するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3f05-126">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="a3f05-127">2020 年 1 月の新機能: [CQD Power BIテンプレートをダウンロードします](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="a3f05-127">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="a3f05-128">カスタマイズ可能Power BI、CQD データの分析とレポートに使用できるテンプレートです。</span><span class="sxs-lookup"><span data-stu-id="a3f05-128">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="a3f05-129">詳細[については、「Power BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3f05-129">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>



## <a name="related-topics"></a><span data-ttu-id="a3f05-130">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a3f05-130">Related topics</span></span>

[<span data-ttu-id="a3f05-131">Teams の通話品質の向上と監視</span><span class="sxs-lookup"><span data-stu-id="a3f05-131">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="a3f05-132">通話品質ダッシュボード (CQD) を設定する</span><span class="sxs-lookup"><span data-stu-id="a3f05-132">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="a3f05-133">アップロードとデータの構築</span><span class="sxs-lookup"><span data-stu-id="a3f05-133">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="a3f05-134">CQD データとレポート</span><span class="sxs-lookup"><span data-stu-id="a3f05-134">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="a3f05-135">CQD を使用して通話と会議の品質を管理する</span><span class="sxs-lookup"><span data-stu-id="a3f05-135">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="a3f05-136">CQD で使用可能なディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="a3f05-136">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="a3f05-137">CQD のストリーム分類</span><span class="sxs-lookup"><span data-stu-id="a3f05-137">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="a3f05-138">CQD Power BI分析するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3f05-138">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)


[<span data-ttu-id="a3f05-139">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a3f05-139">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
