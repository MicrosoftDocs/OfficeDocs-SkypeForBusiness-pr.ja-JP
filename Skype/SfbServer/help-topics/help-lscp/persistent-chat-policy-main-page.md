---
title: 常設チャット ポリシー メイン ページ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0dc18d5c-82d6-4d39-afb1-efdb3ae6d2c7
description: 常設チャット グループの [常設チャット ポリシー] ページを使用して、グローバル、プール、サイト、またはユーザー レベルでポリシーを管理できます。たとえば、既定のグローバル ポリシーの構成や、展開用の 1 つ以上の追加のユーザー ポリシーとサイト ポリシーの作成を含めます。 ユーザーがポリシーによって常設チャット サーバーに対して有効になっている場合、常設チャット サーバー環境がクライアントに表示されます。
ms.openlocfilehash: 9664cbf182fe388fbffd2b270e306a4c17b36e95
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819307"
---
# <a name="persistent-chat-policy-main-page"></a><span data-ttu-id="56bab-104">常設チャット ポリシー メイン ページ</span><span class="sxs-lookup"><span data-stu-id="56bab-104">Persistent Chat Policy Main Page</span></span>
 
<span data-ttu-id="56bab-105">**常設** チャット グループの [常設チャット ポリシー] ページを使用して、グローバル、プール、サイト、またはユーザー レベルでポリシーを管理できます。たとえば、既定のグローバル ポリシーの構成や、展開用の 1 つ以上の追加のユーザー ポリシーとサイト ポリシーの作成を含めます。</span><span class="sxs-lookup"><span data-stu-id="56bab-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="56bab-106">ユーザーがポリシーによって常設チャット サーバーに対して有効になっている場合、常設チャット サーバー環境がクライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="56bab-106">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
> [!NOTE]
> <span data-ttu-id="56bab-107">トポロジでは、常設チャット サーバー サイト ポリシーは、グローバル、ユーザーのプール別、またはユーザーのサイト単位、またはユーザー単位で適用されます。</span><span class="sxs-lookup"><span data-stu-id="56bab-107">In the topology, Persistent Chat Server site policies apply globally, per user's pool, or per user's site, or per user.</span></span> 
  
<span data-ttu-id="56bab-108">グローバル ポリシーは、常設チャット サーバーを展開するときに自動的に作成され、構成できますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="56bab-108">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="56bab-109">グローバル ポリシーはすべてのユーザーに適用されるので、ユーザーごとに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56bab-109">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="56bab-110">複数のサイト ポリシーとユーザー ポリシーを作成して構成し、グローバル ポリシーと共に、常設チャット サーバーのユーザーを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="56bab-110">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="56bab-111">プールおよびサイトの常設チャット サーバー ポリシーは、グローバル常設チャット サーバー ポリシーより優先されますが、そのサイトのユーザーに対してのみです。</span><span class="sxs-lookup"><span data-stu-id="56bab-111">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="56bab-112">ユーザー ポリシーは、ユーザー ポリシーが割り当てられているユーザーのグローバル ポリシー、プール ポリシー、およびサイト ポリシーの両方を上書きします。</span><span class="sxs-lookup"><span data-stu-id="56bab-112">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="56bab-113">常設チャット サーバーを構成して使用するには、まずトポロジ ビルダーを使用して常設チャット サーバーのサポートをトポロジに追加してから、トポロジを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56bab-113">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="56bab-114">詳細については [、「Skype for Business Server 2015 トポロジ](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)への常設チャット サーバーの追加」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56bab-114">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="56bab-115">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="56bab-115">Tasks that you can perform</span></span>

<span data-ttu-id="56bab-116">[常設チャット ポリシー] ページでは、常設 **チャット** サーバー ポリシーを有効にして管理するタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="56bab-116">You can perform the following tasks on the **Persistent Chat Policy** page: enable and manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="56bab-117">常設チャットのグローバル ポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="56bab-117">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="56bab-118">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="56bab-118">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="56bab-119">[スタート **] メニュー** から Skype for Business Server コントロール パネルを選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="56bab-119">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="56bab-120">Skype for Business Server コントロール パネルで、[ **常設チャット]** をクリックし、[常設チャット ポリシー] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="56bab-120">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="56bab-121">ポリシーの一覧の [**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56bab-121">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="56bab-122">[**編集 常設チャットのポリシー - Global**] で、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="56bab-122">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="56bab-123">グローバルという既定の名前を使用しない場合は、[**名前**] でグローバル ポリシーの新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="56bab-123">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="56bab-124">[ **説明]** に、ユーザー ポリシーの内容に関する詳細 (たとえば  _、centralSiteName_ のグローバル ポリシー) を入力します。</span><span class="sxs-lookup"><span data-stu-id="56bab-124">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="56bab-125">サイト ポリシーまたはユーザー ポリシーによって特に制御されていないすべてのサイトおよびユーザーに対して常設チャットを制御するには、[常設チャットを有効にする] チェック ボックス **をオンまたは** オフにします。</span><span class="sxs-lookup"><span data-stu-id="56bab-125">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="56bab-126">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56bab-126">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="56bab-127">サイトの常設チャット ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="56bab-127">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="56bab-128">展開したサイトごとに、サイト固有の常設チャット ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="56bab-128">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="56bab-129">サイト ポリシーの構成はグローバル ポリシーの構成よりも優先されますが、対象になるのはサイト ポリシーで指定された特定のサイトだけです。</span><span class="sxs-lookup"><span data-stu-id="56bab-129">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="56bab-130">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="56bab-130">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="56bab-131">[スタート **] メニューから** Skype for Business Server コントロール パネルを選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="56bab-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="56bab-132">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットのポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56bab-132">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="56bab-133">[**新規作成**] をクリックし、[**サイト ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56bab-133">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="56bab-134">[**サイトの選択**] でポリシーを適用するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="56bab-134">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="56bab-135">[**新規 常設チャットのポリシー**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="56bab-135">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="56bab-136">[**名前**] で、新しいサイト ポリシーの名前 (Redmond など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="56bab-136">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="56bab-137">[**説明**] にサイト ポリシーの内容の詳細 (「Redmond のチャット ルーム ポリシー」など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="56bab-137">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="56bab-138">サイト ポリシーによって特に制御されていないすべてのサイトの常設チャットを制御するには、[**常設チャットを有効にする**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="56bab-138">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="56bab-139">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56bab-139">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="56bab-140">常設チャットのユーザー ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="56bab-140">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="56bab-141">Skype for Business Server コントロール パネルでは、[ユーザー] でユーザーに割り当て可能なユーザー ポリシーを定義 **します**。</span><span class="sxs-lookup"><span data-stu-id="56bab-141">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="56bab-142">ユーザー ポリシーはグローバル ポリシーとサイト ポリシーに優先しますが、そのユーザー ポリシーを割り当てられている個々のユーザーにしか適用されません。</span><span class="sxs-lookup"><span data-stu-id="56bab-142">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="56bab-143">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="56bab-143">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="56bab-144">[スタート **] メニューから** Skype for Business Server コントロール パネルを選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="56bab-144">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="56bab-145">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットのポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56bab-145">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="56bab-146">[**新規**] をクリックし、[**ユーザー ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56bab-146">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="56bab-147">[**新規 常設チャットのポリシー**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="56bab-147">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="56bab-148">[**名前**] で、新しいユーザー ポリシーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="56bab-148">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="56bab-149">[ **説明]** に、ユーザー ポリシーの詳細 (たとえば、特定のユーザーの常設チャット ポリシー) を入力します。</span><span class="sxs-lookup"><span data-stu-id="56bab-149">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="56bab-150">ユーザー ポリシーによって特に制御されていないすべてのユーザーに対して常設チャットを制御するには、[常設チャットを有効にする] チェック ボックス **をオンまたは** オフにします。</span><span class="sxs-lookup"><span data-stu-id="56bab-150">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="56bab-151">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56bab-151">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="56bab-152">常設チャットのユーザー ポリシーをユーザー アカウントに適用するには</span><span class="sxs-lookup"><span data-stu-id="56bab-152">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="56bab-153">ユーザーが Skype for Business に対して有効になっている場合は、特定のユーザーに適切なポリシーを適用して、常設チャット サーバーで有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="56bab-153">If a user has been enabled for Skype for Business, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="56bab-154">このトピックの手順を使用して、以前に作成した常設チャット ユーザー ポリシーを 1 つ以上のユーザー アカウントまたはユーザー グループに適用します。</span><span class="sxs-lookup"><span data-stu-id="56bab-154">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="56bab-155">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="56bab-155">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="56bab-156">[スタート **] メニュー** から Skype for Business Server コントロール パネルを選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="56bab-156">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="56bab-157">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="56bab-157">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="56bab-158">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56bab-158">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="56bab-159">[Lync **Server ユーザーの編集** ] の [ **常設チャット** ポリシー] で、適用する常設チャット ユーザー ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="56bab-159">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="56bab-160">この **\<Automatic\>** 設定では、既定の有効なポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="56bab-160">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="56bab-161">これらの設定はサーバーによって自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="56bab-161">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="56bab-162">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56bab-162">Click **Commit**.</span></span>
    

