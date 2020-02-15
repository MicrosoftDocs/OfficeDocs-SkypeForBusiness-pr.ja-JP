---
title: 'Lync Server 2013: 応答グループアプリケーションの概要'
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
ms.openlocfilehash: d63f13442588a84039fee6e1147a9c29e821e14a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a><span data-ttu-id="cc96e-102">Lync Server 2013 の応答グループアプリケーションの概要</span><span class="sxs-lookup"><span data-stu-id="cc96e-102">Overview of the Response Group application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc96e-103">_**トピックの最終更新日:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="cc96e-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="cc96e-104">発信者が応答グループを呼び出すと、その通話は、ハントグループに基づいてエージェントにルーティングされるか、対話式音声応答 (IVR) の質問に対する発信者の回答になります。</span><span class="sxs-lookup"><span data-stu-id="cc96e-104">When a caller calls a response group, the call is routed to an agent based on a hunt group or the caller's answers to interactive voice response (IVR) questions.</span></span> <span data-ttu-id="cc96e-105">応答グループアプリケーションは、標準の応答グループルーティング方法を使用して、通話を次の利用可能なエージェントにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="cc96e-105">The Response Group application uses standard response group routing methods to route the call to the next available agent.</span></span> <span data-ttu-id="cc96e-106">通話ルーティング方法には、シリアル、最長アイドル、並列、ラウンドロビン、およびアテンダントルーティングがあります (つまり、すべてのエージェントは、現在のプレゼンスに関係なく、すべての着信呼び出しに対して同じ時間に呼び出されます)。</span><span class="sxs-lookup"><span data-stu-id="cc96e-106">Call routing methods include serial, longest-idle, parallel, round robin, and Attendant routing (that is, all agents are called at the same time for every incoming call, regardless of their current presence).</span></span> <span data-ttu-id="cc96e-107">利用可能なエージェントがない場合は、エージェントが使用可能になるまで、呼び出しがキューに保持されます。</span><span class="sxs-lookup"><span data-stu-id="cc96e-107">If no agents are available, the call is held in a queue until an agent is available.</span></span> <span data-ttu-id="cc96e-108">キュー内では、利用可能なエージェントが通話を受け付けるまで、発信者は音楽を聞くことができます。</span><span class="sxs-lookup"><span data-stu-id="cc96e-108">While in the queue, the caller hears music until an available agent accepts the call.</span></span> <span data-ttu-id="cc96e-109">キューがいっぱいになった場合、またはキュー内で呼び出しがタイムアウトになった場合は、発信者がメッセージを聞いた後に切断されるか別の宛先に転送されます。</span><span class="sxs-lookup"><span data-stu-id="cc96e-109">If the queue is full, or if the call times out while in the queue, the caller might hear a message and then is either disconnected or transferred to a different destination.</span></span> <span data-ttu-id="cc96e-110">エージェントが呼び出しを受け入れた場合、管理者が応答グループを構成する方法によっては、発信者がエージェントの id を表示することができない場合があります。</span><span class="sxs-lookup"><span data-stu-id="cc96e-110">When an agent accepts the call, the caller might or might not be able to see the agent's identity, depending on how the administrator configures the response group.</span></span> <span data-ttu-id="cc96e-111">エージェントは、公式にすることができます。つまり、グループにルーティングされた通話を受け付ける前にグループにサインインする必要があります。または、非公式で、つまり、呼び出しを受け入れるためにグループにサインインしたり、グループからサインアウトしたりしないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="cc96e-111">Agents can either be formal, which means that they must sign in to the group before they can accept calls routed to the group, or informal, which means that they do not sign into and out of the group to accept calls.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cc96e-p102">社内ユーザーのみがエージェントであることができます。エージェントが社内からオンラインに移動した場合、応答グループ呼び出しはそのエージェントに送られません。</span><span class="sxs-lookup"><span data-stu-id="cc96e-p102">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="cc96e-114">応答グループアプリケーションは、対戦処理と呼ばれる内部サービスを使用して、通話をキューに置いて、利用可能なエージェントを見つけます。</span><span class="sxs-lookup"><span data-stu-id="cc96e-114">The Response Group application uses an internal service, called Match Making, to queue calls and find available agents.</span></span> <span data-ttu-id="cc96e-115">応答グループアプリケーションを実行する各コンピューターは、対戦するサービスを実行しますが、同時にアクティブになるのは Lync Server プールごとに1つのサービスを提供するサービスのみですが、それ以外の場合はパッシブとなります。</span><span class="sxs-lookup"><span data-stu-id="cc96e-115">Each computer that runs the Response Group application runs the Match Making service, but only one Match Making service per Lync Server pool is active at a time--the others are passive.</span></span> <span data-ttu-id="cc96e-116">予定外の停止時にアクティブなマッチ メイキング サービスが使用できなくなった場合、パッシブなマッチ メイキング サービスの 1 つがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="cc96e-116">If the active Match Making service becomes unavailable during an unplanned outage, one of the passive Match Making services becomes active.</span></span> <span data-ttu-id="cc96e-117">応答グループアプリケーションは、通話のルーティングとキューが中断されないことを確認するのに最適です。</span><span class="sxs-lookup"><span data-stu-id="cc96e-117">The Response Group application does its best to make sure that call routing and queuing continues uninterrupted.</span></span> <span data-ttu-id="cc96e-118">ただし、マッチ メイキング サービスの移行が発生した場合、転送中にサービスの移行が発生した通話はすべて失われます。</span><span class="sxs-lookup"><span data-stu-id="cc96e-118">However, when a Match Making service transition occurs, any calls that are in transfer at the time are lost.</span></span> <span data-ttu-id="cc96e-119">たとえば、フロントエンドサーバーが停止しているために移行が発生している場合、そのフロントエンドサーバー上のアクティブな対戦の作成サービスによって現在処理されているすべての呼び出しも失われます。</span><span class="sxs-lookup"><span data-stu-id="cc96e-119">For example, if the transition is due to the Front End Server going down, any calls currently being handled by the active Match Making service on that Front End Server are also lost.</span></span>



</div>

<span data-ttu-id="cc96e-120">Lync Server 2013 では、応答グループを管理するために2つの管理役割を使用できます。応答グループマネージャーと応答グループの管理者。</span><span class="sxs-lookup"><span data-stu-id="cc96e-120">In Lync Server 2013, two management roles are available for managing response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="cc96e-121">応答グループ管理者は、応答グループのすべての側面を管理できます。</span><span class="sxs-lookup"><span data-stu-id="cc96e-121">Response Group Administrators can manage any aspect of any response group.</span></span> <span data-ttu-id="cc96e-122">応答グループマネージャーは、特定の側面のみを管理でき、自分が所有する応答グループに対してのみ管理できます。</span><span class="sxs-lookup"><span data-stu-id="cc96e-122">Response Group Managers can manage only certain aspects, and only for the response groups that they own.</span></span> <span data-ttu-id="cc96e-123">エンタープライズ Voip が有効になっているすべてのユーザーに特定の応答グループの制限された責任を委任できるため、新しい管理者の役割によって管理コストを削減することができます。</span><span class="sxs-lookup"><span data-stu-id="cc96e-123">The new Manager role can help reduce administration costs, because you can delegate limited responsibilities for specific response groups to any user who is enabled for Enterprise Voice.</span></span>

<span data-ttu-id="cc96e-124">新しい管理者の役割に対応するために、Lync Server 2013 応答グループアプリケーションでは、管理または非管理の**ワークフローの種類**が導入されています。</span><span class="sxs-lookup"><span data-stu-id="cc96e-124">To accommodate the new Manager role, Lync Server 2013 Response Group application introduces a **Workflow Type** of Managed or Unmanaged.</span></span> <span data-ttu-id="cc96e-125">次の表では、管理対象の応答グループと非管理対象の応答グループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cc96e-125">The following table describes Managed and Unmanaged response groups.</span></span>

### <a name="managed-and-unmanaged-response-groups"></a><span data-ttu-id="cc96e-126">管理対象の応答グループと非管理対象の応答グループ</span><span class="sxs-lookup"><span data-stu-id="cc96e-126">Managed and Unmanaged Response Groups</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc96e-127">応答グループの種類</span><span class="sxs-lookup"><span data-stu-id="cc96e-127">Response group type</span></span></th>
<th><span data-ttu-id="cc96e-128">説明</span><span class="sxs-lookup"><span data-stu-id="cc96e-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc96e-129">Unmanaged</span><span class="sxs-lookup"><span data-stu-id="cc96e-129">Unmanaged</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="cc96e-130">非管理対象の応答グループには、マネージャーが割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="cc96e-130">Unmanaged response groups have no assigned Managers.</span></span> <span data-ttu-id="cc96e-131">応答グループ管理者のみが、これらの応答グループを構成できます。</span><span class="sxs-lookup"><span data-stu-id="cc96e-131">Only the Response Group Administrator can configure these response groups.</span></span></p></li>
<li><p><span data-ttu-id="cc96e-132">非管理対象の複数の応答グループが、1 つのキューまたはエージェント グループを共有できます。</span><span class="sxs-lookup"><span data-stu-id="cc96e-132">Multiple unmanaged response groups can share a queue or agent group.</span></span></p></li>
<li><p><span data-ttu-id="cc96e-133">応答グループを以前のバージョンから Lync Server 2013 に移行する場合、種類は [非管理] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cc96e-133">When you migrate response groups from a prior version to Lync Server 2013, the type is set to Unmanaged.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc96e-134">マネージ型</span><span class="sxs-lookup"><span data-stu-id="cc96e-134">Managed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="cc96e-135">応答グループ管理者は、管理された応答グループのあらゆる側面を構成できます。</span><span class="sxs-lookup"><span data-stu-id="cc96e-135">Response Group Administrators can configure any aspect of managed response groups.</span></span></p></li>
<li><p><span data-ttu-id="cc96e-136">応答グループマネージャーは、明示的に割り当てられていない応答グループを表示または変更できません。</span><span class="sxs-lookup"><span data-stu-id="cc96e-136">Response Group Managers cannot view or modify response groups that are not explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="cc96e-137">応答グループマネージャーは、明示的に割り当てられた応答グループの一部の設定のみを構成できます。</span><span class="sxs-lookup"><span data-stu-id="cc96e-137">Response Group Managers can configure only some settings for the response groups that are explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="cc96e-138">管理対象の応答グループは、他の応答グループ (管理対象または非管理対象を問わず) とはキューまたはエージェント グループを共有できません。</span><span class="sxs-lookup"><span data-stu-id="cc96e-138">Managed response groups can't share any queues or agent groups with any other response group, managed or unmanaged.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cc96e-139">次の表では、応答グループマネージャーが割り当てられている応答グループに対して実行できる操作とできないアクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cc96e-139">The following table describes the actions that Response Group Managers can and cannot perform for the response groups assigned to them.</span></span>

### <a name="response-group-manager-capabilities"></a><span data-ttu-id="cc96e-140">応答グループ マネージャーの権限</span><span class="sxs-lookup"><span data-stu-id="cc96e-140">Response Group Manager Capabilities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc96e-141">構成可能</span><span class="sxs-lookup"><span data-stu-id="cc96e-141">Can configure:</span></span></th>
<th><span data-ttu-id="cc96e-142">作成、削除、または構成可能</span><span class="sxs-lookup"><span data-stu-id="cc96e-142">Can create, delete, or configure:</span></span></th>
<th><span data-ttu-id="cc96e-143">できません</span><span class="sxs-lookup"><span data-stu-id="cc96e-143">Cannot:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="cc96e-144">エージェント</span><span class="sxs-lookup"><span data-stu-id="cc96e-144">Agents</span></span></p></li>
<li><p><span data-ttu-id="cc96e-145">ウェルカム メッセージ</span><span class="sxs-lookup"><span data-stu-id="cc96e-145">Welcome message</span></span></p></li>
<li><p><span data-ttu-id="cc96e-146">応答グループ名</span><span class="sxs-lookup"><span data-stu-id="cc96e-146">Response Group name</span></span></p></li>
<li><p><span data-ttu-id="cc96e-147">説明</span><span class="sxs-lookup"><span data-stu-id="cc96e-147">Description</span></span></p></li>
<li><p><span data-ttu-id="cc96e-148">表示番号</span><span class="sxs-lookup"><span data-stu-id="cc96e-148">Display number</span></span></p></li>
<li><p><span data-ttu-id="cc96e-149">営業時間</span><span class="sxs-lookup"><span data-stu-id="cc96e-149">Business hours</span></span></p></li>
<li><p><span data-ttu-id="cc96e-150">保留音</span><span class="sxs-lookup"><span data-stu-id="cc96e-150">Music on hold</span></span></p></li>
<li><p><span data-ttu-id="cc96e-151">ステータス (アクティブ/非アクティブ)</span><span class="sxs-lookup"><span data-stu-id="cc96e-151">Status (active/inactive)</span></span></p></li>
<li><p><span data-ttu-id="cc96e-152">ハント グループまたは対話型音声応答 (IVR) のワークフロー</span><span class="sxs-lookup"><span data-stu-id="cc96e-152">Hunt group workflows or Interactive voice response (IVR) workflows</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="cc96e-153">エージェント グループ</span><span class="sxs-lookup"><span data-stu-id="cc96e-153">Agent Groups</span></span></p></li>
<li><p><span data-ttu-id="cc96e-154">キュー</span><span class="sxs-lookup"><span data-stu-id="cc96e-154">Queues</span></span></p></li>
<li><p><span data-ttu-id="cc96e-155">休日セット</span><span class="sxs-lookup"><span data-stu-id="cc96e-155">Holiday sets</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="cc96e-156">あらゆる種類のワークフローの作成または削除</span><span class="sxs-lookup"><span data-stu-id="cc96e-156">Create or delete any type of workflow</span></span></p></li>
<li><p><span data-ttu-id="cc96e-157">[<strong>SIP URI</strong>]、[<strong>電話番号</strong>]、[<strong>ワークフローの種類</strong>] など、応答グループの核となる設定の変更</span><span class="sxs-lookup"><span data-stu-id="cc96e-157">Modify core response group settings, such as: <strong>SIP URI</strong>, <strong>Telephone Number</strong>, or <strong>Workflow Type</strong>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cc96e-158">応答グループマネージャーは、次のツールを使用して、指定された応答グループを管理できます。</span><span class="sxs-lookup"><span data-stu-id="cc96e-158">Response Group Managers can use the following tools to manage their designated response groups.</span></span>

  - <span data-ttu-id="cc96e-159">Lync Server コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="cc96e-159">Lync Server Control Panel</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cc96e-160">応答グループマネージャーは、このツールを使用して応答グループの設定のみを管理できます。</span><span class="sxs-lookup"><span data-stu-id="cc96e-160">Response Group Managers can only manage Response Group settings with this tool.</span></span> <span data-ttu-id="cc96e-161">その他の Lync Server の設定は、マネージャーでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="cc96e-161">Other Lync Server settings are not available to Managers.</span></span>

    
    </div>

  - <span data-ttu-id="cc96e-162">応答グループ構成ツール</span><span class="sxs-lookup"><span data-stu-id="cc96e-162">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="cc96e-163">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="cc96e-163">Lync Server Management Shell</span></span>

<span data-ttu-id="cc96e-164">応答グループは、部門環境やワークグループ環境に適しています (詳細については、「 [Lync Server 2013 の応答グループの容量計画](lync-server-2013-capacity-planning-for-response-group.md)」を参照してください)。また、完全に新しいテレフォニーインストールに展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="cc96e-164">Response Group scales well to departmental or workgroup environments (for details, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) and can be deployed in entirely new telephony installations.</span></span> <span data-ttu-id="cc96e-165">エンタープライズ Voip 展開とローカルの電話会社ネットワークからの着信呼び出しをサポートします。</span><span class="sxs-lookup"><span data-stu-id="cc96e-165">It supports incoming calls from the Enterprise Voice deployment and from the local carrier network.</span></span> <span data-ttu-id="cc96e-166">エージェントは、Lync 2013、Lync 2010、Lync 2010 アテンダント、または Lync Phone のエディションを使用して、それらにルーティングされた通話を取得できます。</span><span class="sxs-lookup"><span data-stu-id="cc96e-166">Agents can use Lync 2013, Lync 2010, Lync 2010 Attendant, or Lync Phone Edition to take the calls routed to them.</span></span>

<span data-ttu-id="cc96e-167">応答グループアプリケーションは、エンタープライズ Voip のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="cc96e-167">The Response Group application is a component of Enterprise Voice.</span></span> <span data-ttu-id="cc96e-168">エンタープライズ Voip を展開すると、応答グループアプリケーションがインストールされ、自動的にアクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="cc96e-168">When you deploy Enterprise Voice, the Response Group application is installed and activated automatically.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

