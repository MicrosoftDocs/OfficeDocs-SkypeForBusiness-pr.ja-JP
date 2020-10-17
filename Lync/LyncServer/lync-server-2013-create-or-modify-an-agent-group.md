---
title: 'Lync Server 2013: エージェントグループを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an agent group
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205370(v=OCS.15)
ms:contentKeyID: 48185784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 874b73af42869bc5cbe6a66b7efaf792d231b95d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525754"
---
# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="f477b-102">Lync Server 2013 でエージェントグループを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="f477b-102">Create or modify an agent group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f477b-103">_**トピックの最終更新日:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="f477b-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="f477b-104">エージェント グループを作成または変更するには、以下の手順のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="f477b-104">Use one of the following procedures to create or modify an agent group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f477b-105">CsVoiceAdministrator などの管理者は、ユーザーがエージェントグループに割り当てられる前に、エンタープライズ Voip および Lync Server に対してユーザーを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f477b-105">An Administrator—for example, CsVoiceAdministrator—must enable users for Enterprise Voice and Lync Server before the users can be assigned to agent groups.</span></span> <span data-ttu-id="f477b-106">管理ワークフローの委任された応答グループ マネージャーであれば、エージェント グループを作成し、管理するワークフローでそのグループを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f477b-106">If you are one of the delegated Response Group Managers for a managed workflow, you can create agent groups and use the agent groups in the workflows that you manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f477b-p102">ユーザーを応答グループ エージェントとして割り当てる場合、ユーザーがプライバシー モードを有効にしているのであれば、"RGS Presence Watcher" 連絡先を検索して連絡先リストに追加する必要があることを通知してください。プライバシー モードを有効にしているが連絡先リストに RGS Presence Watcher がないエージェントは、応答グループに対する通話を受信できません。プライバシー モードを有効にしていないエージェントは、影響されません。</span><span class="sxs-lookup"><span data-stu-id="f477b-p102">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="f477b-110">Lync Server コントロールパネルを使用してエージェントグループを作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="f477b-110">To use Lync Server Control Panel to create or modify an agent group</span></span>

1.  <span data-ttu-id="f477b-111">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="f477b-111">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f477b-112">管理ワークフローの委任された応答グループ マネージャーであれば、グループを作成し、自分が管理するワークフローにそれらを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f477b-112">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="f477b-113">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f477b-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f477b-114">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f477b-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f477b-115">左側のナビゲーション バーで、[**応答グループ**] をクリックし、[**グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f477b-115">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="f477b-116">[**グループ**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f477b-116">On the **Group** page, do one of the following:</span></span>
    
      - <span data-ttu-id="f477b-p104">新規エージェント グループを作成するには、[**新規**] をクリックします。[**サービスの選択**] 検索フィールドで、グループを追加する **ApplicationServer** サービスの名前のすべてまたは一部を入力します。サービスの結果一覧で、対象のサービスをクリックして [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f477b-p104">To create a new agent group, click **New**. In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group. In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="f477b-p105">既存のエージェント グループを変更するには、検索フィールドでエージェント グループの名前のすべてまたは一部を入力します。結果一覧で、対象のグループをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f477b-p105">To modify an existing agent group, type all or part of the name of the agent group in the search field. In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f477b-122">[**名前**] に、エージェント グループの識別名を入力します。</span><span class="sxs-lookup"><span data-stu-id="f477b-122">In **Name**, type an identifying name for the agent group.</span></span>

6.  <span data-ttu-id="f477b-123">[**説明**] に、グループの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="f477b-123">In **Description**, type a description for the group.</span></span>

7.  <span data-ttu-id="f477b-124">[**参加ポリシー**] で、以下のいずれかを選択してグループのサインイン動作を設定します。</span><span class="sxs-lookup"><span data-stu-id="f477b-124">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
      - <span data-ttu-id="f477b-125">グループに属するエージェントがそのグループにサインイン/サインアウトする必要がないようにするには、[**非公式**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f477b-125">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="f477b-126">エージェントは、Lync Server 2013 にサインインすると自動的にグループにサインインします。</span><span class="sxs-lookup"><span data-stu-id="f477b-126">Agents are automatically signed in to the group when they sign in to Lync Server 2013.</span></span>
    
      - <span data-ttu-id="f477b-127">グループに属するエージェントがそのグループにサインイン/サインアウトする必要があるようにするには、[**公式**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f477b-127">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="f477b-128">このオプションを選択すると、エージェントは Lync のメニュー項目をクリックして、Internet Explorer を開き、グループにサインインまたはサインアウトするための web ページコンソールを表示します。</span><span class="sxs-lookup"><span data-stu-id="f477b-128">When you select this option, agents click a menu item in Lync to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

8.  <span data-ttu-id="f477b-129">[**警告時間 (秒)**] で、次の有効なエージェントの呼び出しに移るまでにエージェントを呼び出す時間 (単位は秒、既定値は 20 秒) を指定します。</span><span class="sxs-lookup"><span data-stu-id="f477b-129">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f477b-p108">エージェント警告時間の設定に 180 秒を超える値は指定できません。エージェント警告時間が 180 秒を超える場合、SIP トランザクション タイマーが最長待機時間に達することによって、クライアント アプリケーションが通話を拒否します。</span><span class="sxs-lookup"><span data-stu-id="f477b-p108">The agent alert time setting cannot exceed 180 seconds. If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

9.  <span data-ttu-id="f477b-132">[**ルーティング方法**] で、グループのエージェントに通話をルーティングする方法を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="f477b-132">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
      - <span data-ttu-id="f477b-133">新しい通話を最初にアイドル状態になった (Lync Server で **利用可能** な状態または **非アクティブ** な状態になっていた) エージェントに最初に提供するには、[ **最長アイドル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f477b-133">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Lync Server the longest), click **Longest idle**.</span></span>
    
      - <span data-ttu-id="f477b-p109">新しい通話を、有効なすべてのエージェントに同時に提供するには、[**パラレル**] をクリックします。 通話は、最初に受け付けたエージェントに送られます。</span><span class="sxs-lookup"><span data-stu-id="f477b-p109">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
      - <span data-ttu-id="f477b-136">新しい通話を各エージェントに順番に提供するには、[**ラウンド ロビン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f477b-136">To offer a new call to each agent in turn, click **Round robin**.</span></span>
    
      - <span data-ttu-id="f477b-137">新しい通話を、常に [**エージェント**] リストでのリスト順でエージェントに提供するには、[**シリアル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f477b-137">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span>
    
      - <span data-ttu-id="f477b-138">現在のプレゼンスに関係なく、Lync Server 2013 および応答グループアプリケーションにサインインしているすべてのエージェントに対して同時に新しい通話を提供するには、[ **アテンダント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f477b-138">To offer a new call to all agents who are signed into Lync Server 2013 and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="f477b-139">Lync 2010 アテンダントユーザーがエージェントとして構成されている場合は、待機中のすべての通話、および任意の順序で待機通話に応答することができます。</span><span class="sxs-lookup"><span data-stu-id="f477b-139">Lync 2010 Attendant users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="f477b-140">呼び出しは、それを受け入れる最初のエージェントに送信され、その後、他の Lync 2010 アテンダントユーザーが通話を表示しなくなります。</span><span class="sxs-lookup"><span data-stu-id="f477b-140">The call is sent to the first agent who accepts it, after which the other Lync 2010 Attendant users no longer see the call.</span></span>

10. <span data-ttu-id="f477b-141">[**エージェント**] で、エージェント リストの作成方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="f477b-141">In **Agents**, specify how you want to create your agents list:</span></span>
    
      - <span data-ttu-id="f477b-142">エージェントのカスタム リストを使用するには、[**エージェントのカスタム グループを定義する**] をクリックして、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f477b-142">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
        
          - <span data-ttu-id="f477b-p111">ユーザーをエージェント グループに追加するには、[**選択**] をクリックして [**エージェントの選択**] 検索フィールドで、このグループに追加するユーザーの名前または名前の一部を入力して [**検索**] をクリックします。エージェントの結果リストで、ユーザーをクリックして [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f477b-p111">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**. In the resulting list of agents, click the user, and then click **OK**.</span></span>
        
          - <span data-ttu-id="f477b-145">エージェント グループからユーザーを削除するには、エージェントのリストで削除するユーザーをクリックし [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f477b-145">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
        
          - <span data-ttu-id="f477b-146">ラウンド ロビン ルーティングまたはシリアル ルーティングのいずれかを使用するグループでエージェントが通話を提供される順序を変更するには、エージェントのリストで、ユーザーをクリックして上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f477b-146">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span>
    
      - <span data-ttu-id="f477b-147">Microsoft Exchange Server 配布リストをエージェント グループとして使用するには、[**既存の電子メール配布リストを使用する**] をクリックし、[**配布リストのアドレス**] に配布リストの電子メール アドレス (NetworkSupport@contoso.com など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="f477b-147">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
        
        <span data-ttu-id="f477b-148">電子メール配布リストを使用する場合には、次の制約があります。</span><span class="sxs-lookup"><span data-stu-id="f477b-148">If you use an email distribution list, you are subject to the following constraints:</span></span>
        
          - <span data-ttu-id="f477b-p112">エージェント グループに対して複数の配布リストを選択することはできません。 各グループでサポートされる配布リストは 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="f477b-p112">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
        
          - <span data-ttu-id="f477b-151">配布リストの中に別の配布リストが含まれている場合、入れ子となった配布リストのメンバーはエージェント リストに追加されません。</span><span class="sxs-lookup"><span data-stu-id="f477b-151">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
        
          - <span data-ttu-id="f477b-152">シリアルまたはラウンド ロビン ルーティングを選択した場合、着信通話はサーバーによってルーティング方法および配布リスト内のエージェントの順序に基づいて適切なエージェントに提供されます。</span><span class="sxs-lookup"><span data-stu-id="f477b-152">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
        
          - <span data-ttu-id="f477b-153">配布リストに Lync Server 2010 が有効になっているが、エンタープライズ Voip が有効になっていないユーザーが含まれている場合、それらのユーザーは中エージェントとしてエージェントグループに追加されます。</span><span class="sxs-lookup"><span data-stu-id="f477b-153">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents.</span></span> <span data-ttu-id="f477b-154">配布リストのすべてのメンバーのユーザーアカウントに対してエンタープライズ Voip が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f477b-154">Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="f477b-155">電子メール配布リストを使用する場合、非表示のメンバーシップまたは非表示のリストが応答グループの管理者またはユーザーに表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f477b-155">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span>

        
        </div>
        
        <span data-ttu-id="f477b-156">非表示のメンバーシップまたは非表示のリストが表示されるようになるのは、次のような場合です。</span><span class="sxs-lookup"><span data-stu-id="f477b-156">Hidden memberships or hidden lists can become visible as follows:</span></span>
        
          - <span data-ttu-id="f477b-157">メンバーシップが非表示になるように配布リストが構成されており、応答グループの管理者が配布リストをエージェントリストに割り当てると、ユーザーはグループを呼び出して、メンバーが誰であるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f477b-157">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span>
        
          - <span data-ttu-id="f477b-158">配布リストが Exchange グローバルアドレス一覧で非表示になるように構成されている場合、応答グループの管理者が適切なユーザー権限とアクセス許可を持っていない場合でも、応答グループプロセスに適切なユーザー権限とアクセス許可がある場合は、配布リストを表示してエージェントリストに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f477b-158">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>

11. <span data-ttu-id="f477b-159">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f477b-159">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="f477b-160">Windows PowerShell を使用してエージェントグループを作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="f477b-160">To use Windows PowerShell to create or modify an agent group</span></span>

1.  <span data-ttu-id="f477b-161">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="f477b-161">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="f477b-162">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f477b-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f477b-163">新規エージェント グループを作成するには、**New-CsRgsAgentGroup** を使用します。</span><span class="sxs-lookup"><span data-stu-id="f477b-163">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="f477b-164">既存のエージェント グループを変更するには、**Set-CsRgsAgentGroup** を使用します。</span><span class="sxs-lookup"><span data-stu-id="f477b-164">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="f477b-165">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f477b-165">At the command line, run:</span></span>
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    <span data-ttu-id="f477b-166">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f477b-166">For example:</span></span>
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f477b-p115">エージェント警告時間の設定に 180 秒を超える値は指定できません。エージェント警告時間が 180 秒を超える場合、SIP トランザクション タイマーが最長待機時間に達することによって、クライアント アプリケーションが通話を拒否します。</span><span class="sxs-lookup"><span data-stu-id="f477b-p115">The agent alert time setting cannot exceed 180 seconds. If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

4.  <span data-ttu-id="f477b-p116">次のコマンドを実行して、エージェント グループが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f477b-p116">Confirm that the agent group is created. Run:</span></span>
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f477b-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="f477b-171">See Also</span></span>


[<span data-ttu-id="f477b-172">Lync Server 2013 でエージェントグループを削除する</span><span class="sxs-lookup"><span data-stu-id="f477b-172">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)  


[<span data-ttu-id="f477b-173">Lync Server 2013 での応答グループエージェントグループの管理</span><span class="sxs-lookup"><span data-stu-id="f477b-173">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)  
[<span data-ttu-id="f477b-174">取得-CsService</span><span class="sxs-lookup"><span data-stu-id="f477b-174">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="f477b-175">New-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="f477b-175">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[<span data-ttu-id="f477b-176">Set-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="f477b-176">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[<span data-ttu-id="f477b-177">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="f477b-177">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

