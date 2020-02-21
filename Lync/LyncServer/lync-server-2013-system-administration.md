---
title: 'Lync Server 2013: システム管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87f128196f1d541e8a7f8ffd3b48bac8f34de85b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a><span data-ttu-id="8db6b-102">Lync Server 2013 のシステム管理</span><span class="sxs-lookup"><span data-stu-id="8db6b-102">System administration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8db6b-103">_**トピックの最終更新日:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="8db6b-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="8db6b-104">システム管理には、予定およびオンデマンドの両方の管理タスクが含まれます。これにより、IT システムを円滑に稼働させるために必要になります。</span><span class="sxs-lookup"><span data-stu-id="8db6b-104">System administration includes the day-to-day administrative tasks, both planned and on-demand, that are required to keep an IT system operating smoothly.</span></span> <span data-ttu-id="8db6b-105">通常、システム管理タスクについては、記載されている手順で説明します。</span><span class="sxs-lookup"><span data-stu-id="8db6b-105">Typically, system administration tasks are covered by written procedures.</span></span> <span data-ttu-id="8db6b-106">これらの手順により、すべてのサポートスタッフが同じ標準ツールおよび方法を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="8db6b-106">These procedures help ensure that the same standard tools and methods are used by all support staff.</span></span>

<span data-ttu-id="8db6b-107">Lync 環境での一般的なシステム管理タスクには、プールのバックアップとアーカイブ、ログの監視、ユーザーの作成と管理、ウイルス対策ソフトウェアの更新などがあります。</span><span class="sxs-lookup"><span data-stu-id="8db6b-107">In a Lync environment, typical system administration tasks include backing up and archiving pools, monitoring logs, creating and managing users, and updating antivirus software.</span></span>

<div>

## <a name="system-troubleshooting"></a><span data-ttu-id="8db6b-108">システムのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="8db6b-108">System troubleshooting</span></span>

<span data-ttu-id="8db6b-109">組織は予期しない問題に対処できるように準備しておく必要があります。また、問題を解決するまでに報告された時点から問題を管理する手順を用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db6b-109">An organization must be prepared to deal with unexpected issues and should have a procedure to manage issues from the point at which they are reported until their resolution.</span></span> <span data-ttu-id="8db6b-110">完了した作業が不必要に繰り返されることを回避するために、問題を診断したサポートスタッフが記録および使用する方法に関する情報を記録しておきます。</span><span class="sxs-lookup"><span data-stu-id="8db6b-110">Information about how support staff diagnosed an issue should be recorded and used in the future to avoid unnecessarily repeating completed work.</span></span>

</div>

<div>

## <a name="system-troubleshooting-process"></a><span data-ttu-id="8db6b-111">システムトラブルシューティングプロセス</span><span class="sxs-lookup"><span data-stu-id="8db6b-111">System troubleshooting process</span></span>

<span data-ttu-id="8db6b-112">次の図は、システムのトラブルシューティングプロセスと、他の操作役割との相互作用を示しています。</span><span class="sxs-lookup"><span data-stu-id="8db6b-112">The following diagram shows the system troubleshooting process and the interactions with other operations roles.</span></span>

<span data-ttu-id="8db6b-113">**システムトラブルシューティングのフローチャート**</span><span class="sxs-lookup"><span data-stu-id="8db6b-113">**System troubleshooting flowchart**</span></span>

<span data-ttu-id="8db6b-114">![システムトラブルシューティングのフローチャート](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "システムトラブルシューティングのフローチャート")</span><span class="sxs-lookup"><span data-stu-id="8db6b-114">![System Troubleshooting Flowchart](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "System Troubleshooting Flowchart")</span></span>

  - <span data-ttu-id="8db6b-115">**分類して優先度**   を設定するこのタスクは、通常、サービスデスクによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="8db6b-115">**Classify and Prioritize**   This task is typically performed by the service desk.</span></span> <span data-ttu-id="8db6b-116">たとえば、問題がソフトウェアの問題またはハードウェアの問題としてグループ化されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="8db6b-116">For example, an issue may be grouped as a software issue or a hardware issue.</span></span> <span data-ttu-id="8db6b-117">その後、問題は調査のために適切なサポートチームにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="8db6b-117">The issue is then routed to the appropriate support team for investigation.</span></span> <span data-ttu-id="8db6b-118">問題の優先度を決定するための規則と、解決に要する時間と時間は、通常、SLA で定義されています。</span><span class="sxs-lookup"><span data-stu-id="8db6b-118">The rules for determining the priority of an issue, together with the time to respond and time to resolve, are typically defined in the SLA.</span></span>

  - <span data-ttu-id="8db6b-119">\*\*\*\*   適切なサポートチームを調査および診断して問題を診断し、変更を提案して問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="8db6b-119">**Investigate and Diagnose**   The appropriate support team diagnoses the issue and proposes changes to resolve the issue.</span></span> <span data-ttu-id="8db6b-120">ソリューションが単純で、変更管理を必要としない場合は、ソリューションをすぐに適用できます。</span><span class="sxs-lookup"><span data-stu-id="8db6b-120">If the solution is simple and does not require change control, the solution can be applied immediately.</span></span> <span data-ttu-id="8db6b-121">ソリューションが簡単でない場合は、変更の要求を発生させ、提案された作業を変更管理プロセスで管理する必要があります (多くの場合は「ファストトラック」の手順を実行します)。</span><span class="sxs-lookup"><span data-stu-id="8db6b-121">If the solution is not easy, a request for change should be raised and the proposed work should be managed by the change management process, frequently under a “fast-track” procedure.</span></span> <span data-ttu-id="8db6b-122">加えられた変更はすべて、構成管理プロセスを使用して記録されます。</span><span class="sxs-lookup"><span data-stu-id="8db6b-122">Any changes that are made should be recorded using the configuration management process.</span></span>

  - <span data-ttu-id="8db6b-123">\*\*\*\*   解決策をテストした後、終了して記録します。この問題は、終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db6b-123">**Close and Record**   After testing the resolution, the issue should be closed.</span></span> <span data-ttu-id="8db6b-124">問題から学んだ教訓がある場合は、サポート技術情報にエントリを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db6b-124">If there are lessons to be learned from the issue, an entry should be created in the knowledge base.</span></span>

  - <span data-ttu-id="8db6b-125">\*\*\*\*   問題の傾向を特定するには、最新の問題のレビューと傾向分析を定期的に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db6b-125">**Review and Trend Analysis**   Periodic reviews of recent issues should be performed to identify issue trends.</span></span> <span data-ttu-id="8db6b-126">たとえば、ユーザーが Lync サイトへのログオンが遅いと、頻繁に問題が発生している場合、ネットワーク帯域幅の問題が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8db6b-126">For example, if the users are experiencing frequent issues with slow logons to their Lync sites, network bandwidth issues may be the cause.</span></span> <span data-ttu-id="8db6b-127">問題の解決時間と、システム可用性に対する停止の影響を確認し、SLA と比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db6b-127">Issue resolution times and the effect of any outages on system availability should be reviewed and compared with the SLA.</span></span> <span data-ttu-id="8db6b-128">顧客がサービスに関する問題 (アカウントマネージャーなど) にスポンサーしたユーザーには、重要な問題があることを通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db6b-128">The person who liaises with the customer on service issues, such as an account manager, should be informed of any significant issues.</span></span>

</div>

<div>

## <a name="issue-management-tools"></a><span data-ttu-id="8db6b-129">問題管理ツール</span><span class="sxs-lookup"><span data-stu-id="8db6b-129">Issue management tools</span></span>

<span data-ttu-id="8db6b-130">サービスデスクツールを使用すると、スタッフは新しい問題の記録、分類、および優先順位付けを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8db6b-130">Service desk tools enable staff to record, classify, and prioritize new issues.</span></span> <span data-ttu-id="8db6b-131">その後、ツールは、調査と診断を通じて問題のサービス要求を管理するためのワークフロープロセスを提供します。多くの場合、複数のサポートチームがこれを使用します。</span><span class="sxs-lookup"><span data-stu-id="8db6b-131">Tools will then provide the workflow processes to manage the issue service request through investigation and diagnosis, often by more than one support team.</span></span> <span data-ttu-id="8db6b-132">ツールは、解決時間と過去の傾向に関するレポートを提供します。サポート技術情報データベースも含まれていることがあります。これは、過去の問題を検索するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="8db6b-132">Tools, which will frequently provide reports about resolution times and historical trends, may also include a knowledge base database, which can be used to search through past issues.</span></span>

<span data-ttu-id="8db6b-133">Microsoft サポート技術情報は、Microsoft によって発生したサポート問題の有用な記録です。</span><span class="sxs-lookup"><span data-stu-id="8db6b-133">The Microsoft Knowledge Base is a useful record of support issues that were encountered by Microsoft.</span></span> <span data-ttu-id="8db6b-134">詳細については、Microsoft サポート web サイト<https://go.microsoft.com/fwlink/?linkid=14898>() を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8db6b-134">For more information, see the Microsoft Support website (<https://go.microsoft.com/fwlink/?linkid=14898>).</span></span>

<span data-ttu-id="8db6b-135">通常、サードパーティソフトウェアでは、組織のニーズに合わせてカスタマイズする必要があります (teams の編成、レポート要件、SLA に必要な対策など)。</span><span class="sxs-lookup"><span data-stu-id="8db6b-135">Third-party software typically requires customization to suit the organization’s needs, such as the organization of teams, reporting requirements, and measures required by the SLA.</span></span>

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a><span data-ttu-id="8db6b-136">一元管理と分散化管理</span><span class="sxs-lookup"><span data-stu-id="8db6b-136">Centralized vs. decentralized administration</span></span>

<span data-ttu-id="8db6b-137">システム管理タスクを実行するための役割と責任は、組織が集中モデル、分散モデル、またはその両方の組み合わせに従っているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="8db6b-137">Roles and responsibilities for performing system administration tasks depend on whether the organization follows a centralized model, a decentralized model, or a combination of both.</span></span>

  - <span data-ttu-id="8db6b-138">**集中モデル**   中央モデルでは、1つまたは複数の管理グループが Lync Server 環境全体を完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="8db6b-138">**Centralized Model**   In a centralized model, one or several administrative groups maintain complete control of the whole Lync Server environment.</span></span> <span data-ttu-id="8db6b-139">この管理モデルは、すべての管理タスクが1つの情報技術グループによって実行されるデータセンターに似ています。</span><span class="sxs-lookup"><span data-stu-id="8db6b-139">This administrative model resembles a data center where all administration tasks are performed by a single information technology group.</span></span> <span data-ttu-id="8db6b-140">チーム内の役割と責任は、経験と専門知識に従って定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db6b-140">Roles and responsibilities within the team should be defined according to experience and expertise.</span></span>

  - <span data-ttu-id="8db6b-141">**分散**   型のモデル分散化された組織は、複数の地理的な場所に配置されており、さまざまな場所にある Lync Server サーバーと管理者のチームが機能しています。</span><span class="sxs-lookup"><span data-stu-id="8db6b-141">**Decentralized Model**   Decentralized organizations are located in several geographic locations and have functioning Lync Server servers and teams of administrators in different locations.</span></span> <span data-ttu-id="8db6b-142">たとえば、ローカル管理スタッフと、Lync Server 2013 を実行している1つ以上のサーバーが国/地域ごとに存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="8db6b-142">For example, there may be local administration staff and one or more servers that are running Lync Server 2013 for each country/region.</span></span> <span data-ttu-id="8db6b-143">または、Lync Server 2013 を実行しているサーバーのプールと、北米用の管理チームが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="8db6b-143">Or, there may be a pool of servers that are running Lync Server 2013 and an administrative team for North America and one for Europe.</span></span> <span data-ttu-id="8db6b-144">場合によっては、管理者が自分の地域に対してのみ責任を持ち、他の領域のリソースを管理する権限を制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8db6b-144">Sometimes, you may want administrators to be responsible only for their own geographical area and restrict permissions to administer resources in other areas.</span></span>

<span data-ttu-id="8db6b-145">Lync Server では、役割ベースのアクセス制御 (RBAC) を使用して特定のユーザーまたはグループに特定の管理タスクを委任することもできます。</span><span class="sxs-lookup"><span data-stu-id="8db6b-145">Lync Server also allows you to delegate specific administrative tasks to specific people or groups by using role-based access control (RBAC).</span></span> <span data-ttu-id="8db6b-146">RBAC を使用すると、管理者は特定のユーザー権限とアクセス許可を他の管理者に委任して、可能な管理タスクのサブセットを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="8db6b-146">RBAC allows administrators to delegate specific user rights and permissions to other administrators to perform a subset of the administrative tasks possible.</span></span> <span data-ttu-id="8db6b-147">RBAC を使用することにより、ユーザーが特定の管理タスクを実行できるかどうかは、ユーザーに割り当てられている RBAC の役割によって決まります。</span><span class="sxs-lookup"><span data-stu-id="8db6b-147">By using RBAC, the user’s ability to perform specific administrative tasks depends on the RBAC roles that are assigned to the user.</span></span> <span data-ttu-id="8db6b-148">RBAC は、ユーザーがメンバーになっている RBAC の役割に基づいて、ユーザーが実行できるコマンドレットの一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="8db6b-148">RBAC provides a list of cmdlets that the user can run based on the RBAC roles that the user is a member of.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

