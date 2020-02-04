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
ms.openlocfilehash: 1f7db75e8f4e6e7d8b8a36d0e5ba614ac89c22e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="b4298-102">Lync Server 2013 のメディア品質診断レポート</span><span class="sxs-lookup"><span data-stu-id="b4298-102">Media Quality Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4298-103">_**最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="b4298-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="b4298-104">メディア品質診断レポートは、通話の品質についての情報、および失敗した通話についての診断とトラブルシューティングの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b4298-104">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b4298-105">このセクション中</span><span class="sxs-lookup"><span data-stu-id="b4298-105">In This Section</span></span>

  - <span data-ttu-id="b4298-106">[Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   のメディア品質の概要レポートでは、さまざまなエンドポイントの種類に対応した全体的な品質データが提供されます。エンタープライズボイスピアツーピア通話、エンタープライズボイス会議通話、通話交換電話網 (PSTN) では、少なくとも一部に依存しています。</span><span class="sxs-lookup"><span data-stu-id="b4298-106">[Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>

  - <span data-ttu-id="b4298-107">[Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   のメディア品質比較レポートでは、さまざまな種類の音声通話 (たとえば、ワイヤレスネットワーク経由で発信された通話、有線接続を経由した通話など) の通話品質を比較できます。</span><span class="sxs-lookup"><span data-stu-id="b4298-107">[Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

  - <span data-ttu-id="b4298-108">[Lync server 2013](lync-server-2013-server-performance-report.md)   のサーバーパフォーマンスレポートには、パフォーマンスの低下、パケット損失、ジッタなどの主要品質指標の測定値に基づいて、最も問題が発生したサーバーが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4298-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md)   Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>

  - <span data-ttu-id="b4298-109">[Lync Server 2013](lync-server-2013-location-report.md)   の場所レポートには、ネットワーク上の場所の一覧と、各場所で発生した通話のメディア品質の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4298-109">[Location Report in Lync Server 2013](lync-server-2013-location-report.md)   Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="b4298-110">このレポートの目的として、場所は IP サブネットに基づいています。</span><span class="sxs-lookup"><span data-stu-id="b4298-110">For purposes of this report, locations are based on IP subnets.</span></span>

  - <span data-ttu-id="b4298-111">[Lync Server 2013](lync-server-2013-device-report.md)   のデバイスレポートには、企業の音声通話に使用されるデバイスの概要と、デバイス別の通話の平均メディア品質が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b4298-111">[Device Report in Lync Server 2013](lync-server-2013-device-report.md)   Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>

  - <span data-ttu-id="b4298-112">[Lync Server 2013](lync-server-2013-call-list-report.md)   の通話リストレポートは、組織内で発信または受信した電話の詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b4298-112">[Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md)   Provides detailed information about phone calls made or received within your organization.</span></span>

  - <span data-ttu-id="b4298-113">[Lync Server 2013](lync-server-2013-call-detail-report.md)   の通話詳細レポートには、組織内で発信または受信した電話の詳細情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="b4298-113">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md)   Provides detailed information about phone calls made from or received within your organization.</span></span>

  - <span data-ttu-id="b4298-114">[Lync server 2013 のサーバーのメディア品質トレンドレポートで](lync-server-2013-server-media-quality-trend-report.md)   は、通話音量、低品質の通話率、パケット損失、ジッタなどのさまざまなエクスペリエンスメトリックについて、最大5台のサーバーを視覚的に比較することができます。</span><span class="sxs-lookup"><span data-stu-id="b4298-114">[Server Media Quality Trend Report in Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   Provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>

  - <span data-ttu-id="b4298-115">[Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   のメディア品質指標配布レポートには、ジッタやパケット損失などの品質のエクスペリエンスメトリックの分布値を示すグラフが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b4298-115">[The Media Quality Metrics Distribution Report in Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>

  - <span data-ttu-id="b4298-116">[Lync Server 2013](lync-server-2013-location-trend-report.md)   の位置情報の傾向レポートでは、ネットワーク上の場所の通話品質の傾向情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="b4298-116">[Location Trend Report in Lync Server 2013](lync-server-2013-location-trend-report.md)   Provides call quality trend information for network locations.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

