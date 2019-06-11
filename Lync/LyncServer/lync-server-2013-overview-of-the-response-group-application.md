---
title: 'Lync Server 2013: 応答グループアプリケーションの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b523a05509b0043effb8cb2b761d7ee06fd36751
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a><span data-ttu-id="af256-102">Lync Server 2013 の応答グループアプリケーションの概要</span><span class="sxs-lookup"><span data-stu-id="af256-102">Overview of the Response Group application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af256-103">_**最終更新日:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="af256-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="af256-104">発信者が応答グループに対して通話を行うと、その通話は、ハント グループまたは対話型音声応答 (IVR) の質問に対する発信者の回答に基づいて、エージェントにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="af256-104">When a caller calls a response group, the call is routed to an agent based on a hunt group or the caller's answers to interactive voice response (IVR) questions.</span></span> <span data-ttu-id="af256-105">応答グループアプリケーションは、標準応答グループルーティングメソッドを使用して、次の使用可能なエージェントに通話をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="af256-105">The Response Group application uses standard response group routing methods to route the call to the next available agent.</span></span> <span data-ttu-id="af256-106">通話ルーティングメソッドには、シリアル、最長アイドル、並列、ラウンドロビン、およびアテンダントルーティングが含まれます (つまり、現在のプレゼンスに関係なく、すべての着信通話に対してすべてのエージェントが同時に呼び出されます)。</span><span class="sxs-lookup"><span data-stu-id="af256-106">Call routing methods include serial, longest-idle, parallel, round robin, and Attendant routing (that is, all agents are called at the same time for every incoming call, regardless of their current presence).</span></span> <span data-ttu-id="af256-107">利用可能なエージェントがない場合は、エージェントが利用可能になるまで、通話はキュー内に保持されます。</span><span class="sxs-lookup"><span data-stu-id="af256-107">If no agents are available, the call is held in a queue until an agent is available.</span></span> <span data-ttu-id="af256-108">キュー内で、利用可能なエージェントが通話を受け入れ終わるまで、発信者は音楽を耳にします。</span><span class="sxs-lookup"><span data-stu-id="af256-108">While in the queue, the caller hears music until an available agent accepts the call.</span></span> <span data-ttu-id="af256-109">キューがいっぱいになっている場合、またはキューの途中で呼び出しがタイムアウトした場合、発信者はメッセージを聞き、切断されているか、別の場所に移動している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="af256-109">If the queue is full, or if the call times out while in the queue, the caller might hear a message and then is either disconnected or transferred to a different destination.</span></span> <span data-ttu-id="af256-110">エージェントが通話を受け入れた場合、管理者によって応答グループがどのように構成されているかに応じて、呼び出し元は、エージェントの id を確認できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="af256-110">When an agent accepts the call, the caller might or might not be able to see the agent's identity, depending on how the administrator configures the response group.</span></span> <span data-ttu-id="af256-111">エージェントは、正式な場合もあります。つまり、グループにサインインする前にグループにサインインする必要があります。つまり、グループに対してルーティングされた通話を受け入れる前にグループにサインインしたり、非公式にしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="af256-111">Agents can either be formal, which means that they must sign in to the group before they can accept calls routed to the group, or informal, which means that they do not sign into and out of the group to accept calls.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="af256-112">エージェントにできるのは社内ユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="af256-112">Only on-premises users can be agents.</span></span> <span data-ttu-id="af256-113">エージェントがオンプレミスからオンラインに移行された場合、応答グループの呼び出しはそのエージェントにルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="af256-113">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="af256-114">応答グループのアプリケーションでは、通話をキューに記録して使用可能なエージェントを見つけるために、Match と呼ばれる内部サービスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="af256-114">The Response Group application uses an internal service, called Match Making, to queue calls and find available agents.</span></span> <span data-ttu-id="af256-115">応答グループアプリケーションを実行している各コンピューターは、Match サービスを実行しますが、1つの Lync Server プールに対してサービスを提供するサービスは1つだけです。その他は受動的です。</span><span class="sxs-lookup"><span data-stu-id="af256-115">Each computer that runs the Response Group application runs the Match Making service, but only one Match Making service per Lync Server pool is active at a time--the others are passive.</span></span> <span data-ttu-id="af256-116">予定外の停止時にアクティブなマッチ メイキング サービスが使用できなくなった場合、パッシブなマッチ メイキング サービスの 1 つがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="af256-116">If the active Match Making service becomes unavailable during an unplanned outage, one of the passive Match Making services becomes active.</span></span> <span data-ttu-id="af256-117">応答グループアプリケーションは、通話ルーティングとキューが中断されないようにします。</span><span class="sxs-lookup"><span data-stu-id="af256-117">The Response Group application does its best to make sure that call routing and queuing continues uninterrupted.</span></span> <span data-ttu-id="af256-118">ただし、マッチ メイキング サービスの移行が発生した場合、転送中にサービスの移行が発生した通話はすべて失われます。</span><span class="sxs-lookup"><span data-stu-id="af256-118">However, when a Match Making service transition occurs, any calls that are in transfer at the time are lost.</span></span> <span data-ttu-id="af256-119">たとえば、フロントエンドサーバーが停止するために移行が行われているために、現在アクティブになっている対戦によって処理されているすべての通話は失われます。</span><span class="sxs-lookup"><span data-stu-id="af256-119">For example, if the transition is due to the Front End Server going down, any calls currently being handled by the active Match Making service on that Front End Server are also lost.</span></span>



</div>

<span data-ttu-id="af256-120">Lync Server 2013 では、応答グループを管理するために2つの管理役割を利用できます。応答グループマネージャーと応答グループの管理者。</span><span class="sxs-lookup"><span data-stu-id="af256-120">In Lync Server 2013, two management roles are available for managing response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="af256-121">回答グループ管理者は、任意の応答グループの任意の局面を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="af256-121">Response Group Administrators can manage any aspect of any response group.</span></span> <span data-ttu-id="af256-122">応答グループマネージャーは、特定の側面のみを管理し、所有している応答グループに対してのみ管理できます。</span><span class="sxs-lookup"><span data-stu-id="af256-122">Response Group Managers can manage only certain aspects, and only for the response groups that they own.</span></span> <span data-ttu-id="af256-123">新しいマネージャーの役割は、管理コストの削減に役立ちます。特定の応答グループについては、エンタープライズ Voip が有効になっているすべてのユーザーに限定された責任を委任することができます。</span><span class="sxs-lookup"><span data-stu-id="af256-123">The new Manager role can help reduce administration costs, because you can delegate limited responsibilities for specific response groups to any user who is enabled for Enterprise Voice.</span></span>

<span data-ttu-id="af256-124">新しい管理者の役割に対応するために、Lync Server 2013 応答グループアプリケーションでは、管理または非管理の**ワークフローの種類**が導入されています。</span><span class="sxs-lookup"><span data-stu-id="af256-124">To accommodate the new Manager role, Lync Server 2013 Response Group application introduces a **Workflow Type** of Managed or Unmanaged.</span></span> <span data-ttu-id="af256-125">次の表では、管理対象の応答グループと非管理対象の応答グループについて説明します。</span><span class="sxs-lookup"><span data-stu-id="af256-125">The following table describes Managed and Unmanaged response groups.</span></span>

### <a name="managed-and-unmanaged-response-groups"></a><span data-ttu-id="af256-126">管理対象の応答グループと非管理対象の応答グループ</span><span class="sxs-lookup"><span data-stu-id="af256-126">Managed and Unmanaged Response Groups</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="af256-127">応答グループの種類</span><span class="sxs-lookup"><span data-stu-id="af256-127">Response group type</span></span></th>
<th><span data-ttu-id="af256-128">説明</span><span class="sxs-lookup"><span data-stu-id="af256-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af256-129">非管理対象</span><span class="sxs-lookup"><span data-stu-id="af256-129">Unmanaged</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="af256-130">非管理対象の応答グループには、マネージャーが割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="af256-130">Unmanaged response groups have no assigned Managers.</span></span> <span data-ttu-id="af256-131">応答グループ管理者のみが、これらの応答グループを構成できます。</span><span class="sxs-lookup"><span data-stu-id="af256-131">Only the Response Group Administrator can configure these response groups.</span></span></p></li>
<li><p><span data-ttu-id="af256-132">非管理対象の複数の応答グループが、1 つのキューまたはエージェント グループを共有できます。</span><span class="sxs-lookup"><span data-stu-id="af256-132">Multiple unmanaged response groups can share a queue or agent group.</span></span></p></li>
<li><p><span data-ttu-id="af256-133">応答グループを以前のバージョンから Lync Server 2013 に移行する場合、種類は [非管理] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="af256-133">When you migrate response groups from a prior version to Lync Server 2013, the type is set to Unmanaged.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af256-134">管理対象</span><span class="sxs-lookup"><span data-stu-id="af256-134">Managed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="af256-135">応答グループ管理者は、管理された応答グループの任意の側面を構成できます。</span><span class="sxs-lookup"><span data-stu-id="af256-135">Response Group Administrators can configure any aspect of managed response groups.</span></span></p></li>
<li><p><span data-ttu-id="af256-136">応答グループマネージャーは、明示的に割り当てられていない応答グループを表示したり、変更したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="af256-136">Response Group Managers cannot view or modify response groups that are not explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="af256-137">応答グループマネージャーは、明示的に割り当てられている応答グループの一部の設定のみを構成できます。</span><span class="sxs-lookup"><span data-stu-id="af256-137">Response Group Managers can configure only some settings for the response groups that are explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="af256-138">管理対象の応答グループは、他の応答グループ (管理対象または非管理対象を問わず) とはキューまたはエージェント グループを共有できません。</span><span class="sxs-lookup"><span data-stu-id="af256-138">Managed response groups can't share any queues or agent groups with any other response group, managed or unmanaged.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="af256-139">次の表では、グループ管理者に対して応答グループを割り当てることができるアクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="af256-139">The following table describes the actions that Response Group Managers can and cannot perform for the response groups assigned to them.</span></span>

### <a name="response-group-manager-capabilities"></a><span data-ttu-id="af256-140">応答グループ マネージャーの権限</span><span class="sxs-lookup"><span data-stu-id="af256-140">Response Group Manager Capabilities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="af256-141">構成可能</span><span class="sxs-lookup"><span data-stu-id="af256-141">Can configure:</span></span></th>
<th><span data-ttu-id="af256-142">作成、削除、または構成可能</span><span class="sxs-lookup"><span data-stu-id="af256-142">Can create, delete, or configure:</span></span></th>
<th><span data-ttu-id="af256-143">不可</span><span class="sxs-lookup"><span data-stu-id="af256-143">Cannot:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="af256-144">エージェント</span><span class="sxs-lookup"><span data-stu-id="af256-144">Agents</span></span></p></li>
<li><p><span data-ttu-id="af256-145">ウェルカム メッセージ</span><span class="sxs-lookup"><span data-stu-id="af256-145">Welcome message</span></span></p></li>
<li><p><span data-ttu-id="af256-146">応答グループ名</span><span class="sxs-lookup"><span data-stu-id="af256-146">Response Group name</span></span></p></li>
<li><p><span data-ttu-id="af256-147">説明</span><span class="sxs-lookup"><span data-stu-id="af256-147">Description</span></span></p></li>
<li><p><span data-ttu-id="af256-148">表示番号</span><span class="sxs-lookup"><span data-stu-id="af256-148">Display number</span></span></p></li>
<li><p><span data-ttu-id="af256-149">営業時間</span><span class="sxs-lookup"><span data-stu-id="af256-149">Business hours</span></span></p></li>
<li><p><span data-ttu-id="af256-150">保留音</span><span class="sxs-lookup"><span data-stu-id="af256-150">Music on hold</span></span></p></li>
<li><p><span data-ttu-id="af256-151">ステータス (アクティブ/非アクティブ)</span><span class="sxs-lookup"><span data-stu-id="af256-151">Status (active/inactive)</span></span></p></li>
<li><p><span data-ttu-id="af256-152">ハント グループまたは対話型音声応答 (IVR) のワークフロー</span><span class="sxs-lookup"><span data-stu-id="af256-152">Hunt group workflows or Interactive voice response (IVR) workflows</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="af256-153">エージェント グループ</span><span class="sxs-lookup"><span data-stu-id="af256-153">Agent Groups</span></span></p></li>
<li><p><span data-ttu-id="af256-154">キュー</span><span class="sxs-lookup"><span data-stu-id="af256-154">Queues</span></span></p></li>
<li><p><span data-ttu-id="af256-155">休日セット</span><span class="sxs-lookup"><span data-stu-id="af256-155">Holiday sets</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="af256-156">あらゆる種類のワークフローの作成または削除</span><span class="sxs-lookup"><span data-stu-id="af256-156">Create or delete any type of workflow</span></span></p></li>
<li><p><span data-ttu-id="af256-157">[<strong>SIP URI</strong>]、[<strong>電話番号</strong>]、[<strong>ワークフローの種類</strong>] など、応答グループの核となる設定の変更</span><span class="sxs-lookup"><span data-stu-id="af256-157">Modify core response group settings, such as: <strong>SIP URI</strong>, <strong>Telephone Number</strong>, or <strong>Workflow Type</strong>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="af256-158">応答グループマネージャーは、次のツールを使用して、指定した応答グループを管理できます。</span><span class="sxs-lookup"><span data-stu-id="af256-158">Response Group Managers can use the following tools to manage their designated response groups.</span></span>

  - <span data-ttu-id="af256-159">Lync Server コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="af256-159">Lync Server Control Panel</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="af256-160">応答グループマネージャーは、このツールを使用して応答グループの設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="af256-160">Response Group Managers can only manage Response Group settings with this tool.</span></span> <span data-ttu-id="af256-161">その他の Lync Server の設定は、管理者には使用できません。</span><span class="sxs-lookup"><span data-stu-id="af256-161">Other Lync Server settings are not available to Managers.</span></span>

    
    </div>

  - <span data-ttu-id="af256-162">応答グループ構成ツール</span><span class="sxs-lookup"><span data-stu-id="af256-162">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="af256-163">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="af256-163">Lync Server Management Shell</span></span>

<span data-ttu-id="af256-164">応答グループは、部署またはワークグループ環境に適しています (詳細については、「 [Lync Server 2013 の応答グループのキャパシティ計画](lync-server-2013-capacity-planning-for-response-group.md)」を参照してください)。また、まったく新しいテレフォニーインストールで展開できます。</span><span class="sxs-lookup"><span data-stu-id="af256-164">Response Group scales well to departmental or workgroup environments (for details, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) and can be deployed in entirely new telephony installations.</span></span> <span data-ttu-id="af256-165">エンタープライズボイス展開とローカルキャリアネットワークからの着信通話がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="af256-165">It supports incoming calls from the Enterprise Voice deployment and from the local carrier network.</span></span> <span data-ttu-id="af256-166">Lync 2013、Lync 2010、Lync 2010 アテンダント、Lync Phone Edition を使用して、通話を転送することができます。</span><span class="sxs-lookup"><span data-stu-id="af256-166">Agents can use Lync 2013, Lync 2010, Lync 2010 Attendant, or Lync Phone Edition to take the calls routed to them.</span></span>

<span data-ttu-id="af256-167">応答グループアプリケーションは、エンタープライズ Voip のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="af256-167">The Response Group application is a component of Enterprise Voice.</span></span> <span data-ttu-id="af256-168">エンタープライズ Voip を展開すると、応答グループアプリケーションがインストールされて自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="af256-168">When you deploy Enterprise Voice, the Response Group application is installed and activated automatically.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

