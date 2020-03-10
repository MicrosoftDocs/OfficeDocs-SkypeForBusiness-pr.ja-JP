---
title: Power BI を使用して Microsoft Teams の CQD データを分析する
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Power BI を使用して、Microsoft Teams の CQD データを分析します。
ms.openlocfilehash: 155bde0373880befc770d745ca246b76d4c63eec
ms.sourcegitcommit: 543f650ad4aff73bccfe7a60b66fb944b4e3c119
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2020
ms.locfileid: "42572895"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a><span data-ttu-id="a4b73-103">Power BI を使用して Microsoft Teams の CQD データを分析する</span><span class="sxs-lookup"><span data-stu-id="a4b73-103">Use Power BI to analyze CQD data for Microsoft Teams</span></span>

<span data-ttu-id="a4b73-104">2020年1月の新[機能: POWER BI クエリテンプレートをダウンロードして CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)します。</span><span class="sxs-lookup"><span data-stu-id="a4b73-104">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="a4b73-105">CQD データの分析と報告に使用できる、カスタマイズ可能な Power BI テンプレート。</span><span class="sxs-lookup"><span data-stu-id="a4b73-105">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="a4b73-106">Teams の CQD レポートの場合、Power BI を使ってデータのクエリやレポートを行う場合は、CQD Power BI テンプレートをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="a4b73-106">For CQD reports in Teams, if you’d rather use Power BI to query and report your data, download our CQD Power BI templates.</span></span> <span data-ttu-id="a4b73-107">Power BI でテンプレートを開くと、CQD 管理者の資格情報でサインインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="a4b73-107">When you open the templates in Power BI, you’ll be prompted to sign in with your CQD admin credentials.</span></span> <span data-ttu-id="a4b73-108">これらのクエリテンプレートをカスタマイズして、Power BI ライセンスと CQD の管理者権限を持つ組織内のすべてのユーザーに配布することができます。</span><span class="sxs-lookup"><span data-stu-id="a4b73-108">You can customize these query templates and distribute them to anyone in your organization who has a Power BI license and CQD admin permissions.</span></span>

<span data-ttu-id="a4b73-109">これらの .PBIX ファイルを使用するには、その前に、[ダウンロード](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)に含まれている[Microsoft CQD の Power BI コネクタをインストール](CQD-Power-BI-connector.md)する必要があり*ます。*</span><span class="sxs-lookup"><span data-stu-id="a4b73-109">Before you can use these PBIX files, you’ll need to [Install the Power BI Connector for Microsoft CQD](CQD-Power-BI-connector.md) using the *MicrosoftCallQuality.pqx* file included in the [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


|  |  |
|---------|---------|
|<span data-ttu-id="a4b73-110">CQD のヘルプデスクのレポート .pbix</span><span class="sxs-lookup"><span data-stu-id="a4b73-110">CQD Helpdesk Report.pbix</span></span>     |<span data-ttu-id="a4b73-111">このレポートは、ビルディングと EUII のデータを統合することを目的としています。このレポートは、1人のユーザーとの間で、そのユーザーの通話品質の低下 (たとえば、ネットワークの問題が発生している建物内にいるなど) を見つけることができるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="a4b73-111">Integrating building and EUII data, this report is designed to let you drill up from a single user to find the upstream root cause of poor call quality for that user (for example, the user is in a building that’s experiencing network problems).</span></span>         |
|<span data-ttu-id="a4b73-112">CQD の場所の拡張レポート .pbix</span><span class="sxs-lookup"><span data-stu-id="a4b73-112">CQD Location Enhanced Report.pbix</span></span>     | <span data-ttu-id="a4b73-113">CQD SPD location レポートを再想像します。</span><span class="sxs-lookup"><span data-stu-id="a4b73-113">Re-imagining CQD SPD location reports.</span></span> <span data-ttu-id="a4b73-114">9つのレポートが含まれており、通話品質の提供、WiFi、信頼性の構築、また、建物またはユーザーごとの追加のドリルダウン thrus での通話 (RMC) 情報の評価を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a4b73-114">Includes 9 reports, providing Call Quality, Building WiFi, Reliability, and Rate My Call (RMC) information with additional drill-thrus by Building or by User.</span></span>        |
|<span data-ttu-id="a4b73-115">CQD モバイルデバイスのレポート .pbix</span><span class="sxs-lookup"><span data-stu-id="a4b73-115">CQD Mobile Device Report.pbix</span></span>     | <span data-ttu-id="a4b73-116">通話品質、信頼性、通話料金などのモバイルデバイスユーザーに向けて、明確に調整された洞察を提供します。</span><span class="sxs-lookup"><span data-stu-id="a4b73-116">Provides insights specifically tuned towards mobile device users, including Call Quality, Reliability, and Rate My Call.</span></span> <span data-ttu-id="a4b73-117">モバイルネットワーク、WiFi ネットワーク、モバイルオペレーティングシステムレポート (Android、iOS) を表示します。</span><span class="sxs-lookup"><span data-stu-id="a4b73-117">View mobile network, WiFi network, and mobile operating system reports (Android, iOS).</span></span>        |
|<span data-ttu-id="a4b73-118">CQD PSTN ダイレクトルーティングレポート .pbix</span><span class="sxs-lookup"><span data-stu-id="a4b73-118">CQD PSTN Direct Routing Report.pbix</span></span>     |<span data-ttu-id="a4b73-119">直接ルーティングを経由する PSTN 通話に固有の洞察を提供します。</span><span class="sxs-lookup"><span data-stu-id="a4b73-119">Provides insights specific for PSTN calls that go through Direct Routing.</span></span> <span data-ttu-id="a4b73-120">詳細については、「 [CQD PSTN ダイレクトルーティングレポートを使用](CQD-PSTN-report.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4b73-120">To learn more, read [Using the CQD PSTN Direct Routing Report](CQD-PSTN-report.md).</span></span>         |
|<span data-ttu-id="a4b73-121">CQD Summary レポート .pbix</span><span class="sxs-lookup"><span data-stu-id="a4b73-121">CQD Summary Report.pbix</span></span>     |<span data-ttu-id="a4b73-122">視覚エフェクトの向上、向上したプレゼンテーション、情報の密度の向上、日付のローリング。</span><span class="sxs-lookup"><span data-stu-id="a4b73-122">Better visualizations, improved presentation, increased information density, and rolling dates.</span></span> <span data-ttu-id="a4b73-123">これらのレポートを使用すると、値を簡単に識別することができます。</span><span class="sxs-lookup"><span data-stu-id="a4b73-123">These reports make it easier to identifier outliers.</span></span> <span data-ttu-id="a4b73-124">使いやすいインタラクティブな地図を使用して、場所別の通話品質を詳しく調べることができます。</span><span class="sxs-lookup"><span data-stu-id="a4b73-124">Drill into call quality by location with an easy-to-use interactive map.</span></span> <span data-ttu-id="a4b73-125">9新しいレポート:</span><span class="sxs-lookup"><span data-stu-id="a4b73-125">9 new reports:</span></span></p><span data-ttu-id="a4b73-126">-全体的な品質</span><span class="sxs-lookup"><span data-stu-id="a4b73-126">- Quality Overall</span></span><br><span data-ttu-id="a4b73-127">-信頼性全体</span><span class="sxs-lookup"><span data-stu-id="a4b73-127">- Reliability Overall</span></span><br><span data-ttu-id="a4b73-128">-RMC (通話の評価) 全体</span><span class="sxs-lookup"><span data-stu-id="a4b73-128">- RMC (Rate My Call) Overall</span></span><br><span data-ttu-id="a4b73-129">-会議の品質</span><span class="sxs-lookup"><span data-stu-id="a4b73-129">- Conference Quality</span></span><br><span data-ttu-id="a4b73-130">-P2P の品質</span><span class="sxs-lookup"><span data-stu-id="a4b73-130">- P2P Quality</span></span><br><span data-ttu-id="a4b73-131">-会議の信頼性</span><span class="sxs-lookup"><span data-stu-id="a4b73-131">- Conference Reliability</span></span><br><span data-ttu-id="a4b73-132">-P2P の信頼性</span><span class="sxs-lookup"><span data-stu-id="a4b73-132">- P2P Reliability</span></span><br><span data-ttu-id="a4b73-133">-電話会議 RMC</span><span class="sxs-lookup"><span data-stu-id="a4b73-133">- Conference RMC</span></span><br><span data-ttu-id="a4b73-134">-P2P RMC</span><span class="sxs-lookup"><span data-stu-id="a4b73-134">- P2P RMC</span></span>         |
|<span data-ttu-id="a4b73-135"><strong>(New!)</strong>CQD Teams の使用状況レポート .pbix</span><span class="sxs-lookup"><span data-stu-id="a4b73-135"><strong>(New!)</strong>CQD Teams Utilization Report.pbix</span></span>     | <span data-ttu-id="a4b73-136">組織内のユーザーが Teams をどのように使用しているかを示し、その量を示します。</span><span class="sxs-lookup"><span data-stu-id="a4b73-136">Shows how users in your organization are using Teams and how much.</span></span> <span data-ttu-id="a4b73-137">詳細については、「 [CQD POWER BI レポートを使用して Microsoft Teams の利用状況を表示](CQD-teams-utilization-report.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4b73-137">To learn more, read [Use CQD Power BI report to view Microsoft Teams utilization](CQD-teams-utilization-report.md).</span></span>        |
|<span data-ttu-id="a4b73-138">CQD ユーザーフィードバック (通話の評価) レポート .pbix</span><span class="sxs-lookup"><span data-stu-id="a4b73-138">CQD User Feedback (Rate My Call) Report.pbix</span></span>     | <span data-ttu-id="a4b73-139">組織への通話をサポートするために簡単に使用できる方法で、通話データの料金が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4b73-139">Shows Rate My Call data in a way that you can easily use to help support calling for your organization.</span></span> <span data-ttu-id="a4b73-140">Verbatims との相互参照により、エンドユーザーの教育機会を特定します。</span><span class="sxs-lookup"><span data-stu-id="a4b73-140">Cross reference with verbatims to identify end user education opportunities.</span></span>        |


## <a name="related-topics"></a><span data-ttu-id="a4b73-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4b73-141">Related topics</span></span>

[<span data-ttu-id="a4b73-142">通話品質ダッシュボードで利用できるディメンションとメジャー</span><span class="sxs-lookup"><span data-stu-id="a4b73-142">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="a4b73-143">通話品質ダッシュボードでのストリームの分類</span><span class="sxs-lookup"><span data-stu-id="a4b73-143">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="a4b73-144">Skype for Business の通話分析をセットアップする</span><span class="sxs-lookup"><span data-stu-id="a4b73-144">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="a4b73-145">通話分析を使用して低品質の通話をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="a4b73-145">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="a4b73-146">通話分析および通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="a4b73-146">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)
 