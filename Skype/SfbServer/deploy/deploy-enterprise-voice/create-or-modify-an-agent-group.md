---
title: Skype for Business でエージェントグループを作成または変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: Skype for Business Server Enterprise Voice で、[応答] グループのエージェントグループを作成または変更します。
ms.openlocfilehash: 0b496160f00cde80364c0f81c150392405ef7768
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767760"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a><span data-ttu-id="4e4f4-103">Skype for Business でエージェントグループを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="4e4f4-103">Create or modify an agent group in Skype for Business</span></span>
 
<span data-ttu-id="4e4f4-104">Skype for Business Server Enterprise Voice で、[応答] グループのエージェントグループを作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-104">Create or modify an agent group in Response Group, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="4e4f4-105">エージェント グループを作成するときは、そのグループに割り当てるエージェントを選択し、詳細なグループ設定 (ルーティング方法、グループに対するエージェントの権限など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-105">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span> 
  
<span data-ttu-id="4e4f4-106">グループからサインアウトする必要があるエージェントは、Skype for Business のサインインまたはサインアウトとは異なり、正式なエージェントと呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-106">An agent who must sign in and out of the group, which is different from signing in or out of Skype for Business, is called a formal agent.</span></span> <span data-ttu-id="4e4f4-107">公式エージェントが、グループにルーティングされた着信を受信するには、そのグループにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-107">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="4e4f4-108">これは、パートタイム ベースでグループから通話に応答するエージェントには便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-108">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="4e4f4-109">正式なエージェント Skype for Business のメニュー項目をクリックすると、Windows Internet Explorer のインターネットブラウザが開き、web ページ本体が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-109">Formal agents sign in and out of their groups by clicking a menu item in Skype for Business to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>
  
<span data-ttu-id="4e4f4-110">グループにサインインしていないか、グループからサインアウトしていないエージェントは、"非公式のエージェント" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-110">An agent who does not sign in or out of the group is called an informal agent.</span></span> <span data-ttu-id="4e4f4-111">非公式のエージェントは、Skype for Business にサインインするときにグループに自動的にサインインされ、グループからサインアウトすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-111">Informal agents are automatically signed in to the group when they sign in to Skype for Business, and they cannot sign out of the group.</span></span>
  
<span data-ttu-id="4e4f4-112">エージェントにできるのは社内ユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-112">Only on-premises users can be agents.</span></span> <span data-ttu-id="4e4f4-113">エージェントがオンプレミスからオンラインに移行された場合、応答グループの呼び出しはそのエージェントにルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-113">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>
  
<span data-ttu-id="4e4f4-114">エージェント グループを作成または変更するには、以下の手順のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-114">Use one of the following procedures to create or modify an agent group.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4e4f4-p104">ユーザーを応答グループ エージェントとして割り当てる場合、ユーザーがプライバシー モードを有効にしているのであれば、"RGS Presence Watcher" 連絡先を検索して連絡先リストに追加する必要があることを伝えてください。プライバシー モードを有効にしているが連絡先リストに RGS Presence Watcher がないエージェントは、応答グループに対する通話を受信できません。プライバシー モードを有効にしていないエージェントは、影響されません。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-p104">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="4e4f4-118">Skype for Business Server コントロールパネルを使用してエージェントグループを作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="4e4f4-118">To use Skype for Business Server Control Panel to create or modify an agent group</span></span>

1. <span data-ttu-id="4e4f4-119">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-119">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4e4f4-120">管理ワークフローの委任された応答グループ マネージャーであれば、グループを作成し、自分が管理するワークフローにそれらを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-120">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="4e4f4-121">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-121">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="4e4f4-122">左側のナビゲーション バーで、[**応答グループ**] をクリックし、[**グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-122">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>
    
4. <span data-ttu-id="4e4f4-123">[**グループ**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-123">On the **Group** page, do one of the following:</span></span>
    
   - <span data-ttu-id="4e4f4-p105">新規エージェント グループを作成するには、[**新規**] をクリックします。[**サービスの選択**] 検索フィールドで、グループを追加する **ApplicationServer** サービスの名前の全体または一部を入力します。サービスの結果一覧で、対象のサービスをクリックして [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-p105">To create a new agent group, click **New**. In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group. In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="4e4f4-p106">既存のエージェント グループを変更するには、検索フィールドでエージェント グループの名前の全体または一部を入力します。結果一覧で、対象のグループをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-p106">To modify an existing agent group, type all or part of the name of the agent group in the search field. In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="4e4f4-129">[**名前**] に、エージェント グループの識別名を入力します。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-129">In **Name**, type an identifying name for the agent group.</span></span>
    
6. <span data-ttu-id="4e4f4-130">[**説明**] に、グループの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-130">In **Description**, type a description for the group.</span></span>
    
7. <span data-ttu-id="4e4f4-131">[**参加ポリシー**] で、以下のいずれかを選択してグループのサインイン動作を設定します。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-131">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
   - <span data-ttu-id="4e4f4-132">グループに属するエージェントがそのグループにサインイン/サインアウトする必要がないようにするには、[**非公式**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-132">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="4e4f4-133">Skype for Business にサインインすると、そのグループに自動的にサインインされます。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-133">Agents are automatically signed in to the group when they sign in to Skype for Business.</span></span>
    
   - <span data-ttu-id="4e4f4-134">グループに属するエージェントがそのグループにサインイン/サインアウトする必要があるようにするには、[**公式**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-134">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="4e4f4-135">このオプションを選択すると、[Skype for Business] のメニュー項目をクリックすると、Internet Explorer が開き、グループにサインインまたはサインアウトするための web ページ本体が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-135">When you select this option, agents click a menu item in Skype for Business to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>
    
8. <span data-ttu-id="4e4f4-136">[**警告時間 (秒)**] で、次の連絡可能なエージェントの呼び出しに移るまでにエージェントを呼び出す時間 (単位は秒、既定値は 20 秒) を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-136">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="4e4f4-p109">エージェント警告時間の設定に 180 秒を超える値は指定できません。エージェント警告時間が 180 秒を超える場合、SIP トランザクション タイマーが最長待機時間に達することによって、クライアント アプリケーションが通話を拒否します。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-p109">The agent alert time setting cannot exceed 180 seconds. If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
9. <span data-ttu-id="4e4f4-139">[**ルーティング方法**] で、グループのエージェントに通話をルーティングする方法を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-139">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
   - <span data-ttu-id="4e4f4-140">新しい通話を最初にアイドル状態になったエージェントに対して行うには、最も長い時間が経過した (Skype for Business で**使用可能**または**非アクティブ**状態になっていた)、[**最長アイドル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-140">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Skype for Business the longest), click **Longest idle**.</span></span> 
    
   - <span data-ttu-id="4e4f4-p110">新しい通話を、連絡可能なすべてのエージェントに同時に提供するには、[**パラレル**] をクリックします。通話は、最初に承諾したエージェントに送られます。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-p110">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
   - <span data-ttu-id="4e4f4-143">新しい通話を各エージェントに順番に提供するには、[**ラウンド ロビン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-143">To offer a new call to each agent in turn, click **Round robin**.</span></span> 
    
   - <span data-ttu-id="4e4f4-144">新しい通話を、常に [**エージェント**] リストでのリスト順でエージェントに提供するには、[**シリアル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-144">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span> 
    
   - <span data-ttu-id="4e4f4-145">現在のプレゼンスに関係なく、Skype for Business と応答グループアプリケーションにサインインしているすべてのエージェントへの新しい通話を提供するには、[**応答**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-145">To offer a new call to all agents who are signed into Skype for Business and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="4e4f4-146">エージェントとして構成されているユーザーには、待機中のすべての通話が表示され、待機通話に任意の順序で応対できます。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-146">Users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="4e4f4-147">通話は、最初に承諾したエージェントに送信され、その後は他のエージェントには表示されません。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-147">The call is sent to the first agent who accepts it, after which the other agents no longer see the call.</span></span>
    
10. <span data-ttu-id="4e4f4-148">[**エージェント**] で、エージェント リストの作成方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-148">In **Agents**, specify how you want to create your agents list:</span></span>
    
    - <span data-ttu-id="4e4f4-149">エージェントのカスタム リストを使用するには、[**エージェントのカスタム グループを定義する**] をクリックして、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-149">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
    
    - <span data-ttu-id="4e4f4-p112">ユーザーをエージェント グループに追加するには、[**選択**] をクリックして [**エージェントの選択**] 検索フィールドで、このグループに追加するユーザーの名前の全体または一部を入力して [**検索**] をクリックします。エージェントの結果リストで、ユーザーをクリックして [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-p112">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**. In the resulting list of agents, click the user, and then click **OK**.</span></span>
    
    - <span data-ttu-id="4e4f4-152">エージェント グループからユーザーを削除するには、エージェントのリストで削除するユーザーをクリックし [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-152">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
    
    - <span data-ttu-id="4e4f4-153">ラウンド ロビン ルーティングまたはシリアル ルーティングのいずれかを使用するグループでエージェントが通話を提供される順序を変更するには、エージェントのリストで、ユーザーをクリックして上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-153">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span> 
    
    - <span data-ttu-id="4e4f4-154">Microsoft Exchange Server 配布リストをエージェント グループとして使用するには、[**既存の電子メール配布リストを使用する**] をクリックし、[**配布リストのアドレス**] に配布リストの電子メール アドレス (NetworkSupport@contoso.com など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-154">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
    
      <span data-ttu-id="4e4f4-155">電子メール配布リストを使用する場合には、次の制約があります。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-155">If you use an email distribution list, you are subject to the following constraints:</span></span>
    
      - <span data-ttu-id="4e4f4-p113">エージェント グループに対して複数の配布リストを選択することはできません。各グループでサポートされる配布リストは 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-p113">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
    
      - <span data-ttu-id="4e4f4-158">配布リストの中に別の配布リストが含まれている場合、入れ子となった配布リストのメンバーはエージェント リストに追加されません。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-158">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
    
      - <span data-ttu-id="4e4f4-159">シリアルまたはラウンド ロビン ルーティングを選択した場合、着信通話はサーバーによってルーティング方法および配布リスト内のエージェントの順序に基づいて適切なエージェントに提供されます。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-159">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
    
      - <span data-ttu-id="4e4f4-p114">配布リストのユーザーの中に、Lync Server 2010 は有効だが Enterprise Voice が無効なユーザーが含まれていると、それらのユーザーは機能しないエージェントとしてエージェント リストに追加されます。配布リストのすべてのメンバーのアカウントで、Enterprise Voice が有効であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-p114">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents. Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="4e4f4-162">メール配布リストを使用している場合、非表示のメンバーシップや非表示のリストが、応答グループの管理者またはユーザーに表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-162">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span> 
  
    <span data-ttu-id="4e4f4-163">非表示のメンバーシップまたは非表示のリストが表示されるようになるのは、次のような場合です。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-163">Hidden memberships or hidden lists can become visible as follows:</span></span>
    
     - <span data-ttu-id="4e4f4-164">配布リストが構成されていて、メンバーシップが非表示になっていて、応答グループの管理者がその配布リストをエージェントの一覧に割り当てると、ユーザーはそのグループを呼び出してメンバーの誰を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-164">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span> 
    
     - <span data-ttu-id="4e4f4-165">配布リストが Exchange のグローバルアドレス一覧で非表示になるように構成されている場合、応答グループの管理者が適切なユーザー権限を持っている場合は、その配布リストを表示してエージェントの一覧に割り当てることができる場合があります。管理者が適切なユーザー権限と権限を持っていない場合でも、権限。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-165">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>
    
11. <span data-ttu-id="4e4f4-166">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-166">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="4e4f4-167">Skype for Business Server 管理シェルを使用してエージェントグループを作成または変更するには</span><span class="sxs-lookup"><span data-stu-id="4e4f4-167">To use Skype for Business Server Management Shell to create or modify an agent group</span></span>

1. <span data-ttu-id="4e4f4-168">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-168">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="4e4f4-169">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-169">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4e4f4-170">新規エージェント グループを作成するには、**New-CsRgsAgentGroup** を使用します。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-170">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="4e4f4-171">既存のエージェント グループを変更するには、**Set-CsRgsAgentGroup** を使用します。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-171">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="4e4f4-172">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-172">At the command line, run:</span></span>
    
   ```powershell
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    <span data-ttu-id="4e4f4-173">例:</span><span class="sxs-lookup"><span data-stu-id="4e4f4-173">For example:</span></span>
    
   ```powershell
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="4e4f4-p116">エージェント警告時間の設定に 180 秒を超える値は指定できません。エージェント警告時間が 180 秒を超える場合、SIP トランザクション タイマーが最長待機時間に達することによって、クライアント アプリケーションが通話を拒否します。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-p116">The agent alert time setting cannot exceed 180 seconds. If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
4. <span data-ttu-id="4e4f4-p117">次のコマンドを実行して、エージェント グループが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4e4f4-p117">Confirm that the agent group is created. Run:</span></span>
    
   ```powershell
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a><span data-ttu-id="4e4f4-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e4f4-178">See also</span></span>

[<span data-ttu-id="4e4f4-179">CsService の入手</span><span class="sxs-lookup"><span data-stu-id="4e4f4-179">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[<span data-ttu-id="4e4f4-180">New-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="4e4f4-180">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="4e4f4-181">Set-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="4e4f4-181">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="4e4f4-182">Get-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="4e4f4-182">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)
