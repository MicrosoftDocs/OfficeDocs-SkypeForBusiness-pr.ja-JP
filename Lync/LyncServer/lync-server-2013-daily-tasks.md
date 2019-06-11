---
title: 'Lync Server 2013: 日次タスク'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Daily tasks
ms:assetid: f7a5f99e-5d2b-445d-9ba1-cbfcfeff16ae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720351(v=OCS.15)
ms:contentKeyID: 63969666
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4375b11511d3b2c88222ea36575c18ca6fcc7dfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="daily-tasks-in-lync-server-2013"></a><span data-ttu-id="1e8a1-102">Lync Server 2013 での日次タスク</span><span class="sxs-lookup"><span data-stu-id="1e8a1-102">Daily tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e8a1-103">_**最終更新日:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="1e8a1-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="1e8a1-104">Lync Server 2013 の展開の可用性と信頼性を確保するために、システムの機能 (物理プラットフォーム、オペレーティングシステム、オペレーティングシステムなど) に非常に重要な日常的な日常的な監視とテスト要素の一部としてお勧めします。すべての重要な Lync Server 2013 サービス。</span><span class="sxs-lookup"><span data-stu-id="1e8a1-104">To help ensure the availability and reliability of the Lync Server 2013 deployment, you should as part of daily routine monitor and test elements that are very important to the functioning of the system, which includes the physical platform, the operating system, and all important Lync Server 2013 services.</span></span> <span data-ttu-id="1e8a1-105">予防的なメンテナンスと事前監視は、Lync Server 2013 の展開に悪影響を与える可能性のあるエラーや問題を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1e8a1-105">Preventive maintenance and proactive monitoring will help you identify potential errors and issues that may adversely affect the Lync Server 2013 deployment.</span></span>

<span data-ttu-id="1e8a1-106">Lync Server 2013 の展開を監視する場合は、接続、サービス、サーバーリソース、システムリソースの問題をチェックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e8a1-106">Monitoring the Lync Server 2013 deployment involves checking for issues with connections, services, server resources, and system resources.</span></span> <span data-ttu-id="1e8a1-107">Windows Server オペレーティングシステムと System Center Operations Manager、Lync Server を使用すると、Lync Server 組織が円滑に動作していることを確認するための多くの監視ツールとサービスを利用できます。</span><span class="sxs-lookup"><span data-stu-id="1e8a1-107">Windows Server operating systems, together with System Center Operations Manager, and Lync Server give you many monitoring tools and services to help ensure that the Lync Server organization is running smoothly.</span></span> <span data-ttu-id="1e8a1-108">これらのテクノロジが一緒に実装されている場合、管理者は問題発生以前にアラートを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="1e8a1-108">When these technologies are implemented together, administrators will be able to receive alerts when or before issues occur.</span></span>

<span data-ttu-id="1e8a1-109">日常的な監視を行うことの主な利点は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1e8a1-109">The key advantages to daily monitoring are as follows:</span></span>

  - <span data-ttu-id="1e8a1-110">定義されている SLA のパフォーマンスと可用性の要件を満たす。</span><span class="sxs-lookup"><span data-stu-id="1e8a1-110">Meeting the performance and availability requirements of defined SLAs.</span></span>

  - <span data-ttu-id="1e8a1-111">日々のバックアップ処理、サーバーの状態のチェックといった特定の管理タスクを正常に完了する。</span><span class="sxs-lookup"><span data-stu-id="1e8a1-111">Successfully completing specific administrative tasks, such as daily backup operations, and checking server health.</span></span>

  - <span data-ttu-id="1e8a1-112">サーバーのパフォーマンスにおけるボトルネックなどの問題を検知し、対処する。またはこれらの問題が生産性に影響を及ぼす前に追加リソースの必要性を検知し、対処する。</span><span class="sxs-lookup"><span data-stu-id="1e8a1-112">Detecting and addressing issues, such as bottlenecks in the server performance, or need for additional resources before they affect productivity.</span></span>

<span data-ttu-id="1e8a1-113">毎日のメンテナンスによって、管理チームは、組織内の標準的なシステム動作の基準やベースラインを定義または確立したり、通常とは異なる動作を検知したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="1e8a1-113">Daily maintenance tasks help the administrative team to define or establish a criteria or baseline for normal systems operations within the organization, and to detect any abnormal activity.</span></span> <span data-ttu-id="1e8a1-114">この日常的なメンテナンスタスクを実装して、管理チームが Lync Server 2013 インフラストラクチャに関するデータ (使用レベル、考えられるパフォーマンスのボトルネック、管理上の変更など) に関するデータを取得して管理できるようにすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="1e8a1-114">It is important to implement these daily maintenance tasks so that the administrative team can capture and maintain data about the Lync Server 2013 infrastructure, such as usage levels, possible performance bottlenecks, and administrative changes.</span></span>

<span data-ttu-id="1e8a1-115">日次タスクのパフォーマンスを簡単に体系化するには、[日次タスク チェックリスト](lync-server-2013-operations-checklists.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="1e8a1-115">To help organize the performance of daily tasks, use the [Daily task checklist](lync-server-2013-operations-checklists.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="1e8a1-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e8a1-116">See Also</span></span>


[<span data-ttu-id="1e8a1-117">日次タスク チェックリスト</span><span class="sxs-lookup"><span data-stu-id="1e8a1-117">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

