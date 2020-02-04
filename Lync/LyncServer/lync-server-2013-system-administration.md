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
ms.openlocfilehash: 8e10f0d340ec0d291d0b184b8649f8f132683e08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a><span data-ttu-id="1fe47-102">Lync Server 2013 でのシステム管理</span><span class="sxs-lookup"><span data-stu-id="1fe47-102">System administration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fe47-103">_**最終更新日:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="1fe47-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="1fe47-104">システム管理には、IT システムをスムーズに運用するために必要な日常的な管理タスク (計画およびオンデマンドの両方) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1fe47-104">System administration includes the day-to-day administrative tasks, both planned and on-demand, that are required to keep an IT system operating smoothly.</span></span> <span data-ttu-id="1fe47-105">通常、システム管理タスクについては、記載されている手順で説明します。</span><span class="sxs-lookup"><span data-stu-id="1fe47-105">Typically, system administration tasks are covered by written procedures.</span></span> <span data-ttu-id="1fe47-106">以下の手順を行うと、すべてのサポートスタッフが同じ標準ツールとメソッドを使用していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1fe47-106">These procedures help ensure that the same standard tools and methods are used by all support staff.</span></span>

<span data-ttu-id="1fe47-107">Lync 環境では、一般的なシステム管理タスクには、バックアップとアーカイブのプール、ログの監視、ユーザーの作成と管理、ウイルス対策ソフトウェアの更新が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1fe47-107">In a Lync environment, typical system administration tasks include backing up and archiving pools, monitoring logs, creating and managing users, and updating antivirus software.</span></span>

<div>

## <a name="system-troubleshooting"></a><span data-ttu-id="1fe47-108">システムのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1fe47-108">System troubleshooting</span></span>

<span data-ttu-id="1fe47-109">予期しない問題に対処するために組織が準備しておく必要があります。また、解決までに報告されるポイントから問題を管理するための手順を用意しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fe47-109">An organization must be prepared to deal with unexpected issues and should have a procedure to manage issues from the point at which they are reported until their resolution.</span></span> <span data-ttu-id="1fe47-110">不要になった完了した作業を回避するために、問題を診断したサポートスタッフを記録して、将来使用する方法についての情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fe47-110">Information about how support staff diagnosed an issue should be recorded and used in the future to avoid unnecessarily repeating completed work.</span></span>

</div>

<div>

## <a name="system-troubleshooting-process"></a><span data-ttu-id="1fe47-111">システムのトラブルシューティングプロセス</span><span class="sxs-lookup"><span data-stu-id="1fe47-111">System troubleshooting process</span></span>

<span data-ttu-id="1fe47-112">次の図は、システムのトラブルシューティングプロセスと、他の操作の役割との相互作用を示しています。</span><span class="sxs-lookup"><span data-stu-id="1fe47-112">The following diagram shows the system troubleshooting process and the interactions with other operations roles.</span></span>

<span data-ttu-id="1fe47-113">**システムのトラブルシューティングのフローチャート**</span><span class="sxs-lookup"><span data-stu-id="1fe47-113">**System troubleshooting flowchart**</span></span>

<span data-ttu-id="1fe47-114">![システム トラブルシューティング、フローチャート](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "システム トラブルシューティング、フローチャート")</span><span class="sxs-lookup"><span data-stu-id="1fe47-114">![System Troubleshooting Flowchart](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "System Troubleshooting Flowchart")</span></span>

  - <span data-ttu-id="1fe47-115">**このタスクの分類と優先順位付け**   は、通常、サービスデスクによって行われます。</span><span class="sxs-lookup"><span data-stu-id="1fe47-115">**Classify and Prioritize**   This task is typically performed by the service desk.</span></span> <span data-ttu-id="1fe47-116">たとえば、問題がソフトウェアの問題またはハードウェアの問題としてグループ化されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1fe47-116">For example, an issue may be grouped as a software issue or a hardware issue.</span></span> <span data-ttu-id="1fe47-117">この問題は、調査のために適切なサポートチームにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="1fe47-117">The issue is then routed to the appropriate support team for investigation.</span></span> <span data-ttu-id="1fe47-118">問題の優先順位を決定するための規則と、それに対応するための時間と解決策は、通常、SLA で定義されます。</span><span class="sxs-lookup"><span data-stu-id="1fe47-118">The rules for determining the priority of an issue, together with the time to respond and time to resolve, are typically defined in the SLA.</span></span>

  - <span data-ttu-id="1fe47-119">\*\*\*\*   適切なサポートチームを調査して診断し、問題を診断し、変更を提案して、問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="1fe47-119">**Investigate and Diagnose**   The appropriate support team diagnoses the issue and proposes changes to resolve the issue.</span></span> <span data-ttu-id="1fe47-120">ソリューションが単純で、変更の制御が必要ない場合は、ソリューションをすぐに適用できます。</span><span class="sxs-lookup"><span data-stu-id="1fe47-120">If the solution is simple and does not require change control, the solution can be applied immediately.</span></span> <span data-ttu-id="1fe47-121">ソリューションが簡単でない場合は、変更依頼を発生させる必要があります。提案された作業は、"ファストトラッキング" の手順で頻繁に変更管理プロセスによって管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fe47-121">If the solution is not easy, a request for change should be raised and the proposed work should be managed by the change management process, frequently under a “fast-track” procedure.</span></span> <span data-ttu-id="1fe47-122">加えた変更はすべて、構成管理プロセスを使用して記録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fe47-122">Any changes that are made should be recorded using the configuration management process.</span></span>

  - <span data-ttu-id="1fe47-123">\*\*\*\*   解決した解決策を確認して記録したら、問題を閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fe47-123">**Close and Record**   After testing the resolution, the issue should be closed.</span></span> <span data-ttu-id="1fe47-124">問題から学んだ教訓がある場合は、サポート技術情報でエントリを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fe47-124">If there are lessons to be learned from the issue, an entry should be created in the knowledge base.</span></span>

  - <span data-ttu-id="1fe47-125">\*\*\*\*   問題の傾向を特定するために、最近の問題のレビューとトレンド分析を定期的に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fe47-125">**Review and Trend Analysis**   Periodic reviews of recent issues should be performed to identify issue trends.</span></span> <span data-ttu-id="1fe47-126">たとえば、ユーザーが Lync サイトへのログオン速度が遅いという問題が頻繁に発生する場合、ネットワーク帯域幅の問題が原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1fe47-126">For example, if the users are experiencing frequent issues with slow logons to their Lync sites, network bandwidth issues may be the cause.</span></span> <span data-ttu-id="1fe47-127">問題の解決時間と、システムの可用性の停止による影響は、SLA と比較して確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fe47-127">Issue resolution times and the effect of any outages on system availability should be reviewed and compared with the SLA.</span></span> <span data-ttu-id="1fe47-128">アカウントマネージャーなどのサービスの問題について顧客と liaises したユーザーには、重大な問題があることを通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fe47-128">The person who liaises with the customer on service issues, such as an account manager, should be informed of any significant issues.</span></span>

</div>

<div>

## <a name="issue-management-tools"></a><span data-ttu-id="1fe47-129">問題管理ツール</span><span class="sxs-lookup"><span data-stu-id="1fe47-129">Issue management tools</span></span>

<span data-ttu-id="1fe47-130">サービスデスクツールを使用すると、スタッフは、新しい問題の記録、分類、優先順位付けを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1fe47-130">Service desk tools enable staff to record, classify, and prioritize new issues.</span></span> <span data-ttu-id="1fe47-131">ツールでは、複数のサポートチームによって、調査と診断を通じて問題のサービスリクエストを管理するワークフロープロセスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="1fe47-131">Tools will then provide the workflow processes to manage the issue service request through investigation and diagnosis, often by more than one support team.</span></span> <span data-ttu-id="1fe47-132">[ツール] では、解決時間や履歴の傾向に関するレポートを頻繁に提供します。また、過去の問題を検索するために使用できるナレッジベースデータベースも含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1fe47-132">Tools, which will frequently provide reports about resolution times and historical trends, may also include a knowledge base database, which can be used to search through past issues.</span></span>

<span data-ttu-id="1fe47-133">Microsoft サポート技術情報は、Microsoft によって発生したサポートの問題を記録したものです。</span><span class="sxs-lookup"><span data-stu-id="1fe47-133">The Microsoft Knowledge Base is a useful record of support issues that were encountered by Microsoft.</span></span> <span data-ttu-id="1fe47-134">詳細については、Microsoft サポート web サイト<http://go.microsoft.com/fwlink/?linkid=14898>() を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fe47-134">For more information, see the Microsoft Support website (<http://go.microsoft.com/fwlink/?linkid=14898>).</span></span>

<span data-ttu-id="1fe47-135">サードパーティのソフトウェアでは通常、組織のニーズに合わせてカスタマイズする必要があります。これには、チームの編成、レポート要件、SLA に必要な措置などがあります。</span><span class="sxs-lookup"><span data-stu-id="1fe47-135">Third-party software typically requires customization to suit the organization’s needs, such as the organization of teams, reporting requirements, and measures required by the SLA.</span></span>

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a><span data-ttu-id="1fe47-136">一元管理と分散管理</span><span class="sxs-lookup"><span data-stu-id="1fe47-136">Centralized vs. decentralized administration</span></span>

<span data-ttu-id="1fe47-137">システム管理タスクを実行するための役割と責任は、組織が一元管理モデル、分散モデル、または両方の組み合わせのいずれを使用しているかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1fe47-137">Roles and responsibilities for performing system administration tasks depend on whether the organization follows a centralized model, a decentralized model, or a combination of both.</span></span>

  - <span data-ttu-id="1fe47-138">**一元管理モデル**   では、1つまたは複数の管理グループが、Lync Server 環境全体の完全な制御を維持します。</span><span class="sxs-lookup"><span data-stu-id="1fe47-138">**Centralized Model**   In a centralized model, one or several administrative groups maintain complete control of the whole Lync Server environment.</span></span> <span data-ttu-id="1fe47-139">この管理モデルは、1つの情報技術グループによってすべての管理タスクが実行されるデータセンターに似ています。</span><span class="sxs-lookup"><span data-stu-id="1fe47-139">This administrative model resembles a data center where all administration tasks are performed by a single information technology group.</span></span> <span data-ttu-id="1fe47-140">チーム内の役割と責任は、経験と専門知識に基づいて定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fe47-140">Roles and responsibilities within the team should be defined according to experience and expertise.</span></span>

  - <span data-ttu-id="1fe47-141">**分散型モデル**   分散組織は、いくつかの地理的な場所に配置されており、Lync Server サーバーと管理者のチームがさまざまな場所で機能しています。</span><span class="sxs-lookup"><span data-stu-id="1fe47-141">**Decentralized Model**   Decentralized organizations are located in several geographic locations and have functioning Lync Server servers and teams of administrators in different locations.</span></span> <span data-ttu-id="1fe47-142">たとえば、地域管理スタッフと、Lync Server 2013 を実行している1つ以上のサーバーが、国/地域ごとに存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="1fe47-142">For example, there may be local administration staff and one or more servers that are running Lync Server 2013 for each country/region.</span></span> <span data-ttu-id="1fe47-143">または、Lync Server 2013 を実行しているサーバーのプールと北米向けの管理チーム、およびヨーロッパのサーバーのプールが存在する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="1fe47-143">Or, there may be a pool of servers that are running Lync Server 2013 and an administrative team for North America and one for Europe.</span></span> <span data-ttu-id="1fe47-144">場合によっては、管理者が自分の地理的領域のみを担当し、他の領域のリソースを管理するためのアクセス許可を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="1fe47-144">Sometimes, you may want administrators to be responsible only for their own geographical area and restrict permissions to administer resources in other areas.</span></span>

<span data-ttu-id="1fe47-145">Lync Server では、役割ベースのアクセス制御 (RBAC) を使って特定の管理タスクを特定のユーザーまたはグループに委任することもできます。</span><span class="sxs-lookup"><span data-stu-id="1fe47-145">Lync Server also allows you to delegate specific administrative tasks to specific people or groups by using role-based access control (RBAC).</span></span> <span data-ttu-id="1fe47-146">RBAC を使用すると、管理者は、特定のユーザー権限と権限を他の管理者に委任して、可能な管理タスクのサブセットを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="1fe47-146">RBAC allows administrators to delegate specific user rights and permissions to other administrators to perform a subset of the administrative tasks possible.</span></span> <span data-ttu-id="1fe47-147">RBAC を使うことで、ユーザーに割り当てられている RBAC の役割に応じて、特定の管理タスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="1fe47-147">By using RBAC, the user’s ability to perform specific administrative tasks depends on the RBAC roles that are assigned to the user.</span></span> <span data-ttu-id="1fe47-148">RBAC には、ユーザーがメンバーになっている RBAC の役割に基づいてユーザーが実行できるコマンドレットの一覧が用意されています。</span><span class="sxs-lookup"><span data-stu-id="1fe47-148">RBAC provides a list of cmdlets that the user can run based on the RBAC roles that the user is a member of.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

