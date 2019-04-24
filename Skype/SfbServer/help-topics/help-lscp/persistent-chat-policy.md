---
title: 常設チャットのポリシー
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: 永続的なチャット グループの永続的なチャットのポリシー] ページを使用するには既定のグローバル ポリシーを構成するポリシーを作成する 1 つまたは複数追加ユーザーとサイトの展開など、グローバル、プール、サイト、またはユーザー レベルでポリシーを管理します。 ポリシーによってユーザーの永続的なチャット サーバーが有効である場合は、そのクライアントに永続的なチャット サーバー環境が表示されます。
ms.openlocfilehash: fc994f74acc0abf8d4d615d3d85ea3662c367904
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200640"
---
# <a name="persistent-chat-policy"></a><span data-ttu-id="1a025-104">常設チャットのポリシー</span><span class="sxs-lookup"><span data-stu-id="1a025-104">Persistent Chat Policy</span></span>
 
<span data-ttu-id="1a025-105">**永続的なチャット**グループの**永続的なチャットのポリシー** ] ページを使用するには既定のグローバル ポリシーを構成する 1 つまたは複数追加ユーザーとサイトのポリシーを作成するなど、グローバル、プール、サイト、またはユーザー レベルでポリシーを管理するために、展開します。</span><span class="sxs-lookup"><span data-stu-id="1a025-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="1a025-106">ポリシーによってユーザーの永続的なチャット サーバーが有効である場合は、そのクライアントに永続的なチャット サーバー環境が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a025-106">If Persistent Chat Server is enabled for a user by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
<span data-ttu-id="1a025-107">永続的なチャット サーバーを展開すると、構成しますが、削除されませんが、グローバル ポリシーは自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="1a025-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="1a025-108">グローバル ポリシーは、すべてのユーザーに適用するためにユーザー単位で設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1a025-108">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="1a025-109">作成し、グローバル ポリシー、および永続的なチャット サーバーのユーザーを有効にする複数のサイトやユーザー ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1a025-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="1a025-110">プールとサイトの永続的なチャット サーバー ポリシーでは、永続的なチャット サーバーのグローバル ポリシーで、そのサイトのユーザーについてを上書きします。</span><span class="sxs-lookup"><span data-stu-id="1a025-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="1a025-111">ユーザー ポリシーは、両方のグローバル プールをオーバーライドし、ユーザー ポリシーが割り当てられるユーザー用のポリシーをサイトします。</span><span class="sxs-lookup"><span data-stu-id="1a025-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1a025-112">構成し、永続的なチャット サーバーを使用してするには最初のトポロジでは、永続的なチャット サーバーのサポートを追加するのにはトポロジ ビルダーを使用し、トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="1a025-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="1a025-113">詳細については、[ビジネス サーバー 2015 トポロジの場合、Skype を永続的なチャットのサーバーを追加](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a025-113">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="1a025-114">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="1a025-114">Tasks that you can perform</span></span>

<span data-ttu-id="1a025-115">[**常設チャットのポリシー**] ページでは、常設チャット サーバー ポリシーの有効化と常設チャット サーバー ポリシーの管理のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="1a025-115">You can perform the following tasks on the **Persistent Chat Policy** page: enable Persistent Chat Server policy; manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="1a025-116">永続的なチャットのグローバル ポリシーを構成するのには</span><span class="sxs-lookup"><span data-stu-id="1a025-116">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="1a025-117">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザーから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1a025-117">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1a025-118">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a025-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="1a025-119">ビジネス サーバーのコントロール パネルの Skype では、**永続的なチャット**] をクリックし、**永続的なチャットのポリシー**] をクリックし、します。</span><span class="sxs-lookup"><span data-stu-id="1a025-119">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="1a025-120">ポリシーの一覧の [**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a025-120">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="1a025-121">[**編集 常設チャットのポリシー - Global**] で、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a025-121">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="1a025-122">グローバルという既定の名前を使用しない場合は、[**名前**] でグローバル ポリシーの新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a025-122">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="1a025-123">[**説明**] に、ユーザー ポリシーとは (たとえば、 _centralSiteName_のグローバル ポリシー) の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="1a025-123">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="1a025-124">すべてのサイトおよびサイト ポリシーまたはユーザー ポリシーによって特に制御のユーザーの永続的なチャットを制御するには、オンまたは**永続的なチャットを有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="1a025-124">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="1a025-125">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a025-125">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="1a025-126">永続的なチャットのサイトのポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="1a025-126">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="1a025-127">展開した各サイトのサイト固有の永続的なチャットのポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1a025-127">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="1a025-128">サイト ポリシーの構成はグローバル ポリシーよりも優先されますが、サイト ポリシーで指定されたサイトだけが対象となります。</span><span class="sxs-lookup"><span data-stu-id="1a025-128">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="1a025-129">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザーから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1a025-129">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1a025-130">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a025-130">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="1a025-131">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットのポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a025-131">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="1a025-132">[**新規作成**] をクリックし、[**サイト ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a025-132">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="1a025-133">[**サイトの選択**] でポリシーを適用するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a025-133">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="1a025-134">[**新規 常設チャットのポリシー**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a025-134">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="1a025-135">[**名前**] で、新しいサイト ポリシーの名前 (Redmond など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a025-135">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="1a025-136">[**説明**] にサイト ポリシーの内容の詳細 (「Redmond のチャット ルーム ポリシー」など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a025-136">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="1a025-137">サイト ポリシーによって特に制御されていないすべてのサイトの常設チャットを制御するには、[**常設チャットを有効にする**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="1a025-137">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="1a025-138">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a025-138">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="1a025-139">永続的なチャットのユーザー ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="1a025-139">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="1a025-140">ビジネス サーバーのコントロール パネルの Skype、**ユーザー**のユーザーに割り当てることができるユーザーのポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="1a025-140">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="1a025-141">ユーザー ポリシーは、グローバル ポリシーやサイト ポリシーよりも優先されますが、そのユーザー ポリシーを割り当てられた特定のユーザーのみを対象にします。</span><span class="sxs-lookup"><span data-stu-id="1a025-141">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="1a025-142">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザーから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1a025-142">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1a025-143">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a025-143">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="1a025-144">左側のナビゲーション バーで [**常設チャット**] をクリックし、[**常設チャットのポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a025-144">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="1a025-145">[**新規**] をクリックし、[**ユーザー ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a025-145">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="1a025-146">[**新規 常設チャットのポリシー**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a025-146">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="1a025-147">[**名前**] で、新しいユーザー ポリシーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a025-147">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="1a025-148">[**説明**] に、ユーザー ポリシーとは (たとえば、特定のユーザーの永続的なチャットのポリシーなど) に関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="1a025-148">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="1a025-149">ユーザー ポリシーでは、具体的には制御できないユーザーのためには、永続的なチャットを制御するには、オンまたは**永続的なチャットを有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="1a025-149">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="1a025-150">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a025-150">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="1a025-151">永続的なチャット ユーザー ポリシーをユーザー アカウントに適用するには</span><span class="sxs-lookup"><span data-stu-id="1a025-151">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="1a025-152">場合は、ユーザーが有効になって Skype ビジネス サーバーは、特定のユーザーを有効にするか、永続的なチャット サーバーを無効にする適切なポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="1a025-152">If a user has been enabled for Skype for Business Server, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="1a025-153">このトピックで以前に作成された永続的なチャット ユーザーのポリシーを 1 つまたは複数のユーザー アカウントまたはユーザー グループに適用するのに手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="1a025-153">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="1a025-154">CsPersistentChatAdministrator、CsAdministrator、または CsUserAdministrator の役割に割り当てられているユーザーから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1a025-154">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1a025-155">**[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a025-155">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="1a025-156">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="1a025-156">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="1a025-157">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a025-157">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="1a025-158">**永続的なチャット**ポリシーでは、 **Lync Server ユーザーの編集**では、永続的なチャット ユーザー ポリシーを適用するを選択します。</span><span class="sxs-lookup"><span data-stu-id="1a025-158">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1a025-159">**\<自動\>** の設定は、既定の有効なポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="1a025-159">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="1a025-160">これらの設定はサーバーにより自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1a025-160">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="1a025-161">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a025-161">Click **Commit**.</span></span>
    

