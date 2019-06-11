---
title: 'Lync Server 2013: 診断レポートを発信する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Diagnostic Reports
ms:assetid: 8d362dd9-a119-4601-a3b4-3e7ed0aaa92e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615013(v=OCS.15)
ms:contentKeyID: 48184794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 342c1727985418930a333c723962da2bb276692f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="0e7db-102">Lync Server 2013 での通話診断レポート</span><span class="sxs-lookup"><span data-stu-id="0e7db-102">Call Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e7db-103">_**最終更新日:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="0e7db-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="0e7db-104">通話診断レポートは、エラーが発生したピアツーピア セッションと電話会議セッションに関する概要情報と診断データを提供します。</span><span class="sxs-lookup"><span data-stu-id="0e7db-104">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0e7db-105">このセクション中</span><span class="sxs-lookup"><span data-stu-id="0e7db-105">In This Section</span></span>

  - <span data-ttu-id="0e7db-106">[Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   の通話診断の概要レポートには、ピアツーピアセッションと会議セッションの失敗の全体的な概要が記載されています。</span><span class="sxs-lookup"><span data-stu-id="0e7db-106">[Call Diagnostic Summary Report in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="0e7db-107">ピアツーピアセッションは、2人の参加者に関連するセッションです。</span><span class="sxs-lookup"><span data-stu-id="0e7db-107">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="0e7db-108">会議セッションには3人以上の参加者が関係します。</span><span class="sxs-lookup"><span data-stu-id="0e7db-108">Conferencing sessions involve three or more participants.</span></span>

  - <span data-ttu-id="0e7db-109">[Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   のピアツーピアアクティビティ診断レポートには、ピアツーピアセッションの失敗の全体的な傾向ビューが用意されています。</span><span class="sxs-lookup"><span data-stu-id="0e7db-109">[Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="0e7db-110">ピアツーピアセッションには、2人の参加者のみが関係します。</span><span class="sxs-lookup"><span data-stu-id="0e7db-110">A peer-to-peer session involves just two participants.</span></span>

  - <span data-ttu-id="0e7db-111">[Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   の会議の診断レポートには、会議セッションの失敗と、各会議モードのトレンドビューが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0e7db-111">[Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="0e7db-112">会議セッションには、少なくとも3人の参加者が関係します。</span><span class="sxs-lookup"><span data-stu-id="0e7db-112">Conferencing sessions involve at least three participants.</span></span>

  - <span data-ttu-id="0e7db-113">[Lync Server 2013](lync-server-2013-top-failures-report.md)   の上位のエラーレポートには、最も頻繁に発生するエラーの一覧と、時間の経過に伴う傾向が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e7db-113">[Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md)   Provides a list of the most frequent failures and their trends over time.</span></span>

  - <span data-ttu-id="0e7db-114">[Lync Server 2013](lync-server-2013-failure-distribution-report.md)   のエラー配信レポートは、失敗したセッションの分析を提供します。</span><span class="sxs-lookup"><span data-stu-id="0e7db-114">[Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md)   Provides an analysis of failed sessions.</span></span>

  - <span data-ttu-id="0e7db-115">[Lync Server 2013](lync-server-2013-failure-list-report.md)   の [エラー一覧] レポートには、失敗した会議に関わる個々の参加者に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0e7db-115">[Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md)   Provides detailed information about the individual participants involved in a failed conference.</span></span>

  - <span data-ttu-id="0e7db-116">[Lync Server 2013](lync-server-2013-diagnostic-report.md)   の診断レポートでは、失敗したセッションの診断とトラブルシューティングの情報 (SIP 応答コード、診断ヘッダー、IDs など) が提供されます。</span><span class="sxs-lookup"><span data-stu-id="0e7db-116">[Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md)   Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

