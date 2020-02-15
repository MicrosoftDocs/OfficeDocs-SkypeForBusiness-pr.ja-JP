---
title: 'Lync Server 2013: メディア品質診断レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Diagnostic Reports
ms:assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615044(v=OCS.15)
ms:contentKeyID: 48185935
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 257346792c7f1e3d815942c7eecacd16cba9194e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="208a3-102">Lync Server 2013 のメディア品質診断レポート</span><span class="sxs-lookup"><span data-stu-id="208a3-102">Media Quality Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="208a3-103">_**トピックの最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="208a3-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="208a3-104">メディア品質診断レポートは、通話の品質についての情報、および失敗した通話についての診断とトラブルシューティングの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="208a3-104">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="208a3-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="208a3-105">In This Section</span></span>

  - <span data-ttu-id="208a3-106">[Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   のメディア品質概要レポートエンタープライズ voip ピアツーピア通話、エンタープライズ voip 電話会議、公衆交換電話網 (PSTN) で少なくとも部分的に依存する通話など、さまざまな種類のエンドポイントの全体的な品質データを提供します。</span><span class="sxs-lookup"><span data-stu-id="208a3-106">[Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>

  - <span data-ttu-id="208a3-107">[Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   のメディア品質比較レポートでは、さまざまな種類の音声通話 (たとえば、ワイヤレスネットワークで行われた通話、および有線接続経由の通話) の通話品質の値の比較を示します。</span><span class="sxs-lookup"><span data-stu-id="208a3-107">[Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

  - <span data-ttu-id="208a3-108">[Lync server 2013](lync-server-2013-server-performance-report.md)   のサーバーパフォーマンスレポート。低下、パケット損失、ジッターなどの主要な品質指標の測定値に基づいて、最も問題が発生したサーバーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="208a3-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md)   Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>

  - <span data-ttu-id="208a3-109">[Lync Server 2013](lync-server-2013-location-report.md)   の場所レポートネットワークの場所の一覧と、各場所で発生する呼び出しのメディア品質の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="208a3-109">[Location Report in Lync Server 2013](lync-server-2013-location-report.md)   Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="208a3-110">このレポートの目的として、場所は IP サブネットに基づいています。</span><span class="sxs-lookup"><span data-stu-id="208a3-110">For purposes of this report, locations are based on IP subnets.</span></span>

  - <span data-ttu-id="208a3-111">[Lync Server 2013](lync-server-2013-device-report.md)   のデバイスレポートは、エンタープライズ voip 通話で使用されるデバイスの概要と、デバイスごとの通話の平均的なメディア品質を含みます。</span><span class="sxs-lookup"><span data-stu-id="208a3-111">[Device Report in Lync Server 2013](lync-server-2013-device-report.md)   Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>

  - <span data-ttu-id="208a3-112">[「Lync Server 2013](lync-server-2013-call-list-report.md)   の通話リストレポート」では、組織内で発信または受信した通話に関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="208a3-112">[Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md)   Provides detailed information about phone calls made or received within your organization.</span></span>

  - <span data-ttu-id="208a3-113">[「Lync Server 2013](lync-server-2013-call-detail-report.md)   の通話の詳細レポート」では、組織内で発信または受信した通話に関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="208a3-113">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md)   Provides detailed information about phone calls made from or received within your organization.</span></span>

  - <span data-ttu-id="208a3-114">[Lync server 2013](lync-server-2013-server-media-quality-trend-report.md)   のサーバーメディア品質傾向レポート通話ボリューム、低品質通話のパーセンテージ、パケット損失、ジッターなどの、qoe (quality of Experience) 指標で最大5台のサーバーをグラフィカルに比較する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="208a3-114">[Server Media Quality Trend Report in Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   Provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>

  - <span data-ttu-id="208a3-115">[Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   のメディア品質メトリック分布レポートには、ジッターやパケット損失などの qoe (quality of Experience) 指標の分布値を示すグラフが用意されています。</span><span class="sxs-lookup"><span data-stu-id="208a3-115">[The Media Quality Metrics Distribution Report in Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>

  - <span data-ttu-id="208a3-116">[Lync Server 2013](lync-server-2013-location-trend-report.md)   の場所の傾向レポートは、ネットワークの場所の通話品質の傾向情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="208a3-116">[Location Trend Report in Lync Server 2013](lync-server-2013-location-trend-report.md)   Provides call quality trend information for network locations.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

