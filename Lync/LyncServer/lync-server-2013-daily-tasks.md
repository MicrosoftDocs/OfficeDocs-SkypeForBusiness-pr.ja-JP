---
title: 'Lync Server 2013: 毎日のタスク'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Daily tasks
ms:assetid: f7a5f99e-5d2b-445d-9ba1-cbfcfeff16ae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720351(v=OCS.15)
ms:contentKeyID: 63969666
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 777d0fdfc8857022c0a54fcb1cd237b90f68d9d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516644"
---
# <a name="daily-tasks-in-lync-server-2013"></a><span data-ttu-id="906d1-102">Lync Server 2013 の毎日のタスク</span><span class="sxs-lookup"><span data-stu-id="906d1-102">Daily tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="906d1-103">_**トピックの最終更新日:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="906d1-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="906d1-104">Lync Server 2013 の展開の可用性と信頼性を確保するために、日常的な日常モニターの一部として、またはシステムの機能にとって非常に重要なテスト要素を使用する必要があります。これには、物理プラットフォーム、オペレーティングシステム、およびすべての重要な Lync Server 2013 サービスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="906d1-104">To help ensure the availability and reliability of the Lync Server 2013 deployment, you should as part of daily routine monitor and test elements that are very important to the functioning of the system, which includes the physical platform, the operating system, and all important Lync Server 2013 services.</span></span> <span data-ttu-id="906d1-105">予防的なメンテナンスと予防的な監視は、Lync Server 2013 の展開に悪影響を及ぼす可能性のある潜在的なエラーや問題を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="906d1-105">Preventive maintenance and proactive monitoring will help you identify potential errors and issues that may adversely affect the Lync Server 2013 deployment.</span></span>

<span data-ttu-id="906d1-106">Lync Server 2013 の展開の監視では、接続、サービス、サーバーリソース、およびシステムリソースの問題をチェックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="906d1-106">Monitoring the Lync Server 2013 deployment involves checking for issues with connections, services, server resources, and system resources.</span></span> <span data-ttu-id="906d1-107">Windows Server オペレーティングシステムと System Center Operations Manager、および Lync Server は、Lync Server 組織が円滑に稼働していることを確認するために、多くの監視ツールとサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="906d1-107">Windows Server operating systems, together with System Center Operations Manager, and Lync Server give you many monitoring tools and services to help ensure that the Lync Server organization is running smoothly.</span></span> <span data-ttu-id="906d1-108">これらのテクノロジが一緒に実装されている場合、管理者は問題が発生する前に通知を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="906d1-108">When these technologies are implemented together, administrators will be able to receive alerts when or before issues occur.</span></span>

<span data-ttu-id="906d1-109">日常の監視の主な利点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="906d1-109">The key advantages to daily monitoring are as follows:</span></span>

  - <span data-ttu-id="906d1-110">定義されている Sla のパフォーマンスと可用性の要件を満たしていること。</span><span class="sxs-lookup"><span data-stu-id="906d1-110">Meeting the performance and availability requirements of defined SLAs.</span></span>

  - <span data-ttu-id="906d1-111">毎日のバックアップ操作などの特定の管理タスクを正常に完了し、サーバーの正常性をチェックします。</span><span class="sxs-lookup"><span data-stu-id="906d1-111">Successfully completing specific administrative tasks, such as daily backup operations, and checking server health.</span></span>

  - <span data-ttu-id="906d1-112">サーバーパフォーマンスのボトルネックなどの問題を検出し、対処するか、生産性に影響する前に追加のリソースを必要とします。</span><span class="sxs-lookup"><span data-stu-id="906d1-112">Detecting and addressing issues, such as bottlenecks in the server performance, or need for additional resources before they affect productivity.</span></span>

<span data-ttu-id="906d1-113">毎日のメンテナンスタスクは、管理チームが組織内の通常のシステム操作の基準または基準を定義または確立したり、異常な動作を検出したりするのを支援します。</span><span class="sxs-lookup"><span data-stu-id="906d1-113">Daily maintenance tasks help the administrative team to define or establish a criteria or baseline for normal systems operations within the organization, and to detect any abnormal activity.</span></span> <span data-ttu-id="906d1-114">管理チームが Lync Server 2013 のインフラストラクチャに関するデータを取得して管理できるようにするには、これらの毎日のメンテナンスタスクを実装することが重要です。</span><span class="sxs-lookup"><span data-stu-id="906d1-114">It is important to implement these daily maintenance tasks so that the administrative team can capture and maintain data about the Lync Server 2013 infrastructure, such as usage levels, possible performance bottlenecks, and administrative changes.</span></span>

<span data-ttu-id="906d1-115">毎日のタスクのパフォーマンスを整理するには、 [日単位のタスクチェックリスト](lync-server-2013-operations-checklists.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="906d1-115">To help organize the performance of daily tasks, use the [Daily task checklist](lync-server-2013-operations-checklists.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="906d1-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="906d1-116">See Also</span></span>


[<span data-ttu-id="906d1-117">日毎のタスクチェックリスト</span><span class="sxs-lookup"><span data-stu-id="906d1-117">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

