---
title: 'Lync Server 2013: 応答グループアプリケーションの概要'
description: 'Lync Server 2013: 応答グループアプリケーションの概要。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 763a64adcf0eaf43e8f98a49cd850882ca9c91c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552383"
---
# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a><span data-ttu-id="38bb2-103">Lync Server 2013 の応答グループアプリケーションの概要</span><span class="sxs-lookup"><span data-stu-id="38bb2-103">Overview of the Response Group application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38bb2-104">_**トピックの最終更新日:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="38bb2-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="38bb2-105">発信者が応答グループを呼び出すと、その通話は、ハントグループに基づいてエージェントにルーティングされるか、対話式音声応答 (IVR) の質問に対する発信者の回答になります。</span><span class="sxs-lookup"><span data-stu-id="38bb2-105">When a caller calls a response group, the call is routed to an agent based on a hunt group or the caller's answers to interactive voice response (IVR) questions.</span></span> <span data-ttu-id="38bb2-106">応答グループアプリケーションは、標準の応答グループルーティング方法を使用して、通話を次の利用可能なエージェントにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="38bb2-106">The Response Group application uses standard response group routing methods to route the call to the next available agent.</span></span> <span data-ttu-id="38bb2-107">通話ルーティング方法には、シリアル、最長アイドル、並列、ラウンドロビン、およびアテンダントルーティングがあります (つまり、すべてのエージェントは、現在のプレゼンスに関係なく、すべての着信呼び出しに対して同じ時間に呼び出されます)。</span><span class="sxs-lookup"><span data-stu-id="38bb2-107">Call routing methods include serial, longest-idle, parallel, round robin, and Attendant routing (that is, all agents are called at the same time for every incoming call, regardless of their current presence).</span></span> <span data-ttu-id="38bb2-108">利用可能なエージェントがない場合は、エージェントが使用可能になるまで、呼び出しがキューに保持されます。</span><span class="sxs-lookup"><span data-stu-id="38bb2-108">If no agents are available, the call is held in a queue until an agent is available.</span></span> <span data-ttu-id="38bb2-109">キュー内では、利用可能なエージェントが通話を受け付けるまで、発信者は音楽を聞くことができます。</span><span class="sxs-lookup"><span data-stu-id="38bb2-109">While in the queue, the caller hears music until an available agent accepts the call.</span></span> <span data-ttu-id="38bb2-110">キューがいっぱいになった場合、またはキュー内で呼び出しがタイムアウトになった場合は、発信者がメッセージを聞いた後に切断されるか別の宛先に転送されます。</span><span class="sxs-lookup"><span data-stu-id="38bb2-110">If the queue is full, or if the call times out while in the queue, the caller might hear a message and then is either disconnected or transferred to a different destination.</span></span> <span data-ttu-id="38bb2-111">エージェントが呼び出しを受け入れた場合、管理者が応答グループを構成する方法によっては、発信者がエージェントの id を表示することができない場合があります。</span><span class="sxs-lookup"><span data-stu-id="38bb2-111">When an agent accepts the call, the caller might or might not be able to see the agent's identity, depending on how the administrator configures the response group.</span></span> <span data-ttu-id="38bb2-112">エージェントは、公式にすることができます。つまり、グループにルーティングされた通話を受け付ける前にグループにサインインする必要があります。または、非公式で、つまり、呼び出しを受け入れるためにグループにサインインしたり、グループからサインアウトしたりしないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="38bb2-112">Agents can either be formal, which means that they must sign in to the group before they can accept calls routed to the group, or informal, which means that they do not sign into and out of the group to accept calls.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="38bb2-p102">社内ユーザーのみがエージェントであることができます。エージェントが社内からオンラインに移動した場合、応答グループ呼び出しはそのエージェントに送られません。</span><span class="sxs-lookup"><span data-stu-id="38bb2-p102">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="38bb2-115">応答グループアプリケーションは、対戦処理と呼ばれる内部サービスを使用して、通話をキューに置いて、利用可能なエージェントを見つけます。</span><span class="sxs-lookup"><span data-stu-id="38bb2-115">The Response Group application uses an internal service, called Match Making, to queue calls and find available agents.</span></span> <span data-ttu-id="38bb2-116">応答グループアプリケーションを実行する各コンピューターは、対戦するサービスを実行しますが、同時にアクティブになるのは Lync Server プールごとに1つのサービスを提供するサービスのみですが、それ以外の場合はパッシブとなります。</span><span class="sxs-lookup"><span data-stu-id="38bb2-116">Each computer that runs the Response Group application runs the Match Making service, but only one Match Making service per Lync Server pool is active at a time--the others are passive.</span></span> <span data-ttu-id="38bb2-117">予定外の停止時にアクティブなマッチ メイキング サービスが使用できなくなった場合、パッシブなマッチ メイキング サービスの 1 つがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="38bb2-117">If the active Match Making service becomes unavailable during an unplanned outage, one of the passive Match Making services becomes active.</span></span> <span data-ttu-id="38bb2-118">応答グループアプリケーションは、通話のルーティングとキューが中断されないことを確認するのに最適です。</span><span class="sxs-lookup"><span data-stu-id="38bb2-118">The Response Group application does its best to make sure that call routing and queuing continues uninterrupted.</span></span> <span data-ttu-id="38bb2-119">ただし、マッチ メイキング サービスの移行が発生した場合、転送中にサービスの移行が発生した通話はすべて失われます。</span><span class="sxs-lookup"><span data-stu-id="38bb2-119">However, when a Match Making service transition occurs, any calls that are in transfer at the time are lost.</span></span> <span data-ttu-id="38bb2-120">たとえば、フロントエンドサーバーが停止しているために移行が発生している場合、そのフロントエンドサーバー上のアクティブな対戦の作成サービスによって現在処理されているすべての呼び出しも失われます。</span><span class="sxs-lookup"><span data-stu-id="38bb2-120">For example, if the transition is due to the Front End Server going down, any calls currently being handled by the active Match Making service on that Front End Server are also lost.</span></span>



</div>

<span data-ttu-id="38bb2-121">Lync Server 2013 では、応答グループを管理するために2つの管理役割を使用できます。応答グループマネージャーと応答グループの管理者。</span><span class="sxs-lookup"><span data-stu-id="38bb2-121">In Lync Server 2013, two management roles are available for managing response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="38bb2-122">応答グループ管理者は、応答グループのすべての側面を管理できます。</span><span class="sxs-lookup"><span data-stu-id="38bb2-122">Response Group Administrators can manage any aspect of any response group.</span></span> <span data-ttu-id="38bb2-123">応答グループマネージャーは、特定の側面のみを管理でき、自分が所有する応答グループに対してのみ管理できます。</span><span class="sxs-lookup"><span data-stu-id="38bb2-123">Response Group Managers can manage only certain aspects, and only for the response groups that they own.</span></span> <span data-ttu-id="38bb2-124">エンタープライズ Voip が有効になっているすべてのユーザーに特定の応答グループの制限された責任を委任できるため、新しい管理者の役割によって管理コストを削減することができます。</span><span class="sxs-lookup"><span data-stu-id="38bb2-124">The new Manager role can help reduce administration costs, because you can delegate limited responsibilities for specific response groups to any user who is enabled for Enterprise Voice.</span></span>

<span data-ttu-id="38bb2-125">新しい管理者の役割に対応するために、Lync Server 2013 応答グループアプリケーションでは、管理または非管理の **ワークフローの種類** が導入されています。</span><span class="sxs-lookup"><span data-stu-id="38bb2-125">To accommodate the new Manager role, Lync Server 2013 Response Group application introduces a **Workflow Type** of Managed or Unmanaged.</span></span> <span data-ttu-id="38bb2-126">次の表では、管理対象の応答グループと非管理対象の応答グループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="38bb2-126">The following table describes Managed and Unmanaged response groups.</span></span>

### <a name="managed-and-unmanaged-response-groups"></a><span data-ttu-id="38bb2-127">管理対象の応答グループと非管理対象の応答グループ</span><span class="sxs-lookup"><span data-stu-id="38bb2-127">Managed and Unmanaged Response Groups</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38bb2-128">応答グループの種類</span><span class="sxs-lookup"><span data-stu-id="38bb2-128">Response group type</span></span></th>
<th><span data-ttu-id="38bb2-129">説明</span><span class="sxs-lookup"><span data-stu-id="38bb2-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38bb2-130">Unmanaged</span><span class="sxs-lookup"><span data-stu-id="38bb2-130">Unmanaged</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="38bb2-131">非管理対象の応答グループには、マネージャーが割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="38bb2-131">Unmanaged response groups have no assigned Managers.</span></span> <span data-ttu-id="38bb2-132">応答グループ管理者のみが、これらの応答グループを構成できます。</span><span class="sxs-lookup"><span data-stu-id="38bb2-132">Only the Response Group Administrator can configure these response groups.</span></span></p></li>
<li><p><span data-ttu-id="38bb2-133">非管理対象の複数の応答グループが、1 つのキューまたはエージェント グループを共有できます。</span><span class="sxs-lookup"><span data-stu-id="38bb2-133">Multiple unmanaged response groups can share a queue or agent group.</span></span></p></li>
<li><p><span data-ttu-id="38bb2-134">応答グループを以前のバージョンから Lync Server 2013 に移行する場合、種類は [非管理] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="38bb2-134">When you migrate response groups from a prior version to Lync Server 2013, the type is set to Unmanaged.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38bb2-135">管理対象</span><span class="sxs-lookup"><span data-stu-id="38bb2-135">Managed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="38bb2-136">応答グループ管理者は、管理された応答グループのあらゆる側面を構成できます。</span><span class="sxs-lookup"><span data-stu-id="38bb2-136">Response Group Administrators can configure any aspect of managed response groups.</span></span></p></li>
<li><p><span data-ttu-id="38bb2-137">応答グループマネージャーは、明示的に割り当てられていない応答グループを表示または変更できません。</span><span class="sxs-lookup"><span data-stu-id="38bb2-137">Response Group Managers cannot view or modify response groups that are not explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="38bb2-138">応答グループマネージャーは、明示的に割り当てられた応答グループの一部の設定のみを構成できます。</span><span class="sxs-lookup"><span data-stu-id="38bb2-138">Response Group Managers can configure only some settings for the response groups that are explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="38bb2-139">管理対象の応答グループは、他の応答グループ (管理対象または非管理対象を問わず) とはキューまたはエージェント グループを共有できません。</span><span class="sxs-lookup"><span data-stu-id="38bb2-139">Managed response groups can't share any queues or agent groups with any other response group, managed or unmanaged.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="38bb2-140">次の表では、応答グループマネージャーが割り当てられている応答グループに対して実行できる操作とできないアクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="38bb2-140">The following table describes the actions that Response Group Managers can and cannot perform for the response groups assigned to them.</span></span>

### <a name="response-group-manager-capabilities"></a><span data-ttu-id="38bb2-141">応答グループ マネージャーの権限</span><span class="sxs-lookup"><span data-stu-id="38bb2-141">Response Group Manager Capabilities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38bb2-142">構成可能</span><span class="sxs-lookup"><span data-stu-id="38bb2-142">Can configure:</span></span></th>
<th><span data-ttu-id="38bb2-143">作成、削除、または構成可能</span><span class="sxs-lookup"><span data-stu-id="38bb2-143">Can create, delete, or configure:</span></span></th>
<th><span data-ttu-id="38bb2-144">できません</span><span class="sxs-lookup"><span data-stu-id="38bb2-144">Cannot:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="38bb2-145">Agents</span><span class="sxs-lookup"><span data-stu-id="38bb2-145">Agents</span></span></p></li>
<li><p><span data-ttu-id="38bb2-146">ウェルカム メッセージ</span><span class="sxs-lookup"><span data-stu-id="38bb2-146">Welcome message</span></span></p></li>
<li><p><span data-ttu-id="38bb2-147">応答グループ名</span><span class="sxs-lookup"><span data-stu-id="38bb2-147">Response Group name</span></span></p></li>
<li><p><span data-ttu-id="38bb2-148">説明</span><span class="sxs-lookup"><span data-stu-id="38bb2-148">Description</span></span></p></li>
<li><p><span data-ttu-id="38bb2-149">表示番号</span><span class="sxs-lookup"><span data-stu-id="38bb2-149">Display number</span></span></p></li>
<li><p><span data-ttu-id="38bb2-150">営業時間</span><span class="sxs-lookup"><span data-stu-id="38bb2-150">Business hours</span></span></p></li>
<li><p><span data-ttu-id="38bb2-151">保留音</span><span class="sxs-lookup"><span data-stu-id="38bb2-151">Music on hold</span></span></p></li>
<li><p><span data-ttu-id="38bb2-152">ステータス (アクティブ/非アクティブ)</span><span class="sxs-lookup"><span data-stu-id="38bb2-152">Status (active/inactive)</span></span></p></li>
<li><p><span data-ttu-id="38bb2-153">ハント グループまたは対話型音声応答 (IVR) のワークフロー</span><span class="sxs-lookup"><span data-stu-id="38bb2-153">Hunt group workflows or Interactive voice response (IVR) workflows</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="38bb2-154">エージェント グループ</span><span class="sxs-lookup"><span data-stu-id="38bb2-154">Agent Groups</span></span></p></li>
<li><p><span data-ttu-id="38bb2-155">キュー</span><span class="sxs-lookup"><span data-stu-id="38bb2-155">Queues</span></span></p></li>
<li><p><span data-ttu-id="38bb2-156">休日セット</span><span class="sxs-lookup"><span data-stu-id="38bb2-156">Holiday sets</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="38bb2-157">あらゆる種類のワークフローの作成または削除</span><span class="sxs-lookup"><span data-stu-id="38bb2-157">Create or delete any type of workflow</span></span></p></li>
<li><p><span data-ttu-id="38bb2-158">[<strong>SIP URI</strong>]、[<strong>電話番号</strong>]、[<strong>ワークフローの種類</strong>] など、応答グループの核となる設定の変更</span><span class="sxs-lookup"><span data-stu-id="38bb2-158">Modify core response group settings, such as: <strong>SIP URI</strong>, <strong>Telephone Number</strong>, or <strong>Workflow Type</strong>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="38bb2-159">応答グループマネージャーは、次のツールを使用して、指定された応答グループを管理できます。</span><span class="sxs-lookup"><span data-stu-id="38bb2-159">Response Group Managers can use the following tools to manage their designated response groups.</span></span>

  - <span data-ttu-id="38bb2-160">Lync Server コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="38bb2-160">Lync Server Control Panel</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38bb2-161">応答グループマネージャーは、このツールを使用して応答グループの設定のみを管理できます。</span><span class="sxs-lookup"><span data-stu-id="38bb2-161">Response Group Managers can only manage Response Group settings with this tool.</span></span> <span data-ttu-id="38bb2-162">その他の Lync Server の設定は、マネージャーでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="38bb2-162">Other Lync Server settings are not available to Managers.</span></span>

    
    </div>

  - <span data-ttu-id="38bb2-163">応答グループ構成ツール</span><span class="sxs-lookup"><span data-stu-id="38bb2-163">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="38bb2-164">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="38bb2-164">Lync Server Management Shell</span></span>

<span data-ttu-id="38bb2-165">応答グループは、部門環境やワークグループ環境に適しています (詳細については、「 [Lync Server 2013 の応答グループの容量計画](lync-server-2013-capacity-planning-for-response-group.md)」を参照してください)。また、完全に新しいテレフォニーインストールに展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="38bb2-165">Response Group scales well to departmental or workgroup environments (for details, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) and can be deployed in entirely new telephony installations.</span></span> <span data-ttu-id="38bb2-166">エンタープライズ Voip 展開とローカルの電話会社ネットワークからの着信呼び出しをサポートします。</span><span class="sxs-lookup"><span data-stu-id="38bb2-166">It supports incoming calls from the Enterprise Voice deployment and from the local carrier network.</span></span> <span data-ttu-id="38bb2-167">エージェントは、Lync 2013、Lync 2010、Lync 2010 アテンダント、または Lync Phone のエディションを使用して、それらにルーティングされた通話を取得できます。</span><span class="sxs-lookup"><span data-stu-id="38bb2-167">Agents can use Lync 2013, Lync 2010, Lync 2010 Attendant, or Lync Phone Edition to take the calls routed to them.</span></span>

<span data-ttu-id="38bb2-168">応答グループアプリケーションは、エンタープライズ Voip のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="38bb2-168">The Response Group application is a component of Enterprise Voice.</span></span> <span data-ttu-id="38bb2-169">エンタープライズ Voip を展開すると、応答グループアプリケーションがインストールされ、自動的にアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="38bb2-169">When you deploy Enterprise Voice, the Response Group application is installed and activated automatically.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

