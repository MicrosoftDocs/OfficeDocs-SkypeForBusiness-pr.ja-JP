---
title: ビジネス サーバーの Skype でのメディア品質診断レポート
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
description: '概要: は、ビジネスのサーバーに、Skype でメディア品質診断レポートについて説明します。'
ms.openlocfilehash: a7861d60e9108dcf599c5cecee9a678248715e44
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197535"
---
# <a name="media-quality-diagnostic-reports-in-skype-for-business-server"></a><span data-ttu-id="7e369-103">ビジネス サーバーの Skype でのメディア品質診断レポート</span><span class="sxs-lookup"><span data-stu-id="7e369-103">Media Quality Diagnostic Reports in Skype for Business Server</span></span>
 
<span data-ttu-id="7e369-104">**の概要:** Business Server には、Skype でメディア品質診断レポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7e369-104">**Summary:** Learn about the Media Quality Diagnostic Reports in Skype for Business Server.</span></span>
  
<span data-ttu-id="7e369-105">メディア品質診断レポートは、通話の品質についての情報、および失敗した通話についての診断とトラブルシューティングの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="7e369-105">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="7e369-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7e369-106">In this section</span></span>

- <span data-ttu-id="7e369-107">[ビジネス サーバーの Skype でのメディア品質概要レポート](summary.md)全体的な品質データを提供する別のエンドポイントの種類など、エンタープライズ VoIP ピア ツー ピア通話、エンタープライズ VoIP 電話会議、および利用するには、少なくとも部分的に、一般に公衆交換電話網 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="7e369-107">[Media Quality Summary Report in Skype for Business Server](summary.md) Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>
    
- <span data-ttu-id="7e369-108">[Skype ビジネス サーバー用のメディアの品質の比較レポート](comparison.md)音声通話 (ワイヤード (有線) 接続経由で行われた呼び出しとワイヤレス ネットワーク経由で行われた呼び出しなど) のさまざまな種類の呼び出しの比較品質評価の値を提供します。</span><span class="sxs-lookup"><span data-stu-id="7e369-108">[Media Quality Comparison Report in Skype for Business Server](comparison.md) Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>
    
- <span data-ttu-id="7e369-109">[Skype ビジネス サーバー用のサーバー パフォーマンス レポート](server-performance.md)このような重要な品質の評価指標の低下、パケット ロス、および変位の測定値に基づいて、ほとんどの問題が発生したサーバーを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7e369-109">[Server Performance Report in Skype for Business Server](server-performance.md) Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="7e369-110">[Skype ビジネス サーバーの場所のレポート](location-report.md)ネットワーク上の場所とそれぞれの場所で発生する通話のメディア品質の概要の一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="7e369-110">[Location Report in Skype for Business Server](location-report.md) Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="7e369-111">このレポートのために、場所は IP サブネットに基づいています。</span><span class="sxs-lookup"><span data-stu-id="7e369-111">For purposes of this report, locations are based on IP subnets.</span></span>
    
- <span data-ttu-id="7e369-112">[Skype ビジネス サーバー用のデバイス ・ レポート](device-report.md)エンタープライズ VoIP 通話で使用されているデバイスの概要には、デバイスで、呼び出しの平均のメディアの品質が含まれていますが用意されています。</span><span class="sxs-lookup"><span data-stu-id="7e369-112">[Device Report in Skype for Business Server](device-report.md) Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>
    
- <span data-ttu-id="7e369-113">[Skype ビジネス サーバーの一覧のレポートを呼び出す](call-list-report-0.md)電話をかけたり、組織内で受信したかに関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="7e369-113">[Call List Report in Skype for Business Server](call-list-report-0.md) Provides detailed information about phone calls made or received within your organization.</span></span>
    
- <span data-ttu-id="7e369-114">[ビジネス サーバーの Skype の詳細レポートを呼び出す](call-detail-report.md)行われたか、組織内で受信した電話の呼び出しに関する詳細な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="7e369-114">[Call Detail Report in Skype for Business Server](call-detail-report.md) Provides detailed information about phone calls made from or received within your organization.</span></span>
    
- <span data-ttu-id="7e369-115">[Skype ビジネス サーバーでのサーバー メディア品質傾向レポート](server-media-quality-trend-report.md)呼び出し音量、不適切な呼び出しの割合、パケット損失、ジッターなどの高品質なエクスペリエンスのメトリックの最大 5 台のサーバをグラフィカルに比較するための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="7e369-115">[Server Media Quality Trend Report in Skype for Business Server](server-media-quality-trend-report.md) Provides a way for you to graphically compare up to five servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="7e369-116">[Skype ビジネス サーバー用のメディアの品質評価基準の配布レポート](media-quality-metrics-distribution-report.md)ジッターやパケット損失などの高品質なエクスペリエンスの指標の分布の値を示すグラフが用意されています。</span><span class="sxs-lookup"><span data-stu-id="7e369-116">[The Media Quality Metrics Distribution Report in Skype for Business Server](media-quality-metrics-distribution-report.md) Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>
    
- <span data-ttu-id="7e369-117">[Skype ビジネス サーバーの場所の傾向レポート](location-trend-report.md)ネットワーク上の場所の通話品質のトレンドに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="7e369-117">[Location Trend Report in Skype for Business Server](location-trend-report.md) Provides call quality trend information for network locations.</span></span>
    

