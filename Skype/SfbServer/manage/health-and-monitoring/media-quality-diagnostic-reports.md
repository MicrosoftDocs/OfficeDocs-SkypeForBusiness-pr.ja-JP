---
title: Skype for Business Server のメディア品質診断レポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
description: '概要: Skype for Business Server のメディア品質診断レポートについて説明します。'
ms.openlocfilehash: d4ea9c56406799a6a053092e7b8ca16f44505ce7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280034"
---
# <a name="media-quality-diagnostic-reports-in-skype-for-business-server"></a><span data-ttu-id="ad4e5-103">Skype for Business Server のメディア品質診断レポート</span><span class="sxs-lookup"><span data-stu-id="ad4e5-103">Media Quality Diagnostic Reports in Skype for Business Server</span></span>
 
<span data-ttu-id="ad4e5-104">**概要:** Skype for Business Server のメディア品質診断レポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ad4e5-104">**Summary:** Learn about the Media Quality Diagnostic Reports in Skype for Business Server.</span></span>
  
<span data-ttu-id="ad4e5-105">メディア品質診断レポートは、通話の品質についての情報、および失敗した通話についての診断とトラブルシューティングの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ad4e5-105">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="ad4e5-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ad4e5-106">In this section</span></span>

- <span data-ttu-id="ad4e5-107">[Skype For Business Server のメディア品質サマリーレポート](summary.md)エンタープライズボイスピアツーピア通話、エンタープライズボイス会議通話、電話会議 (PSTN) 上の少なくとも一部に依存する通話など、エンドポイントの種類ごとに全体的な品質データを提供します。</span><span class="sxs-lookup"><span data-stu-id="ad4e5-107">[Media Quality Summary Report in Skype for Business Server](summary.md) Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>
    
- <span data-ttu-id="ad4e5-108">[Skype For Business Server のメディア品質比較レポート](comparison.md)さまざまな種類の音声通話 (ワイヤレスネットワーク経由で発信された通話、有線接続を経由した通話など) について、通話音質の値の比較が提供されます。</span><span class="sxs-lookup"><span data-stu-id="ad4e5-108">[Media Quality Comparison Report in Skype for Business Server](comparison.md) Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>
    
- <span data-ttu-id="ad4e5-109">[Skype For Business server のサーバーパフォーマンスレポート](server-performance.md)パフォーマンスの低下、パケット損失、ジッタなどの主要品質指標の測定値に基づいて、問題が発生したサーバーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad4e5-109">[Server Performance Report in Skype for Business Server](server-performance.md) Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="ad4e5-110">[Skype For Business Server の場所レポート](location-report.md)ネットワーク上の場所の一覧と、各場所で発生した通話のメディア品質の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="ad4e5-110">[Location Report in Skype for Business Server](location-report.md) Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="ad4e5-111">このレポートの目的として、場所は IP サブネットに基づいています。</span><span class="sxs-lookup"><span data-stu-id="ad4e5-111">For purposes of this report, locations are based on IP subnets.</span></span>
    
- <span data-ttu-id="ad4e5-112">[Skype For Business Server のデバイスレポート](device-report.md)エンタープライズ音声通話に使用されるデバイスの概要と、デバイス別の通話の平均メディア品質が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ad4e5-112">[Device Report in Skype for Business Server](device-report.md) Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>
    
- <span data-ttu-id="ad4e5-113">[Skype For Business Server の通話リストレポート](call-list-report-0.md)組織内で発信または受信した電話の詳細情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="ad4e5-113">[Call List Report in Skype for Business Server](call-list-report-0.md) Provides detailed information about phone calls made or received within your organization.</span></span>
    
- <span data-ttu-id="ad4e5-114">[Skype For Business Server の通話詳細レポート](call-detail-report.md)組織内で発信または受信した電話の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="ad4e5-114">[Call Detail Report in Skype for Business Server](call-detail-report.md) Provides detailed information about phone calls made from or received within your organization.</span></span>
    
- <span data-ttu-id="ad4e5-115">[Skype For Business server のサーバーメディア品質トレンドレポート](server-media-quality-trend-report.md)通話音量、低品質の通話率、パケット損失、ジッタなど、さまざまなエクスペリエンスのメトリックについて、最大5台のサーバーを視覚的に比較するための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="ad4e5-115">[Server Media Quality Trend Report in Skype for Business Server](server-media-quality-trend-report.md) Provides a way for you to graphically compare up to five servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="ad4e5-116">[Skype For Business Server でのメディア品質指標の配布レポート](media-quality-metrics-distribution-report.md)ジッタ、パケット損失など、質の高いメトリックの分布値を示すグラフを提供します。</span><span class="sxs-lookup"><span data-stu-id="ad4e5-116">[The Media Quality Metrics Distribution Report in Skype for Business Server](media-quality-metrics-distribution-report.md) Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>
    
- <span data-ttu-id="ad4e5-117">[Skype For Business Server の位置情報トレンドレポート](location-trend-report.md)ネットワーク上の場所の通話品質の傾向情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ad4e5-117">[Location Trend Report in Skype for Business Server](location-trend-report.md) Provides call quality trend information for network locations.</span></span>
    

