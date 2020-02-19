---
title: 'Lync Server 2013: 通話診断レポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Reports
ms:assetid: 8d362dd9-a119-4601-a3b4-3e7ed0aaa92e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615013(v=OCS.15)
ms:contentKeyID: 48184794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e6fdb8c47e8b16a4a668b710c5903ef568d90c5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="5c6f0-102">Lync Server 2013 の通話診断レポート</span><span class="sxs-lookup"><span data-stu-id="5c6f0-102">Call Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c6f0-103">_**トピックの最終更新日:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="5c6f0-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="5c6f0-104">通話診断レポートは、エラーが発生したピアツーピア セッションと電話会議セッションに関する概要情報と診断データを提供します。</span><span class="sxs-lookup"><span data-stu-id="5c6f0-104">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5c6f0-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5c6f0-105">In This Section</span></span>

  - <span data-ttu-id="5c6f0-106">[Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   の通話診断の概要レポートでは、失敗したピアツーピアセッションと電話会議セッションの全体的な概要が提供されています。</span><span class="sxs-lookup"><span data-stu-id="5c6f0-106">[Call Diagnostic Summary Report in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="5c6f0-107">ピアツーピアセッションとは、2人の参加者のみを含むセッションのことです。</span><span class="sxs-lookup"><span data-stu-id="5c6f0-107">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="5c6f0-108">会議セッションには、3人以上の参加者が関与します。</span><span class="sxs-lookup"><span data-stu-id="5c6f0-108">Conferencing sessions involve three or more participants.</span></span>

  - <span data-ttu-id="5c6f0-109">[Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   のピアツーピアアクティビティ診断レポートでは、エラーが発生したピアツーピアセッションの全体的な傾向ビューが提供されます。</span><span class="sxs-lookup"><span data-stu-id="5c6f0-109">[Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="5c6f0-110">ピアツーピアセッションには、2人の参加者だけが関係します。</span><span class="sxs-lookup"><span data-stu-id="5c6f0-110">A peer-to-peer session involves just two participants.</span></span>

  - <span data-ttu-id="5c6f0-111">[Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   の電話会議診断レポートでは、会議セッションが失敗したことと、会議の各モダリティの傾向ビューの全体的な傾向ビューが提供されています。</span><span class="sxs-lookup"><span data-stu-id="5c6f0-111">[Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="5c6f0-112">会議セッションには、少なくとも3人の参加者が関与します。</span><span class="sxs-lookup"><span data-stu-id="5c6f0-112">Conferencing sessions involve at least three participants.</span></span>

  - <span data-ttu-id="5c6f0-113">[Lync Server 2013](lync-server-2013-top-failures-report.md)   のトップエラーレポートには、最も頻繁に発生するエラーの一覧と、時間の経過に伴う傾向が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c6f0-113">[Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md)   Provides a list of the most frequent failures and their trends over time.</span></span>

  - <span data-ttu-id="5c6f0-114">[Failure Distribution Report Lync Server 2013](lync-server-2013-failure-distribution-report.md)   では、失敗したセッションの分析が提供されます。</span><span class="sxs-lookup"><span data-stu-id="5c6f0-114">[Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md)   Provides an analysis of failed sessions.</span></span>

  - <span data-ttu-id="5c6f0-115">[Lync Server 2013](lync-server-2013-failure-list-report.md)   のエラーリストレポートでは、エラーが発生した電話会議に関係する個々の参加者に関する詳細情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="5c6f0-115">[Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md)   Provides detailed information about the individual participants involved in a failed conference.</span></span>

  - <span data-ttu-id="5c6f0-116">[Lync Server 2013](lync-server-2013-diagnostic-report.md)   の診断レポートエラーが発生したセッションの診断およびトラブルシューティングの情報 (SIP 応答コードと診断ヘッダーおよび IDs を含む) を提供します。</span><span class="sxs-lookup"><span data-stu-id="5c6f0-116">[Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md)   Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

