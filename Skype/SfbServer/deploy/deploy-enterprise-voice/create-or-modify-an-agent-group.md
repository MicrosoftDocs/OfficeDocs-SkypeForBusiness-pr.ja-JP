---
title: 作成するか、ビジネスの Skype でエージェント グループを変更
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
description: 作成またはビジネス サーバーのエンタープライズ VoIP の Skype での応答グループのエージェント グループを変更します。
ms.openlocfilehash: 16dafbfc3157e08a187be5799c5901115d738b48
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894537"
---
# <a name="create-or-modify-an-agent-group-in-skype-for-business"></a><span data-ttu-id="9c168-103">作成するか、ビジネスの Skype でエージェント グループを変更</span><span class="sxs-lookup"><span data-stu-id="9c168-103">Create or modify an agent group in Skype for Business</span></span>
 
<span data-ttu-id="9c168-104">作成またはビジネス サーバーのエンタープライズ VoIP の Skype での応答グループのエージェント グループを変更します。</span><span class="sxs-lookup"><span data-stu-id="9c168-104">Create or modify an agent group in Response Group, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="9c168-105">エージェント グループを作成するときは、そのグループに割り当てるエージェントを選択し、詳細なグループ設定 (ルーティング方法、グループに対するエージェントの権限など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c168-105">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span> 
  
<span data-ttu-id="9c168-106">担当者は、ビジネスの Skype の内外での署名とは異なるグループとの間で署名する必要がありますが、正式なエージェントと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9c168-106">An agent who must sign in and out of the group, which is different from signing in or out of Skype for Business, is called a formal agent.</span></span> <span data-ttu-id="9c168-107">公式エージェントが、グループにルーティングされた着信を受信するには、そのグループにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c168-107">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="9c168-108">これは、パートタイム ベースでグループから通話に応答するエージェントには便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="9c168-108">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="9c168-109">正式なエージェントは、Windows Internet Explorer のインターネット ブラウザーを開き、web ページ コンソールを表示するビジネス用の Skype のメニュー項目をクリックすると、それらのグループとの間で署名します。</span><span class="sxs-lookup"><span data-stu-id="9c168-109">Formal agents sign in and out of their groups by clicking a menu item in Skype for Business to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>
  
<span data-ttu-id="9c168-110">担当者は、グループの内外に署名しないが、非公式エージェントと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="9c168-110">An agent who does not sign in or out of the group is called an informal agent.</span></span> <span data-ttu-id="9c168-111">非公式エージェント自動的にサインインしているグループ、ビジネスの Skype にサインインして、グループから署名するときに。</span><span class="sxs-lookup"><span data-stu-id="9c168-111">Informal agents are automatically signed in to the group when they sign in to Skype for Business, and they cannot sign out of the group.</span></span>
  
<span data-ttu-id="9c168-112">エージェントにできるのは社内ユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="9c168-112">Only on-premises users can be agents.</span></span> <span data-ttu-id="9c168-113">エージェントをオンラインに設置から移動すると、応答グループの呼び出しはそのエージェントにルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="9c168-113">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>
  
<span data-ttu-id="9c168-114">エージェント グループを作成または変更するには、以下の手順のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="9c168-114">Use one of the following procedures to create or modify an agent group.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9c168-p104">ユーザーを応答グループ エージェントとして割り当てる場合、ユーザーがプライバシー モードを有効にしているのであれば、"RGS Presence Watcher" 連絡先を検索して連絡先リストに追加する必要があることを伝えてください。プライバシー モードを有効にしているが連絡先リストに RGS Presence Watcher がないエージェントは、応答グループに対する通話を受信できません。プライバシー モードを有効にしていないエージェントは、影響されません。</span><span class="sxs-lookup"><span data-stu-id="9c168-p104">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="9c168-118">ビジネス サーバーのコントロール パネルの Skype を使用して作成または、エージェント グループを変更するには</span><span class="sxs-lookup"><span data-stu-id="9c168-118">To use Skype for Business Server Control Panel to create or modify an agent group</span></span>

1. <span data-ttu-id="9c168-119">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="9c168-119">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9c168-120">管理ワークフローの委任された応答グループ マネージャーであれば、グループを作成し、自分が管理するワークフローにそれらを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="9c168-120">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="9c168-121">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="9c168-121">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="9c168-122">左側のナビゲーション バーで、[**応答グループ**] をクリックし、[**グループ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c168-122">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>
    
4. <span data-ttu-id="9c168-123">[**グループ**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9c168-123">On the **Group** page, do one of the following:</span></span>
    
   - <span data-ttu-id="9c168-p105">新規エージェント グループを作成するには、[**新規**] をクリックします。[**サービスの選択**] 検索フィールドで、グループを追加する **ApplicationServer** サービスの名前の全体または一部を入力します。サービスの結果一覧で、対象のサービスをクリックして [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c168-p105">To create a new agent group, click **New**. In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group. In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="9c168-p106">既存のエージェント グループを変更するには、検索フィールドでエージェント グループの名前の全体または一部を入力します。結果一覧で、対象のグループをクリックして、[**編集**] をクリックし、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c168-p106">To modify an existing agent group, type all or part of the name of the agent group in the search field. In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="9c168-129">[**名前**] に、エージェント グループの識別名を入力します。</span><span class="sxs-lookup"><span data-stu-id="9c168-129">In **Name**, type an identifying name for the agent group.</span></span>
    
6. <span data-ttu-id="9c168-130">[**説明**] に、グループの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="9c168-130">In **Description**, type a description for the group.</span></span>
    
7. <span data-ttu-id="9c168-131">[**参加ポリシー**] で、以下のいずれかを選択してグループのサインイン動作を設定します。</span><span class="sxs-lookup"><span data-stu-id="9c168-131">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
   - <span data-ttu-id="9c168-132">グループに属するエージェントがそのグループにサインイン/サインアウトする必要がないようにするには、[**非公式**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c168-132">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="9c168-133">エージェントに自動的にサインインしているグループ ビジネスの Skype にサインインするとき。</span><span class="sxs-lookup"><span data-stu-id="9c168-133">Agents are automatically signed in to the group when they sign in to Skype for Business.</span></span>
    
   - <span data-ttu-id="9c168-134">グループに属するエージェントがそのグループにサインイン/サインアウトする必要があるようにするには、[**公式**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9c168-134">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="9c168-135">このオプションを選択すると、エージェントは、Internet Explorer を開き、グループとの間で署名するための web ページ コンソールを表示するビジネス用の Skype のメニュー項目をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c168-135">When you select this option, agents click a menu item in Skype for Business to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>
    
8. <span data-ttu-id="9c168-136">[**警告時間 (秒)**] で、次の連絡可能なエージェントの呼び出しに移るまでにエージェントを呼び出す時間 (単位は秒、既定値は 20 秒) を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c168-136">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9c168-p109">エージェント警告時間の設定に 180 秒を超える値は指定できません。エージェント警告時間が 180 秒を超える場合、SIP トランザクション タイマーが最長待機時間に達することによって、クライアント アプリケーションが通話を拒否します。</span><span class="sxs-lookup"><span data-stu-id="9c168-p109">The agent alert time setting cannot exceed 180 seconds. If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
9. <span data-ttu-id="9c168-139">[**ルーティング方法**] で、グループのエージェントに通話をルーティングする方法を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="9c168-139">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
   - <span data-ttu-id="9c168-140">最長アイドル状態にしたエージェントを最初に新しい呼び出しを提供する (が支持されていました**利用可能**] または [**非アクティブ**の Skype ビジネスの最も長いの)、[**最長アイドル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c168-140">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Skype for Business the longest), click **Longest idle**.</span></span> 
    
   - <span data-ttu-id="9c168-p110">新しい通話を、連絡可能なすべてのエージェントに同時に提供するには、[**パラレル**] をクリックします。通話は、最初に承諾したエージェントに送られます。</span><span class="sxs-lookup"><span data-stu-id="9c168-p110">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
   - <span data-ttu-id="9c168-143">新しい通話を各エージェントに順番に提供するには、[**ラウンド ロビン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c168-143">To offer a new call to each agent in turn, click **Round robin**.</span></span> 
    
   - <span data-ttu-id="9c168-144">新しい通話を、常に [**エージェント**] リストでのリスト順でエージェントに提供するには、[**シリアル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c168-144">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span> 
    
   - <span data-ttu-id="9c168-145">ビジネスと現在の自分の存在に関係なく、同時に応答グループ アプリケーションの Skype にサインインしているユーザーのすべてのエージェントに新しい通話を提供するには、**アテンダント**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c168-145">To offer a new call to all agents who are signed into Skype for Business and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="9c168-146">エージェントとして構成されているユーザーには、待機中のすべての通話が表示され、待機通話に任意の順序で応対できます。</span><span class="sxs-lookup"><span data-stu-id="9c168-146">Users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="9c168-147">通話は、最初に承諾したエージェントに送信され、その後は他のエージェントには表示されません。</span><span class="sxs-lookup"><span data-stu-id="9c168-147">The call is sent to the first agent who accepts it, after which the other agents no longer see the call.</span></span>
    
10. <span data-ttu-id="9c168-148">[**エージェント**] で、エージェント リストの作成方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c168-148">In **Agents**, specify how you want to create your agents list:</span></span>
    
    - <span data-ttu-id="9c168-149">エージェントのカスタム リストを使用するには、[**エージェントのカスタム グループを定義する**] をクリックして、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9c168-149">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
    
    - <span data-ttu-id="9c168-p112">ユーザーをエージェント グループに追加するには、[**選択**] をクリックして [**エージェントの選択**] 検索フィールドで、このグループに追加するユーザーの名前の全体または一部を入力して [**検索**] をクリックします。エージェントの結果リストで、ユーザーをクリックして [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c168-p112">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**. In the resulting list of agents, click the user, and then click **OK**.</span></span>
    
    - <span data-ttu-id="9c168-152">エージェント グループからユーザーを削除するには、エージェントのリストで削除するユーザーをクリックし [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c168-152">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
    
    - <span data-ttu-id="9c168-153">ラウンド ロビン ルーティングまたはシリアル ルーティングのいずれかを使用するグループでエージェントが通話を提供される順序を変更するには、エージェントのリストで、ユーザーをクリックして上矢印または下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c168-153">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span> 
    
    - <span data-ttu-id="9c168-154">Microsoft Exchange Server 配布リストをエージェント グループとして使用するには、[**既存の電子メール配布リストを使用する**] をクリックし、[**配布リストのアドレス**] に配布リストの電子メール アドレス (NetworkSupport@contoso.com など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="9c168-154">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
    
      <span data-ttu-id="9c168-155">電子メール配布リストを使用する場合には、次の制約があります。</span><span class="sxs-lookup"><span data-stu-id="9c168-155">If you use an email distribution list, you are subject to the following constraints:</span></span>
    
      - <span data-ttu-id="9c168-p113">エージェント グループに対して複数の配布リストを選択することはできません。各グループでサポートされる配布リストは 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="9c168-p113">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
    
      - <span data-ttu-id="9c168-158">配布リストの中に別の配布リストが含まれている場合、入れ子となった配布リストのメンバーはエージェント リストに追加されません。</span><span class="sxs-lookup"><span data-stu-id="9c168-158">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
    
      - <span data-ttu-id="9c168-159">シリアルまたはラウンド ロビン ルーティングを選択した場合、着信通話はサーバーによってルーティング方法および配布リスト内のエージェントの順序に基づいて適切なエージェントに提供されます。</span><span class="sxs-lookup"><span data-stu-id="9c168-159">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
    
      - <span data-ttu-id="9c168-p114">配布リストのユーザーの中に、Lync Server 2010 は有効だが Enterprise Voice が無効なユーザーが含まれていると、それらのユーザーは機能しないエージェントとしてエージェント リストに追加されます。配布リストのすべてのメンバーのアカウントで、Enterprise Voice が有効であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9c168-p114">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents. Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9c168-162">電子メールの配布リストを使用する場合は、メンバーシップが非表示または非表示のリストが応答グループの管理者またはユーザーに表示されてなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9c168-162">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span> 
  
    <span data-ttu-id="9c168-163">非表示のメンバーシップまたは非表示のリストが表示されるようになるのは、次のような場合です。</span><span class="sxs-lookup"><span data-stu-id="9c168-163">Hidden memberships or hidden lists can become visible as follows:</span></span>
    
     - <span data-ttu-id="9c168-164">配布リストでは、メンバーシップが非表示にし、応答グループの管理者がエージェントの一覧に配布リストを割り当てるように設定されていれば、ユーザーは、グループ メンバーは、ユーザーを確認するを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="9c168-164">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span> 
    
     - <span data-ttu-id="9c168-165">応答グループの管理者は配布リストし、応答グループのプロセスに適切なユーザー権利が設定されている場合は、[エージェント] ボックスの一覧に割り当てるを参照してくださいできる場合がありますが Exchange のグローバル アドレス一覧に表示されるように配布リストが構成されている場合、アクセス許可を管理者が適切なユーザー権利とアクセス許可があるない場合でも。</span><span class="sxs-lookup"><span data-stu-id="9c168-165">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>
    
11. <span data-ttu-id="9c168-166">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c168-166">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="9c168-167">ビジネス サーバー管理シェルの Skype を使用して作成するか、エージェント グループを変更するのには</span><span class="sxs-lookup"><span data-stu-id="9c168-167">To use Skype for Business Server Management Shell to create or modify an agent group</span></span>

1. <span data-ttu-id="9c168-168">RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="9c168-168">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="9c168-169">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c168-169">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="9c168-170">新規エージェント グループを作成するには、**New-CsRgsAgentGroup** を使用します。</span><span class="sxs-lookup"><span data-stu-id="9c168-170">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="9c168-171">既存のエージェント グループを変更するには、**Set-CsRgsAgentGroup** を使用します。</span><span class="sxs-lookup"><span data-stu-id="9c168-171">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="9c168-172">コマンド ラインで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9c168-172">At the command line, run:</span></span>
    
   ```
   New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
   ```

    <span data-ttu-id="9c168-173">例:</span><span class="sxs-lookup"><span data-stu-id="9c168-173">For example:</span></span>
    
   ```
   New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="9c168-p116">エージェント警告時間の設定に 180 秒を超える値は指定できません。エージェント警告時間が 180 秒を超える場合、SIP トランザクション タイマーが最長待機時間に達することによって、クライアント アプリケーションが通話を拒否します。</span><span class="sxs-lookup"><span data-stu-id="9c168-p116">The agent alert time setting cannot exceed 180 seconds. If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span> 
  
4. <span data-ttu-id="9c168-p117">次のコマンドを実行して、エージェント グループが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c168-p117">Confirm that the agent group is created. Run:</span></span>
    
   ```
   Get-CsRgsAgentGroup -Name "Help Desk"
   ```

## <a name="see-also"></a><span data-ttu-id="9c168-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c168-178">See also</span></span>

[<span data-ttu-id="9c168-179">Get CsService</span><span class="sxs-lookup"><span data-stu-id="9c168-179">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
  
[<span data-ttu-id="9c168-180">新しい-CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="9c168-180">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="9c168-181">セット CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="9c168-181">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsagentgroup?view=skype-ps)
  
[<span data-ttu-id="9c168-182">Get CsRgsAgentGroup</span><span class="sxs-lookup"><span data-stu-id="9c168-182">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsagentgroup?view=skype-ps)
